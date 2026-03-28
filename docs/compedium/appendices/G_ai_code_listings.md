# Додаток G. Лістинги коду ШІ

Цей додаток містить спрощені лістинги ключових алгоритмів штучного інтелекту, використаних для аналізу та гри в Aether Neutral 4×4. Код наведено на Python для наочності, але в реалізації гри використовується JavaScript/React.

## G.1. Представлення стану

```python
class GameState:
    def __init__(self, board, owner, cp, move_count):
        self.board = board          # list of int (0..15) of length 16
        self.owner = owner          # list of int (0/1/EMPTY) of length 16
        self.cp = cp                # 0 or 1 (player to move)
        self.move_count = move_count  # moves without merge

    def hash(self):
        # Zobrist hashing for transposition table
        pass
```

## G.2. Мінімакс з альфа-бета відсіченням

```python
def minimax(state, depth, alpha, beta, maximizing):
    if depth == 0 or state.winner is not None:
        return evaluate(state)

    if maximizing:
        max_eval = -inf
        for move in state.legal_moves():
            new_state = state.apply(move)
            eval = minimax(new_state, depth-1, alpha, beta, False)
            max_eval = max(max_eval, eval)
            alpha = max(alpha, eval)
            if beta <= alpha:
                break
        return max_eval
    else:
        min_eval = inf
        for move in state.legal_moves():
            new_state = state.apply(move)
            eval = minimax(new_state, depth-1, alpha, beta, True)
            min_eval = min(min_eval, eval)
            beta = min(beta, eval)
            if beta <= alpha:
                break
        return min_eval
```

## G.3. Евристична оцінка позиції

```python
def evaluate(state):
    score = 0
    for i in range(16):
        mask = state.board[i]
        if mask == 0: continue
        w = bin(mask).count('1')
        # вага
        score += w * w
        # загрози
        for t in targets[i]:
            other = state.board[t]
            if other == 0: continue
            if (mask | other) == FULL_MASK:
                score += 50000  # переможне злиття
            elif bin(mask | other).count('1') == 3:
                score += 2500   # потенційна загроза
    # бонус за порожні клітинки
    empty_count = state.board.count(0)
    score += empty_count * 5
    return score
```

## G.4. MCTS (Monte Carlo Tree Search) – псевдокод

```python
class MCTSNode:
    def __init__(self, state, parent=None):
        self.state = state
        self.parent = parent
        self.children = []
        self.visits = 0
        self.value = 0.0

def ucb1(node):
    return node.value / node.visits + sqrt(2 * log(node.parent.visits) / node.visits)

def mcts(root, iterations):
    for _ in range(iterations):
        node = root
        # selection
        while node.children and node.state.winner is None:
            node = max(node.children, key=ucb1)
        # expansion
        if node.state.winner is None and not node.children:
            for move in node.state.legal_moves():
                new_state = node.state.apply(move)
                node.children.append(MCTSNode(new_state, node))
            if node.children:
                node = random.choice(node.children)
        # simulation (rollout)
        result = simulate(node.state)
        # backpropagation
        while node:
            node.visits += 1
            node.value += result
            node = node.parent
    return max(root.children, key=lambda n: n.visits).move
```

## G.5. Генерація ходів коня на торі

```python
def knight_targets(sz, x, y):
    vectors = [(2,1),(2,-1),(-2,1),(-2,-1),
               (1,2),(1,-2),(-1,2),(-1,-2)]
    res = []
    for dx, dy in vectors:
        nx = (x + dx) % sz
        ny = (y + dy) % sz
        res.append((nx, ny))
    # remove duplicates (only needed for sz=4)
    return list(set(res))
```

## G.6. Приклад використання

```python
# Ініціалізація
state = GameState.initial(4, 4)  # 4×4, 4 types
ai = AI(minimax_depth=3)
best_move = ai.choose_move(state)
print(f"Best move: {best_move}")
```

## G.7. Примітки

- Наведені лістинги є спрощеними; повна реалізація включає Zobrist хешування, симетрії, адаптивну глибину та обмеження за часом.
- Код доступний у репозиторії `aether-tour/src/ai/`.

---
*Кінець додатку G.*

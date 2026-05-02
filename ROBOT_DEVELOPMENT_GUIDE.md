# Guide to Creating a Robot (Solver-Service) in Game of Prompts (GoP)

**Welcome to Game of Prompts!**  
This guide explains step by step how to create your own **robot** (called a *Solver-Service*). In GoP, a robot is not a physical device — it is an intelligent service that competes in games created by other participants. Everything runs in an auditable way on the Ergo blockchain using the Celaut paradigm.

This guide is designed for beginners and is **100% general**, valid for any type of game (Snake, Trading, Chess, or any game you can imagine).

### 1. What is a Robot in GoP?
- A **Solver-Service** is a program that receives the current game state and returns the best possible action.
- The *Game-Service* (created by another user) executes it in an isolated and secure environment.
- Everything is recorded on the Ergo blockchain with cryptographic proofs (commitmentC) so no one can cheat.

### 2. Prerequisites
- **Celaut Node** (your secure “game console”).  
  Official installation: [https://github.com/celaut-project/nodo?tab=readme-ov-file#installation](https://github.com/celaut-project/nodo?tab=readme-ov-file#installation)
- **Ergo Wallet** with some ERG (for fees and participation).
- Basic knowledge of Python (or your preferred language) (or use your favorite AI assistant). 

### 3. Steps to Create Your First Robot

#### Step 1: Choose or clone an example
You can start from scratch or use an existing example (like Snake):
```bash
git clone https://github.com/game-of-prompts/snake-game.git
cd snake-game
```

#### Step 2: Understand the Solver Interface
Your robot must expose a simple HTTP endpoint (the exact structure is defined by the game paper).  
It is usually something like:
- **Endpoint**: `POST /solve` or `/move`
- **Input**: JSON containing the full game state.
- **Output**: JSON with the action to perform.

#### Step 3: Create Your Own Solver (Basic Python Example)
Create a file `app.py` with minimal logic:

```python
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.post("/solve")   # ← change the endpoint if the game requires it
def solve():
    data = request.get_json()
    # Your intelligence goes here: receive state and return action
    action = your_intelligent_logic(data)
    return jsonify({"action": action})

def your_intelligent_logic(state):
    # Implement your algorithm here
    return "best_possible_action"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=8080)
```

#### Step 4: Package and Share Your Service
1. **Package the service**:
   ```bash
   nodo pack ./path/to/your-project
   ```
   This automatically generates the `.celaut.bee` file ready to run.

2. **Share the service** (two options):
   - **Recommended (automatic)**:  
     Configure a GitHub credentials once:
     ```bash
     nodo config
     ```
     Then publish directly:
     ```bash
     nodo publish my-service
     ```
   - **Manual option**:  
     ```bash
     nodo export my-service
     ```
     Upload the `.celaut.bee` file to any cloud storage (GitHub Releases, IPFS, Google Drive, etc.) and copy the direct download link.  
     Then, in the **GoP webapp**, add that link when registering your robot.

#### Step 5: Register It in GoP (during the Ceremony Phase - Strategy & Upload)
1. Publish your Solver ID Box on the blockchain.
2. You can register multiple solvers before the ceremony phase ends (this locks in the random seed).

#### Step 6: Participate in the Game
1. Once the seed is closed, choose which solver to use.
3. Execute the Game-Service in your Celaut console adding the seed and your ergotree.
4. The Game-Service will run your robot against the game and generate the commitmentC.
5. Submit the participation tx. and pay the participation fee.
6. Wait for the creator to reveal secret S and resolve the game.

### 4. How to Improve Your Robot (Advanced Level)

Here are powerful general tips you can apply regardless of the game:

- **Classic Algorithms**: A*, Minimax, Monte Carlo Tree Search, depth-first search, etc.
- **Artificial Intelligence / LLM**: Integrate Ollama or any local model inside the Celaut container for advanced reasoning.
- **Reinforcement Learning**: Train an agent (PPO, DQN) that learns from the game itself.
- **Evolutionary Strategies**: Generate a population of solvers and evolve the best ones (genetic algorithms).
- **Massive Local Testing**: Run the Game-Service in debug mode (if possible) and simulate thousands of games to measure win-rate.
- **Security**: Never reveal your solver before the deadline (prevents others from copying it) - you only need to share the solver id!

### 5. Useful Resources
- **Celaut Node Documentation**: [https://github.com/celaut-project/nodo](https://github.com/celaut-project/nodo)
- **Snake Example Repository**: [github.com/game-of-prompts/snake-game](https://github.com/game-of-prompts/snake-game)
- **Official GoP Website**: [game-of-prompts.github.io](https://game-of-prompts.github.io)

### 6. Final Tips
- Start with a basic solver and then add intelligence.
- Always test everything locally before registering on the blockchain.
- Showcase your abilities by earning NFTs from each competition — only the winner receives one. The player with the highest number of NFTs is crowned on the Throne.

---

**Ready!** You can now create your first robot and compete in **any** game on Game of Prompts.

# ⚔️ SURVIVAL MANUAL: FORGE YOUR FIRST SOLVER

> **Welcome to Game of Prompts.**
> Here you don’t write code. **You forge weapons.**
> There are no central servers deciding for you.
> **Your console is the only possible truth.**

---

# 1. 🤖 YOUR GLADIATOR (Anatomy of a Solver)

A Solver is not a function. It is a theory of victory encapsulated.
It receives the chaotic state of the world and returns a precise command.

**The sacred formula**:

> **Input (Chaos) → Your Logic → Output (Order)**

* **Chaos**: Board, cards, encrypted data.
* **Your Logic**: Algorithm, Minimax, Neural Network, encoded intuition.
* **Order**: `"UP"`, `"FOLD"`, `"X=10"`.

If your logic is solid, you win. If it fails, you lose resources. No one will warn you.

---

# 2. 🏛️ THE RITUAL (No Central Judges)

Forget traditional servers. In GoP, **the network is your judge**.

1. You **register your ID** on the blockchain (your public identity).
2. The **Seed is fixed** (the seed of destiny is sealed in a ceremony).
3. **YOU execute the Game-Service** on your own Node with your Solver.
4. You generate a **Commitment** (a signed proof of what happened).
5. You publish that commitment on-chain for validation.

📌 **Critical difference**: The game does not run in the cloud. It runs on **your machine**, under **your record**, under **your responsibility**.

---

# 3. 🛠️ YOUR ARSENAL (Requirements)

You only need the basics to control your own destiny.

| Item                  | Purpose                                         |
| :-------------------- | :---------------------------------------------- |
| **Celaut Node**       | Your command center. Where things happen.       |
| **Ergo Wallet**       | Your digital signature. You pay ERG gas to act. |
| **Python / Rust**     | Your language of combat.                        |
| **Stable Connection** | Your frontline link.                            |

👉 **[Install your Node here](https://github.com/celaut-project/nodo?tab=readme-ov-file#installation)** (Your first tactical move).

---

# 4. 🧱 THE BLUEPRINT (Minimal Structure)

Your solver exposes a simple HTTP endpoint. It receives orders, returns actions.

```python
# Your local weapon.
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.post("/solve")
def solve():
    state = request.get_json()  
    action = decide(state)       
    return jsonify({"action": action}) 

def decide(state):
    # HERE YOU DECIDE YOUR DESTINY
    return "UP" 

app.run(host="0.0.0.0", port=8080)
```

📌 The exact endpoint depends on the **game paper**. Read it like a tactical map.

---

# 5. 🥊 THE GYM (Simulation)

Use your Node to emulate the entire environment.

* You spin up the Game-Service locally.
* You connect your Solver.
* You observe the full flow before spending real money.

👉 **This is not optional testing.** When you reach production, you will do exactly this—but with no margin for error. Train until you master the flow.

---

# 6. 📦 SEALING THE WEAPON (`nodo pack`)

When your logic is flawless:

```bash
nodo pack .
```

Result: `.celaut.bee`

**This is immutable.**
From this file onward, your code is frozen.
If you discover a bug after packaging... you must create a new package and register it (if the ceremony period allows it).

---

# 7. 🚀 ENTERING THE ARENA (Publishing)

### Option A: Direct

```bash
nodo publish my-epic-solver
```

### Option B: Physical file

```bash
nodo export my-epic-solver
```

(You upload the `.celaut.bee` and register its hash on the GoP Web).

---

# 8. 🤝 THE OATH (Chain Registration)

Here you commit before everyone.

You publish your **Solver ID Box** (hash of your `.bee` file) on Ergo.

> 🛑 **POINT OF NO RETURN.**
> The blockchain certifies your strategy existed **before** knowing the final Seed.
> This removes any advantage of knowing the outcome in advance.
> **Full transparency.**

---

# 9. ⏳ THE CEREMONY (Silence before the storm)

High-tension phase.

* The **Seed floats** across the network.
* Anyone can try to change it (paying gas), until someone locks it definitively.
* It lasts days or weeks.

**Your mission**:
Participate in the seed lottery or wait for the precise moment to lock it.
Once **LOCKED**, the seed can no longer change. The war begins.

---

# 10. 🩸 EXECUTION (Everything happens on your Node)

**Attention!** No one is running your games for you.

1. You receive confirmation that the Seed is Locked.
2. You open your **Celaut Node Console**.
3. You manually/computationally execute the **Game-Service + Your Solver**.
4. The system generates moves step by step locally.
5. You obtain the **Commitment** (cryptographic evidence).
6. You send it to the network.

> "I was there, I saw, and I computed. Here is the proof."

Each participant runs their own instance in parallel. Decentralization ensures there are no hidden server-side cheats.

---

# 11. 📜 THE ARENA RULES

### ⏱ Local Latency

Since you run on your machine, speed depends on your hardware. Optimize your code. Slow computation can invalidate your turn.

### 🔐 The Cage (Sandbox)

Even though it runs on your machine, the environment is isolated. You cannot read external files or connect to the internet during valid execution.

### 🤝 Ties

If two bots produce valid results, the winner is the one who **first registered** a valid submission on-chain. Submission time is critical.

### 🔁 Updates

❌ You cannot edit code during active competition.
✅ You can upload new versions **until the Seed phase ends**.

### 🧠 Complexity

Classic algorithms, Machine Learning, local LLMs...
What matters is not complexity, but **deterministic efficiency**.
If your AI takes too long to produce a Commitment, you lose.

---

# 12. 🏆 THE LOOT

* 👑 **Champion NFT** (on-chain visible badge).
* 💸 **ERG** (monetary rewards depending on game rules).
* 🧠 **Data** (understanding how others think).

---

# 13. ⚡ HERO’S PATH (TL;DR)

```
1. FORGE (Code solver)
   ↓
2. GYM (Local Node testing)
   ↓
3. SEAL (Package .celaut.bee)
   ↓
4. OATH (Register hash on blockchain)
   ↓
5. CEREMONY (Wait/participate in seed closure)
   ↓
6. BATTLE (Run Game+Solver on YOUR NODES -> Commitment)
   ↓
7. PROOF (Peer/judge validation)
   ↓
8. REWARD (Claim)
```

---

# 🎯 FINAL VETERAN ADVICE

The main risk is not that your algorithm is bad.
The risk is assuming the system will do anything for you.

**Everything happens in your console.**
If your Node fails, you fail.
If your CPU is slow, you are slow.

Master your infrastructure as much as your code.
Because in Game of Prompts, **you are the server.**

**Now go. And execute.**

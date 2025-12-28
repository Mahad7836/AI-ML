# 🧠 Introduction to Artificial Intelligence

* **Turing Test:** Proposed by Alan Turing (1950). A computer passes if a human interrogator cannot distinguish it from a human being.
* **Rational Agent:** An agent that acts so as to maximize the expected value of its performance measure, given the percept sequence and its built-in knowledge.

---

## 2. Intelligent Agents & PEAS

To design an agent, we must first define its task environment using the **PEAS** framework:

* **P**erformance Measure: How do we define success?
* **E**nvironment: Where does the agent operate?
* **A**ctuators: How does the agent affect the world?
* **S**ensors: How does the agent perceive the world?

### Example: Self-Driving Car 🚗

| Component | Description |
| :--- | :--- |
| **Performance** | Safety, time, legal drive, comfort. |
| **Environment** | Roads, other cars, pedestrians, weather. |
| **Actuators** | Steering, accelerator, brake, signal, horn. |
| **Sensors** | Cameras, sonar, GPS, speedometer, odometer. |

### Example: Medical Diagnosis System 🏥

| Component | Description |
| :--- | :--- |
| **Performance** | Healthy patient, minimize costs, lawsuits. |
| **Environment** | Patient, hospital, staff. |
| **Actuators** | Screen display (questions/tests/diagnoses). |
| **Sensors** | Keyboard entry of symptoms. |

---

## 3. Properties of Environments

Environments determine how hard the problem is to solve.

1.  **Fully Observable vs. Partially Observable**
    * *Fully:* Sensors detect the complete state of the world (e.g., Chess).
    * *Partially:* Sensors are noisy or inaccurate (e.g., Poker, Self-driving car).
2.  **Deterministic vs. Stochastic**
    * *Deterministic:* Next state is perfectly determined by current state + action (e.g., Chess).
    * *Stochastic:* Next state involves randomness/uncertainty (e.g., Dice games, Weather).
3.  **Episodic vs. Sequential**
    * *Episodic:* Current decision doesn't affect future decisions (e.g., Image Classification).
    * *Sequential:* Current decision affects future opportunities (e.g., Chess, Driving).
4.  **Static vs. Dynamic**
    * *Static:* World doesn't change while the agent is thinking (e.g., Crossword puzzle).
    * *Dynamic:* World changes while thinking (e.g., Taxi driving).
5.  **Discrete vs. Continuous**
    * *Discrete:* Finite number of states/actions (e.g., Chess).
    * *Continuous:* Infinite range of values (e.g., Steering angle).
6.  **Single Agent vs. Multi-Agent**
    * *Single:* Solitaire.
    * *Multi:* Chess (Competitive), Traffic (Cooperative/Competitive).

---

## 4. Types of Agents

Agents range from simple reflexes to complex learning machines.

### 1. Simple Reflex Agent
* **Action:** Based *only* on the current percept. Ignores history.
* **Logic:** Condition-Action Rule (If `CarInFront` is `Braking` then `Brake`).
* **Limitation:** Only works if the environment is fully observable. Infinite loops in partially observable environments.

### 2. Model-Based Reflex Agent
* **Action:** Uses current percept + internal state.
* **Key:** Keeps track of the world (Internal State) because sensors don't see everything.
* **Example:** A car braking for a pedestrian currently hidden behind a truck (it remembers the pedestrian was there).

### 3. Goal-Based Agent
* **Action:** Selects actions that achieve a specific goal.
* **Key:** Search and Planning. "What sequence of actions gets me to the destination?"
* **Example:** GPS finding the shortest path.

### 4. Utility-Based Agent
* **Action:** Maximizes a "happiness" score (Utility).
* **Key:** Trade-offs. "I can get there in 10 mins (unsafe) or 15 mins (safe)." Utility helps choose the *best* way, not just *any* way.

### 5. Learning Agent
* **Action:** Operates in unknown environments and becomes more competent over time.
* **Components:**
    * *Critic:* Evaluates how well the agent is doing.
    * *Learning Element:* Makes improvements.
    * *Problem Generator:* Suggests exploratory actions.
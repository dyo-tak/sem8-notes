# 🧠 Big Picture: What’s This All About?

Think of social networks as **digital cities**. Just like gossip, memes, or fashion trends spread through people in a city, **information diffuses** through social media.

This module explores **how information spreads**, **why some trends go viral**, and **how we can model and predict these cascades** — from a meme exploding on Twitter to a misinformation post going viral on WhatsApp.

---

## 🚀 1. **Core Concepts: The 5C Framework for Info Spread**

Use the mnemonic: **5C = Cascade, Contagion, Channel, Community, Control**

| Term          | Meaning in Social Media                     | Analogy                                 |
| ------------- | ------------------------------------------- | --------------------------------------- |
| **Cascade**   | The trail of information spreading          | A retweet chain on Twitter              |
| **Contagion** | The “thing” that spreads                    | A viral hashtag, a meme, or a rumor     |
| **Channel**   | How info moves from user to user            | Instagram DMs, Twitter retweets         |
| **Community** | The social structure through which it flows | A fandom group or WhatsApp family group |
| **Control**   | Intervention to influence spread            | Content moderation, fact-check warnings |

---

## 🧠 2. **Herd Behavior & Information Cascades**

### 🔁 What is Herd Behavior?

> People act based on what others are doing, not what they know.

📱 **Example**: You see a long line outside a restaurant and decide to eat there too — without checking reviews.

📘 *Social Media Mining* ties this to **“network observability”** — when public behaviors are visible, people imitate.

---

### 📣 What is an Information Cascade?

A **cascade** happens when:

* Users sequentially **observe others**.
* They **ignore private info** and copy peers.
* It **snowballs into virality**.

📱 **Example**: You retweet a hashtag because 20 of your friends did — not because you believe it’s true.

📚 Related theory: **Bayesian inference** — users make inferences from prior actions.

---

## 🌐 3. **Echo Chambers**

🧠 Echo chambers are **self-reinforcing groups** where everyone thinks alike.

📱 **Example**: A Facebook group where all posts support the same political view, suppressing opposing ideas.

🔁 It reduces **information diversity**, increasing:

* Fake news spread
* Confirmation bias
* Social polarization

📘 Chakraborty explains this via **homophily**: people cluster with similar nodes → leads to **clique-like subgraphs**.

---

## 💡 4. **Models of Diffusion: How Ideas Travel**

Let’s break it into **Decision-based** and **Epidemic-style** models.

---

### ✅ A. Decision-Based Models (Game Theory Inspired)

🎮 Imagine users as players in a game, choosing:

* A (new idea)
* B (old idea)

They want to **match their friends** to **maximize payoff**.

**Threshold Rule**:

> “I’ll switch to A if more than q% of my neighbors have adopted A.”

📱 **Example**: You install Telegram only after most of your WhatsApp friends are there.

📘 *Morris (2000)* introduced this as **local interaction game**.

---

### ⚙️ Threshold Equation:

If neighbors adopting A = $p$, then switch to A if:

$$
p \geq \frac{b}{a + b}
$$

Where:

* $a, b$ = payoff from matching behavior
* $p$ = proportion of neighbors using A

---

### 🔄 Multiple Choice Model

You can adopt **both A and B**, like Netflix + Prime Video — but it costs more (storage, subscriptions).

---

### 🔮 Independent Cascade Model (ICM)

This is **probabilistic**: each user has one chance to influence neighbors.

📱 **Example**: You see a tweet → 30% chance you’ll retweet it → one attempt only.

---

## 🦠 B. Epidemic Models — *“Virality as a Virus”*

Use the mnemonic: **“SIRS” → SI, SIS, SIR, SEIR**

| Model    | Description                     | Example                             |
| -------- | ------------------------------- | ----------------------------------- |
| **SI**   | Infected forever                | WhatsApp forwards                   |
| **SIS**  | Can get infected again          | Recurring memes on Reddit           |
| **SIR**  | Once infected, then immune      | Ice Bucket Challenge (one-time)     |
| **SEIR** | Exposure before infection       | Fake news – read but not shared yet |
| **SEIZ** | Adds Skeptics who ignore rumors | Users who fact-check before sharing |

📘 SEIR is widely used in **rumor modeling** and **misinformation control**.

---

### 🧪 Key Metric: Basic Reproduction Number

$$
R_0 = k \times p
$$

* $k$: contacts per user

* $p$: transmission probability

* If $R_0 > 1$ → cascade grows

* If $R_0 < 1$ → cascade dies out

---

## 🔍 5. **Cascade Prediction: Who Will Spread What and How Much?**

### 🎯 Goal:

Predict:

* Will the cascade go viral?
* How big will it be?
* Who will spread it next?

---

### 🧠 Approaches:

| Type              | Method                       | Example                          |
| ----------------- | ---------------------------- | -------------------------------- |
| **Graph-Based**   | ICM, LT, community detection | Meme diffusion                   |
| **ML Models**     | RF, GNNs, RNNs               | Predict retweets                 |
| **Centrality**    | Degree, betweenness          | Find influencers                 |
| **Temporal**      | Time-series (ARIMA, LSTM)    | Track viral growth               |
| **Content-Based** | Sentiment, virality score    | Predict which tweet will explode |

---

### 🔬 Deep Learning Models

#### 1. **DeepCas**

* Uses **Graph Neural Networks** + LSTM
* Predicts **cascade size** over time

#### 2. **DeepHawkes**

* Builds on **Hawkes process** (time-based influence)
* Predicts **retweet arrival rate**

📘 These models combine **temporal, structural, and influence-based features** — echoing techniques from *Social Media Mining*.

---

## 🎯 TL;DR Cheat Sheet

| Concept            | Analogy                      | Key Idea                           |
| ------------------ | ---------------------------- | ---------------------------------- |
| Herd Behavior      | Eating at crowded restaurant | Imitation without private analysis |
| Info Cascade       | Chain retweets               | Sequential adoption based on peers |
| Echo Chamber       | Political WhatsApp group     | Filtered, reinforcing opinions     |
| SI/SIR/SEIR        | Viral trends or rumors       | Epidemiological spread             |
| Threshold Model    | Peer pressure tipping point  | Adopt when enough friends adopt    |
| ICM                | One-shot chance to influence | Probabilistic propagation          |
| DeepCas/DeepHawkes | Predicting virality          | Learn influence & timing dynamics  |

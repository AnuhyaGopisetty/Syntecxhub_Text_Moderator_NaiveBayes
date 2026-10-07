# Dual-Layer Text Analysis Engine

A lightweight, zero-dependency browser dashboard built in vanilla JavaScript. It uses a two-stage pipeline—combining a hard keyword blocklist with a custom Multinomial Naive Bayes classifier—to analyze text sentiment and catch compliance flags in real time.

## Features

* **No Dependencies:** Pure client-side JavaScript. No `npm install`, no frameworks, no heavy libraries.
* **Two-Stage Pipeline:** 
  1. *Deterministic Layer:* Instantly intercepts critical trigger words via a fast array-matching proxy.
  2. *Probabilistic Layer:* Processes remaining text through a custom Naive Bayes classifier using log probabilities and Laplace smoothing.
* **Privacy Controls:** Automatically scrubs flagged terms from the UI viewport immediately to protect screen privacy in open work environments.
* **Live Analytics:** Evaluates model performance out-of-the-box, showing real-time Accuracy and F1-Scores.

## How It Works

1. **Tokenization:** Text is stripped of punctuation, normalized to lowercase, and split into clean word tokens.
2. **Blocklist Check:** The tokens hit a fast array interceptor first. If a matched term is found, execution stops immediately, and the UI text field is cleared.
3. **Statistical Scoring:** If the text passes the blocklist, the Naive Bayes engine calculates the log-likelihood scores based on token distributions to output an approval or review flag.

## Setup

Just clone the repository and open the HTML file directly in any modern web browser:

```bash
git clone https://github.com
```

Open `Moderator.html` in your browser to run the interface locally.

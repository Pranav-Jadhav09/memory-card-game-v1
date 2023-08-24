<div align="center">

![GitHub repo size](https://img.shields.io/github/repo-size/Pranav-Jadhav09/memory-card-game-v1)
[![Twitter Follow](https://img.shields.io/twitter/follow/Pranav_Jadhav09?style=social)](https://twitter.com/Pranav_Jadhav09)

<br />
<br />

<img src="./assets/images/que_icon.svg" style="width: 150px">

<h2 align="center">Memory Card Game v.1.0</h2>
Built a Memory Card game using JavaScript.

<a href="https://memorycard-game-v1-jrpranav.netlify.app/"><strong>➥ Play Now</strong></a>

</div>

<br />

### 🤷🏻‍♂️ What I Learn

#### 🌟 Explain Game Logic step by step:

1. **Selecting Elements**: The code starts by selecting all HTML elements with the class name "card" using the `document.querySelectorAll(".card")` method. It assigns these elements to the `cards` constant.

2. **Variable Initialization**: Two variables, `matched`, `cardOne`, and `cardTwo`, are initialized. `matched` keeps track of how many pairs of cards have been successfully matched. `cardOne` and `cardTwo` will be used to temporarily store the clicked cards to compare and match.

3. **disableDeck Flag**: The `disableDeck` variable is used to control whether user interactions (clicks on cards) should be disabled temporarily. It's set to `false` initially.

4. **flipCard Function**: This function is called when a card is clicked. It accepts an event object but uses destructuring to directly extract the `target` property and rename it to `clickedCard`.

   - It checks if `cardOne` is not the same as `clickedCard` and if the `disableDeck` flag is not true.
   - If these conditions are met, it adds the "flip" class to the clicked card, triggering a flip animation.
   - If `cardOne` is not set, it sets `cardOne` to the clicked card and exits the function.
   - If `cardOne` is already set, it sets `cardTwo` to the clicked card, disables further clicks (`disableDeck = true`), and gets the image sources of both cards.
   - It then calls the `matchCards` function to check if the clicked cards match.

5. **matchCards Function**: This function is called when two cards are clicked and need to be checked for a match.

   - It takes two image URLs, `img1` and `img2`, as arguments.
   - If the images match (i.e., `img1` is the same as `img2`), it increments the `matched` counter.
   - If all pairs are matched (`matched` equals 8), it schedules a card shuffle after a delay of 1 second.
   - It removes the "click" event listeners from the matched cards, resets the `cardOne` and `cardTwo` variables, and sets `disableDeck` to `false`.
   - If the images don't match, it adds a "shake" animation class to both cards after a delay of 400ms.
   - After another delay of 1200ms, it removes the "shake" and "flip" classes from both cards, resets `cardOne` and `cardTwo`, and sets `disableDeck` to `false`.

6. **shuffleCard Function**: This function is responsible for shuffling and resetting the cards.

   - It resets the `matched` counter and sets `disableDeck` to `false`.
   - It initializes an array `arr` containing numbers from 1 to 8 in pairs (representing the different card images) and then shuffles the array randomly.
   - It loops through the `cards` using `forEach` and performs the following actions:
     - Removes the "flip" class to ensure all cards are face-down.
     - Updates the `src` attribute of the card's image to match the shuffled `arr` for that card.
     - Adds a "click" event listener to the card, connecting it to the `flipCard` function.

7. **Initial Shuffle**: The `shuffleCard` function is called initially to shuffle and set up the cards.

8. **Event Listeners**: Finally, event listeners are attached to all cards to trigger the `flipCard` function when a card is clicked.

### Prerequisites

Before you begin, ensure you have met the following requirements:

- [Git](https://git-scm.com/downloads "Download Git") must be installed on your operating system.

### Run Locally

To run **Memory Card Ga v.1.0**, run this command on your git bash:

Linux and macOS:

```bash
sudo git clone https://github.com/Pranav-Jadhav09/memory-card-ga-v1.git
```

Windows:

```bash
git clone https://github.com/Pranav-Jadhav09/memory-card-ga-v1.git
```

### License

MIT

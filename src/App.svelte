<script lang="ts">
    import FlashCard from "./lib/FlashCard.svelte";

    // Define flash cards data structure
    // Create a shuffled version of the flashcards
    const flashCards = [
        // μάχη (battle - feminine)
        { id:  1, question: "ἡ μάχη", answer: "nom ev" },
        { id:  2, question: "τῆς μάχης", answer: "gen ev" },
        { id:  3, question: "τῇ μάχῃ", answer: "dat ev" },
        { id:  4, question: "τὴν μάχην", answer: "acc ev" },
        { id:  5, question: "αἱ μάχαι", answer: "nom mv" },
        { id:  6, question: "τῶν μαχῶν", answer: "gen mv" },
        { id:  7, question: "ταῖς μάχαις", answer: "dat mv" },
        { id:  8, question: "τὰς μάχας", answer: "acc mv" },
        
        // χώρα (country/land - feminine)
        { id:  9, question: "ἡ χώρα", answer: "nom ev" },
        { id: 10, question: "τῆς χώρας", answer: "gen ev" },
        { id: 11, question: "τῇ χώρᾳ", answer: "dat ev" },
        { id: 12, question: "τὴν χώραν", answer: "acc ev" },
        { id: 13, question: "αἱ χῶραι", answer: "nom mv" },
        { id: 14, question: "τῶν χωρῶν", answer: "gen mv" },
        { id: 15, question: "ταῖς χώραις", answer: "dat mv" },
        { id: 16, question: "τὰς χώρας", answer: "acc mv" },
        
        // δεσπότης (master - masculine)
        { id: 17, question: "ὁ δεσπότης", answer: "nom ev" },
        { id: 18, question: "τοῦ δεσπότου", answer: "gen ev" },
        { id: 19, question: "τῷ δεσπότῃ", answer: "dat ev" },
        { id: 20, question: "τὸν δεσπότην", answer: "acc ev" },
        { id: 21, question: "οἱ δεσπόται", answer: "nom mv" },
        { id: 22, question: "τῶν δεσποτῶν", answer: "gen mv" },
        { id: 23, question: "τοῖς δεσπόταις", answer: "dat mv" },
        { id: 24, question: "τοὺς δεσπότας", answer: "acc mv" },
        
        // δοῦλος (slave - masculine)
        { id: 25, question: "ὁ δοῦλος", answer: "nom ev" },
        { id: 26, question: "τοῦ δούλου", answer: "gen ev" },
        { id: 27, question: "τῷ δούλῳ", answer: "dat ev" },
        { id: 28, question: "τὸν δοῦλον", answer: "acc ev" },
        { id: 29, question: "οἱ δοῦλοι", answer: "nom mv" },
        { id: 30, question: "τῶν δούλων", answer: "gen mv" },
        { id: 31, question: "τοῖς δούλοις", answer: "dat mv" },
        { id: 32, question: "τοὺς δούλους", answer: "acc mv" },
        
        // θηρίον (beast/animal - neuter)
        { id: 33, question: "τὸ θηρίον", answer: "nom acc ev" },
        { id: 34, question: "τοῦ θηρίου", answer: "gen ev" },
        { id: 35, question: "τῷ θηρίῳ", answer: "dat ev" },
        { id: 36, question: "τὰ θηρία", answer: "nom acc mv" },
        { id: 37, question: "τῶν θηρίων", answer: "gen mv" },
        { id: 38, question: "τοῖς θηρίοις", answer: "dat mv" },
        //{
        //    id: 31,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινός",
        //    answer: "nom ev m",
        //},
        //{
        //    id: 32,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινή",
        //    answer: "nom ev f",
        //},
        //{
        //    id: 33,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινόν",
        //    answer: "nom ev o",
        //},
        //{
        //    id: 34,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινοῦ",
        //    answer: "gen ev m",
        //},
        //{
        //    id: 35,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινῆς",
        //    answer: "gen ev f",
        //},
        //{
        //    id: 36,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινοῦ",
        //    answer: "gen ev o",
        //},
        //{
        //    id: 37,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινόν",
        //    answer: "acc ev m",
        //},
        //{
        //    id: 38,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινήν",
        //    answer: "acc ev f",
        //},
        //{
        //    id: 39,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινόν",
        //    answer: "acc ev o",
        //},
        //{
        //    id: 40,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινοί",
        //    answer: "nom mv m",
        //},
        //{
        //    id: 41,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δειναί",
        //    answer: "nom mv f",
        //},
        //{
        //    id: 42,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινά",
        //    answer: "nom mv o",
        //},
        //{
        //    id: 43,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινῶν",
        //    answer: "gen mv o",
        //},
        //{
        //    id: 44,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινῶν",
        //    answer: "gen mv f",
        //},
        //{
        //    id: 45,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινῶν",
        //    answer: "gen mv o",
        //},
        //{
        //    id: 46,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινούς",
        //    answer: "acc mv m",
        //},
        //{
        //    id: 47,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινάς",
        //    answer: "acc mv f",
        //},
        //{
        //    id: 48,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. δεινά",
        //    answer: "acc mv o",
        //},
        //{
        //    id: 49,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρός",
        //    answer: "nom ev m",
        //},
        //{
        //    id: 50,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρά",
        //    answer: "nom ev f",
        //},
        //{
        //    id: 51,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρόν",
        //    answer: "nom ev o",
        //},
        //{
        //    id: 52,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακροῦ",
        //    answer: "gen ev m",
        //},
        //{
        //    id: 53,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρᾶς",
        //    answer: "gen ev f",
        //},
        //{
        //    id: 54,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακροῦ",
        //    answer: "gen ev o",
        //},
        //{
        //    id: 55,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρόν",
        //    answer: "acc ev m",
        //},
        //{
        //    id: 56,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακράν",
        //    answer: "acc ev f",
        //},
        //{
        //    id: 57,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρόν",
        //    answer: "acc ev o",
        //},
        //{
        //    id: 58,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακροί",
        //    answer: "nom mv m",
        //},
        //{
        //    id: 59,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακραί",
        //    answer: "nom mv f",
        //},
        //{
        //    id: 60,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρά",
        //    answer: "nom mv o",
        //},
        //{
        //    id: 61,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρῶν",
        //    answer: "gen mv m",
        //},
        //{
        //    id: 62,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρῶν",
        //    answer: "gen mv f",
        //},
        //{
        //    id: 63,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρῶν",
        //    answer: "gen mv o",
        //},
        //{
        //    id: 64,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρούς",
        //    answer: "acc mv m",
        //},
        //{
        //    id: 65,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακράς",
        //    answer: "acc mv f",
        //},
        //{
        //    id: 66,
        //    question:
        //        "geef de naamval en het getal van het bijv. nw. μακρά",
        //    answer: "acc mv o",
        //},
    ];
    let shuffledCards = [];

    // Fisher-Yates shuffle algorithm function
    function shuffleArray(array: any) {
        // Create a copy of the original array to avoid modifying it
        const arrayCopy = [...array];
        // Start from the last element and swap it with a randomly selected element
        for (let i = arrayCopy.length - 1; i > 0; i--) {
            // Pick a random index from 0 to i
            const j = Math.floor(Math.random() * (i + 1));
            // Swap elements at i and j
            [arrayCopy[i], arrayCopy[j]] = [arrayCopy[j], arrayCopy[i]];
        }
        return arrayCopy;
    }

    // Initialize shuffled cards when component loads
    shuffledCards = shuffleArray(flashCards);

    // Keep track of the current card index
    let currentCardIndex = 0;

    // State for tracking points system
    let points = 0;
    let attempted = 0;

    // Function to go to the next card
    // Function to go to the next card
    function nextCard() {
        if (currentCardIndex < shuffledCards.length - 1) {
            currentCardIndex++;
        }
    }

    // Function to go to the previous card
    function prevCard() {
        if (currentCardIndex > 0) {
            currentCardIndex--;
        }
    }
    // Function to update points when an answer is submitted
    function handleAnswerSubmit(event: any) {
        const isCorrect = event.detail.isCorrect;
        attempted++;

        if (isCorrect) {
            points++; // Add 1 point for correct answer

            // Set a 2-second delay for correct answers before moving to the next card
            if (currentCardIndex < shuffledCards.length - 1) {
                setTimeout(() => {
                    nextCard();
                }, 2000);
            }
        } else {
            // No point deduction for incorrect answers

            // Set a 5-second delay for incorrect answers before moving to the next card
            if (currentCardIndex < shuffledCards.length - 1) {
                setTimeout(() => {
                    nextCard();
                }, 5000);
            }
        }
    }
</script>

<main>
    <div class="container">
        <h1>Flash Cards Grieks Grammatica</h1>

        <div class="score-container">
            <p>Points: {points} (Attempted: {attempted})</p>
        </div>

        <div class="card-container">
            <FlashCard
                flashCard={shuffledCards[currentCardIndex]}
                on:answerSubmitted={handleAnswerSubmit}
            />
        </div>

        <div class="navigation">
            <button on:click={prevCard} disabled={currentCardIndex === 0}
                >Previous</button
            >
            <span class="card-counter"
                >{currentCardIndex + 1} / {shuffledCards.length}</span
            >
            <button
                on:click={nextCard}
                disabled={currentCardIndex === shuffledCards.length - 1}
                >Next</button
            >
        </div>
    </div>
</main>

<style>
    :global(body) {
        background-color: #10abb4;
        color: #004c50;
        margin: 0;
        padding: 0;
        font-family:
            -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen-Sans,
            Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
    }

    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        max-width: 800px;
        margin: 0 auto;
        padding: 20px;
        background-color: white;
        border-radius: 12px;
        box-shadow: 0 4px 12px rgba(0, 76, 80, 0.1);
    }

    h1 {
        color: #004c50;
        margin-bottom: 20px;
        font-weight: 700;
        text-align: center;
    }

    .score-container {
        margin-bottom: 20px;
        font-size: 1.2rem;
        font-weight: bold;
        color: #004c50;
        background-color: rgba(16, 171, 180, 0.1);
        padding: 8px 16px;
        border-radius: 8px;
    }

    .card-container {
        width: 100%;
        margin-bottom: 20px;
    }

    .navigation {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        max-width: 400px;
        padding: 10px;
        background-color: rgba(0, 147, 156, 0.05);
        border-radius: 8px;
    }

    button {
        background-color: #00939c;
        color: white;
        border: none;
        padding: 10px 20px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        border-radius: 4px;
        transition: all 0.3s ease;
        font-weight: 500;
        box-shadow: 0 2px 4px rgba(0, 76, 80, 0.2);
    }

    button:hover {
        background-color: #10abb4;
        transform: translateY(-2px);
        box-shadow: 0 4px 8px rgba(0, 76, 80, 0.3);
    }

    button:disabled {
        background-color: rgba(0, 147, 156, 0.3);
        cursor: not-allowed;
        box-shadow: none;
        transform: none;
    }

    .card-counter {
        font-size: 1rem;
        color: #502000;
        font-weight: 600;
        background-color: rgba(156, 62, 0, 0.1);
        padding: 4px 10px;
        border-radius: 4px;
    }
</style>

<script lang="ts">
    import FlashCard from "./lib/FlashCard.svelte";

    // Define flash cards data structure
    // Create a shuffled version of the flashcards
    const flashCards = [
        {
            id: 1,
            question: "geef de naamval en getal van het zelfst. nw. ἡ μάχη",
            answer: "nom enk",
        },
        {
            id: 2,
            question: "geef de naamval en getal van het zelfst. nw. τῆς μάχης ",
            answer: "gen enk",
        },
        {
            id: 3,
            question: "geef de naamval en getal van het zelfst. nw. τὴν μάχην",
            answer: "acc enk",
        },
        {
            id: 4,
            question: "geef de naamval en getal van het zelfst. nw. αἱ μάχαι",
            answer: "nom mv",
        },
        {
            id: 5,
            question: "geef de naamval en getal van het zelfst. nw. τῶν μαχῶν",
            answer: "gen mv",
        },
        {
            id: 6,
            question: "geef de naamval en getal van het zelfst. nw. τὰς μάχας",
            answer: "acc mv",
        },
        {
            id: 7,
            question: "geef de naamval en getal van het zelfst. nw. ἡ χώρα",
            answer: "nom enk",
        },
        {
            id: 8,
            question: "geef de naamval en getal van het zelfst. nw. ὁ δεσπότης",
            answer: "nom enk",
        },
        {
            id: 9,
            question: "geef de naamval en getal van het zelfst. nw. ὁ δοῦλος",
            answer: "nom enk",
        },
        {
            id: 10,
            question: "geef de naamval en getal van het zelfst. nw. τὸ θηρίον",
            answer: "nom acc enk",
        },
        {
            id: 11,
            question: "geef de naamval en getal van het zelfst. nw. τῆς χώρας",
            answer: "gen enk",
        },
        {
            id: 12,
            question:
                "geef de naamval en getal van het zelfst. nw. τοῦ δεσπότου",
            answer: "gen enk",
        },
        {
            id: 13,
            question: "geef de naamval en getal van het zelfst. nw. τοῦ δούλου",
            answer: "gen enk",
        },
        {
            id: 14,
            question: "geef de naamval en getal van het zelfst. nw. τοῦ θηρίου",
            answer: "gen enk",
        },
        {
            id: 15,
            question: "geef de naamval en getal van het zelfst. nw. τὴν χώραν",
            answer: "acc enk",
        },
        {
            id: 16,
            question:
                "geef de naamval en getal van het zelfst. nw. τὸν δεσπότην",
            answer: "acc enk",
        },
        {
            id: 17,
            question: "geef de naamval en getal van het zelfst. nw. τὸν δοῦλον",
            answer: "acc enk",
        },
        {
            id: 19,
            question: "geef de naamval en getal van het zelfst. nw. αἱ χῶραι",
            answer: "nom mv",
        },
        {
            id: 20,
            question:
                "geef de naamval en getal van het zelfst. nw. οἱ δεσπόται",
            answer: "nom mv",
        },
        {
            id: 21,
            question: "geef de naamval en getal van het zelfst. nw. οἱ δοῦλοι",
            answer: "nom mv",
        },
        {
            id: 22,
            question: "geef de naamval en getal van het zelfst. nw. τὰ θηρία",
            answer: "nom acc mv",
        },
        {
            id: 23,
            question: "geef de naamval en getal van het zelfst. nw. τῶν χώρων",
            answer: "gen mv",
        },
        {
            id: 24,
            question:
                "geef de naamval en getal van het zelfst. nw. τῶν δεσποτῶν",
            answer: "gen mv",
        },
        {
            id: 25,
            question: "geef de naamval en getal van het zelfst. nw. τῶν δούλων",
            answer: "gen mv",
        },
        {
            id: 26,
            question: "geef de naamval en getal van het zelfst. nw. τῶν θηρίων",
            answer: "gen mv",
        },
        {
            id: 27,
            question: "geef de naamval en getal van het zelfst. nw. τὰς χώρας",
            answer: "acc mv",
        },
        {
            id: 28,
            question:
                "geef de naamval en getal van het zelfst. nw. τοὺς δεσπότας",
            answer: "acc mv",
        },
        {
            id: 29,
            question:
                "geef de naamval en getal van het zelfst. nw. τοὺς δούλους",
            answer: "acc mv",
        },
        {
            id: 31,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινός",
            answer: "nom enk m",
        },
        {
            id: 32,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινή",
            answer: "nom enk f",
        },
        {
            id: 33,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινόν",
            answer: "nom enk o",
        },
        {
            id: 34,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινοῦ",
            answer: "gen enk m",
        },
        {
            id: 35,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινῆς",
            answer: "gen enk f",
        },
        {
            id: 36,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινοῦ",
            answer: "gen enk o",
        },
        {
            id: 37,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινόν",
            answer: "acc enk m",
        },
        {
            id: 38,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινήν",
            answer: "acc enk f",
        },
        {
            id: 39,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινόν",
            answer: "acc enk o",
        },
        {
            id: 40,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινοί",
            answer: "nom mv m",
        },
        {
            id: 41,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δειναί",
            answer: "nom mv f",
        },
        {
            id: 42,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινά",
            answer: "nom mv o",
        },
        {
            id: 43,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινῶν",
            answer: "gen mv o",
        },
        {
            id: 44,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινῶν",
            answer: "gen mv f",
        },
        {
            id: 45,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινῶν",
            answer: "gen mv o",
        },
        {
            id: 46,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινούς",
            answer: "acc mv m",
        },
        {
            id: 47,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινάς",
            answer: "acc mv f",
        },
        {
            id: 48,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. δεινά",
            answer: "acc mv o",
        },
        {
            id: 49,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρός",
            answer: "nom enk m",
        },
        {
            id: 50,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρά",
            answer: "nom enk f",
        },
        {
            id: 51,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρόν",
            answer: "nom enk o",
        },
        {
            id: 52,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακροῦ",
            answer: "gen enk m",
        },
        {
            id: 53,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρᾶς",
            answer: "gen enk f",
        },
        {
            id: 54,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακροῦ",
            answer: "gen enk o",
        },
        {
            id: 55,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρόν",
            answer: "acc enk m",
        },
        {
            id: 56,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακράν",
            answer: "acc enk f",
        },
        {
            id: 57,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρόν",
            answer: "acc enk o",
        },
        {
            id: 58,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακροί",
            answer: "nom mv m",
        },
        {
            id: 59,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακραί",
            answer: "nom mv f",
        },
        {
            id: 60,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρά",
            answer: "nom mv o",
        },
        {
            id: 61,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρῶν",
            answer: "gen mv m",
        },
        {
            id: 62,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρῶν",
            answer: "gen mv f",
        },
        {
            id: 63,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρῶν",
            answer: "gen mv o",
        },
        {
            id: 64,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρούς",
            answer: "acc mv m",
        },
        {
            id: 65,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακράς",
            answer: "acc mv f",
        },
        {
            id: 66,
            question:
                "geef de naamval, het getal, en het geslacht van het bijv. nw. μακρά",
            answer: "acc mv o",
        },
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

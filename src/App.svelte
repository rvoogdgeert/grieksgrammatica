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
            answer: "nom mev",
        },
        {
            id: 5,
            question: "geef de naamval en getal van het zelfst. nw. τῶν μαχῶν",
            answer: "gen mev",
        },
        {
            id: 6,
            question: "geef de naamval en getal van het zelfst. nw. τὰς μάχας",
            answer: "acc mev",
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
            answer: "nom enk",
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
            id: 18,
            question: "geef de naamval en getal van het zelfst. nw. τὸ θηρίον",
            answer: "acc enk",
        },
        {
            id: 19,
            question: "geef de naamval en getal van het zelfst. nw. αἱ χῶραι",
            answer: "nom mev",
        },
        {
            id: 20,
            question:
                "geef de naamval en getal van het zelfst. nw. οἱ δεσπόται",
            answer: "nom mev",
        },
        {
            id: 21,
            question: "geef de naamval en getal van het zelfst. nw. οἱ δοῦλοι",
            answer: "nom mev",
        },
        {
            id: 22,
            question: "geef de naamval en getal van het zelfst. nw. τὰ θηρία",
            answer: "nom mev",
        },
        {
            id: 23,
            question: "geef de naamval en getal van het zelfst. nw. τῶν χώρων",
            answer: "gen mev",
        },
        {
            id: 24,
            question:
                "geef de naamval en getal van het zelfst. nw. τῶν δεσποτῶν",
            answer: "gen mev",
        },
        {
            id: 25,
            question: "geef de naamval en getal van het zelfst. nw. τῶν δούλων",
            answer: "gen mev",
        },
        {
            id: 26,
            question: "geef de naamval en getal van het zelfst. nw. τῶν θηρίων",
            answer: "gen mev",
        },
        {
            id: 27,
            question: "geef de naamval en getal van het zelfst. nw. τὰς χώρας",
            answer: "acc mev",
        },
        {
            id: 28,
            question:
                "geef de naamval en getal van het zelfst. nw. τοὺς δεσπότας",
            answer: "acc mev",
        },
        {
            id: 29,
            question:
                "geef de naamval en getal van het zelfst. nw. τοὺς δούλους",
            answer: "acc mev",
        },
        {
            id: 30,
            question: "geef de naamval en getal van het zelfst. nw. τὰ θηρία",
            answer: "acc mev",
        },
        {
            id: 67,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινός",
            answer: "nom enk m",
        },
        {
            id: 68,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινή",
            answer: "nom enk f",
        },
        {
            id: 69,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινόν",
            answer: "nom enk o",
        },
        {
            id: 70,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινοῦ",
            answer: "gen enk m",
        },
        {
            id: 71,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινῆς",
            answer: "gen enk f",
        },
        {
            id: 72,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινοῦ",
            answer: "gen enk o",
        },
        {
            id: 73,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινόν",
            answer: "acc enk m",
        },
        {
            id: 74,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινήν",
            answer: "acc enk f",
        },
        {
            id: 75,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινόν",
            answer: "acc enk o",
        },
        {
            id: 76,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινοί",
            answer: "nom mev m",
        },
        {
            id: 77,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δειναί",
            answer: "nom mev f",
        },
        {
            id: 78,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινά",
            answer: "nom mev o",
        },
        {
            id: 79,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινῶν",
            answer: "gen mev o",
        },
        {
            id: 80,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινῶν",
            answer: "gen mev f",
        },
        {
            id: 81,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινῶν",
            answer: "gen mev o",
        },
        {
            id: 82,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινούς",
            answer: "acc mev m",
        },
        {
            id: 83,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινάς",
            answer: "acc mev f",
        },
        {
            id: 84,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. δεινά",
            answer: "acc mev o",
        },
        {
            id: 85,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρός",
            answer: "nom enk m",
        },
        {
            id: 86,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρά",
            answer: "nom enk f",
        },
        {
            id: 87,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρόν",
            answer: "nom enk o",
        },
        {
            id: 88,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακροῦ",
            answer: "gen enk m",
        },
        {
            id: 89,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρᾶς",
            answer: "gen enk f",
        },
        {
            id: 90,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακροῦ",
            answer: "gen enk o",
        },
        {
            id: 91,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρόν",
            answer: "acc enk m",
        },
        {
            id: 92,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακράν",
            answer: "acc enk f",
        },
        {
            id: 93,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρόν",
            answer: "acc enk o",
        },
        {
            id: 94,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακροί",
            answer: "nom mev m",
        },
        {
            id: 95,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακραί",
            answer: "nom mev f",
        },
        {
            id: 96,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρά",
            answer: "nom mev o",
        },
        {
            id: 97,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρῶν",
            answer: "gen mev m",
        },
        {
            id: 98,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρῶν",
            answer: "gen mev f",
        },
        {
            id: 99,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρῶν",
            answer: "gen mev o",
        },
        {
            id: 100,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρούς",
            answer: "acc mev m",
        },
        {
            id: 101,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακράς",
            answer: "acc mev f",
        },
        {
            id: 102,
            question:
                "geef de naamva, het getal, en het geslacht van het bijv. nw. μακρά",
            answer: "acc mev o",
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

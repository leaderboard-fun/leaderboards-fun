// Countdown Timer
let countdownDuration = 3 * 60; // 3 minutes in seconds
const timerElement = document.getElementById('timer');

function updateTimer() {
    const minutes = Math.floor(countdownDuration / 60);
    const seconds = countdownDuration % 60;
    timerElement.textContent = `${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')}`;
    if (countdownDuration > 0) {
        countdownDuration--;
        setTimeout(updateTimer, 1000);
    }
}

updateTimer();

// Increment Points
let points = 0;

function incrementPoints() {
    points++;
    updateLeaderboard();
}

function updateLeaderboard() {
    const leaderboardList = document.getElementById('leaderboard-list');
    const listItem = document.createElement('li');
    listItem.textContent = `User ${points} - ${points} Points`;
    leaderboardList.appendChild(listItem);
}

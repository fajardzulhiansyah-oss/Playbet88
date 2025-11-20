<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>PlayBet Arena</title>

<!-- TailwindCSS CDN -->
<script src="https://cdn.tailwindcss.com"></script>

<style>
    body {
        font-family: 'Montserrat', sans-serif;
    }
</style>
</head>

<body class="bg-blue-900 text-white">

<!-- LOGIN SCREEN -->
<div id="loginScreen" class="h-screen flex flex-col justify-center items-center">
    <h1 class="text-3xl font-bold mb-4">PlayBet Arena</h1>
    <p class="mb-2">Masukkan username Anda</p>

    <input id="usernameInput" 
        class="p-3 rounded text-black w-64 text-center" 
        type="text" placeholder="username..." />

    <button onclick="saveUsername()"
        class="mt-4 bg-blue-600 px-6 py-2 rounded font-bold">
        Masuk
    </button>
</div>

<!-- MAIN PAGE -->
<div id="mainPage" class="hidden p-6">

    <h1 class="text-3xl font-bold mb-4">Selamat datang, 
        <span id="displayUser" class="text-yellow-300"></span>!
    </h1>

    <p class="opacity-80 mb-6">Anda berada di PlayBet Arena — platform demo permainan digital.</p>

    <div class="bg-blue-700 p-4 rounded-lg shadow-lg">
        <h2 class="text-xl font-semibold mb-2">Menu</h2>
        <ul class="space-y-2">
            <li class="bg-blue-500 p-3 rounded">🎮 Game Slot Demo</li>
            <li class="bg-blue-500 p-3 rounded">⚽ Sport Virtual</li>
            <li class="bg-blue-500 p-3 rounded">🎲 Casino Mini</li>
        </ul>
    </div>

</div>

<script>
    // Load username if already saved
    const savedUser = localStorage.getItem("pba_username");

    if (savedUser) {
        document.getElementById("loginScreen").classList.add("hidden");
        document.getElementById("mainPage").classList.remove("hidden");
        document.getElementById("displayUser").innerText = savedUser;
    }

    // Save username
    function saveUsername() {
        const user = document.getElementById("usernameInput").value.trim();
        if (!user) return alert("Username tidak boleh kosong!");

        localStorage.setItem("pba_username", user);

        document.getElementById("loginScreen").classList.add("hidden");
        document.getElementById("mainPage").classList.remove("hidden");

        document.getElementById("displayUser").innerText = user;
    }
</script>

</body>
</html>

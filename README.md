<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Succesx1783 Team</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
<style>
  body {
    font-family: 'Orbitron', sans-serif;
    margin: 0;
    color: #fff;
    background-image: url('https://up-pic.com/images/2025/10/24/20250913180227_1-1.1.png');
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
  }
  .overlay {
    background-color: rgba(0, 0, 0, 0.6);
    min-height: 100vh;
    padding: 40px 20px;
    text-align: center;
  }
  .title-image {
    width: 400px;
    max-width: 90%;
    height: auto;
    margin: 0 auto 20px auto;
    display: block;
  }
  .search-box { margin: 20px 0; }
  .search-box input {
    padding: 12px 20px;
    font-size: 1em;
    width: 300px;
    max-width: 90%;
    border-radius: 25px;
    border: 2px solid #7289da;
    outline: none;
    background-color: rgba(255,255,255,0.1);
    color: #fff;
    transition: all 0.3s ease;
    box-shadow: 0 0 10px rgba(114,137,218,0.5);
  }
  .search-box input::placeholder { color: #ccc; }
  .search-box input:focus {
    border-color: #00ff22;
    background-color: rgba(255,255,255,0.2);
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.7);
  }
  .members, .leaders {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    margin-top: 20px;
  }
  .member-card {
    background-color: rgba(44, 44, 74, 0.8);
    padding: 15px;
    border-radius: 10px;
    width: 180px;
    text-align: center;
    transition: transform 0.2s;
  }
  .member-card:hover { transform: translateY(-5px); }
  .member-card img { border-radius: 50%; width: 100px; height: 100px; margin-bottom: 10px; }
  .member-card a { display: inline-block; margin-top: 8px; color: #7289da; text-decoration: none; font-weight: bold; }
  .member-card a:hover { text-decoration: underline; }
  .member-role { font-size: 0.9em; color: #000000; margin-bottom: 5px; font-weight: bold; }
  .discord-btn {
    margin-top: 30px;
    background-color: #7289da;
    color: #fff;
    border: none;
    padding: 12px 25px;
    border-radius: 8px;
    font-size: 1.1em;
    cursor: pointer;
    text-decoration: none;
  }
  .discord-btn:hover { background-color: #5b6eae; }
</style>
</head>
<body>
<div class="overlay">
  <img src="https://up-pic.com/images/2025/10/24/SUCCESS.1.png" alt="Succesx1783 Team" class="title-image">

  <h2>Leader</h2>
  <div class="leaders" id="leaderContainer"></div>

  <div class="search-box">
    <input type="text" id="searchInput" placeholder="ค้นหาสมาชิก...">
  </div>

  <h2>Members</h2>
  <div class="members" id="membersContainer"></div>

  <a href="https://discord.gg/mPFVGBXk" target="_blank" class="discord-btn">Join Discord</a>
</div>

<script>
const members = [
  { name: "Copper Winterfell", role: "Leader", avatar: "https://up-pic.com/images/2025/10/24/564625725_122100022419073985_3585383388920527768_n.jpg", facebook: "https://www.facebook.com/copperwinterfell" },
  { name: "Nxne Vincere", role: "Leader", avatar: "", facebook: "https://www.facebook.com/profile.php?id=61582453533435" },
  { name: "Nxne Vincere 2", role: "Leader", avatar: "", facebook: "#" },
  { name: "Nxne Vincere 3", role: "Leader", avatar: "", facebook: "#" },
  { name: "Nxne Vincere 4", role: "Leader", avatar: "", facebook: "#" },
  { name: "GG", role: "members", avatar: "", facebook: "https://www.facebook.com/profile.php?id=61573593144071" },
  { name: "ChinJi Vongolay", role: "Leader", avatar: "", facebook: "https://www.facebook.com/profile.php?id=61576906906228" }
];


const leaderContainer = document.getElementById("leaderContainer");
const membersContainer = document.getElementById("membersContainer");
const searchInput = document.getElementById("searchInput");

function renderMembers(filter = "") {
  leaderContainer.innerHTML = "";
  membersContainer.innerHTML = "";

  const filtered = members.filter(m => m.name.toLowerCase().includes(filter.toLowerCase()));
  const leaders = filtered.filter(m => m.role.toLowerCase() === "leader");
  const others = filtered.filter(m => m.role.toLowerCase() !== "leader");

  // Render Leaders (ตรงกลาง)
  leaders.forEach(member => {
    const card = document.createElement("div");
    card.className = "member-card";
    card.innerHTML = `
      
      <img src="${member.avatar || 'https://via.placeholder.com/100'}" alt="${member.name}">
      <h3>${member.name}</h3>
      <a href="${member.facebook}" target="_blank">Facebook</a>
    `;
    leaderContainer.appendChild(card);
  });

  // Render Members
  others.forEach(member => {
    const card = document.createElement("div");
    card.className = "member-card";
    card.innerHTML = `
      
      <img src="${member.avatar || 'https://via.placeholder.com/100'}" alt="${member.name}">
      <h3>${member.name}</h3>
      <a href="${member.facebook}" target="_blank">Facebook</a>
    `;
    membersContainer.appendChild(card);
  });
}

// เรียกครั้งแรก
renderMembers();

// ค้นหาแบบ realtime
searchInput.addEventListener("input", (e) => renderMembers(e.target.value));
</script>
</body>
</html>

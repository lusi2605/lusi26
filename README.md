<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>My APK Store - Android Apps</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,Helvetica,sans-serif;
}

body{
    background:#f5f7fa;
    color:#202124;
}

/* HEADER */
.header{
    background:linear-gradient(135deg,#16a34a,#0f8a3d);
    color:white;
    padding:22px 16px 28px;
}

.header-top{
    max-width:1050px;
    margin:auto;
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.logo{
    font-size:25px;
    font-weight:800;
}

.menu{
    font-size:25px;
}

.hero{
    max-width:1050px;
    margin:25px auto 0;
}

.hero h1{
    font-size:30px;
    margin-bottom:8px;
}

.hero p{
    font-size:15px;
    opacity:.9;
}

/* SEARCH */
.search-area{
    max-width:1050px;
    margin:-22px auto 0;
    padding:0 15px;
}

.search{
    background:white;
    border-radius:14px;
    box-shadow:0 5px 20px rgba(0,0,0,.12);
    display:flex;
    align-items:center;
    padding:5px;
}

.search span{
    font-size:23px;
    padding:0 10px;
}

.search input{
    border:0;
    outline:0;
    width:100%;
    padding:15px 8px;
    font-size:16px;
}

/* MAIN */
.container{
    max-width:1050px;
    margin:auto;
    padding:20px 15px 50px;
}

.section-title{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin:25px 0 15px;
}

.section-title h2{
    font-size:22px;
}

.section-title a{
    color:#16a34a;
    text-decoration:none;
    font-size:14px;
    font-weight:bold;
}

/* CATEGORIES */
.categories{
    display:flex;
    gap:10px;
    overflow-x:auto;
    padding-bottom:5px;
}

.categories::-webkit-scrollbar{
    display:none;
}

.category{
    background:white;
    border:1px solid #e5e7eb;
    padding:10px 17px;
    border-radius:25px;
    white-space:nowrap;
    cursor:pointer;
    font-size:14px;
}

.category.active{
    background:#16a34a;
    color:white;
    border-color:#16a34a;
}

/* APP GRID */
.apps{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:15px;
}

.app-card{
    background:white;
    border-radius:16px;
    padding:16px;
    border:1px solid #e8eaed;
    transition:.2s;
}

.app-card:hover{
    transform:translateY(-2px);
    box-shadow:0 7px 20px rgba(0,0,0,.08);
}

.app-info{
    display:flex;
    gap:13px;
    align-items:center;
}

.icon{
    width:65px;
    height:65px;
    border-radius:16px;
    background:#eef2f3;
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:31px;
    flex-shrink:0;
}

.app-name{
    font-size:17px;
    font-weight:700;
    margin-bottom:5px;
}

.app-meta{
    color:#777;
    font-size:13px;
    line-height:1.5;
}

.download{
    display:block;
    text-align:center;
    background:#16a34a;
    color:white;
    text-decoration:none;
    font-weight:bold;
    padding:12px;
    border-radius:9px;
    margin-top:15px;
}

.download:hover{
    background:#12823b;
}

/* FEATURE BOX */
.feature{
    background:white;
    border-radius:16px;
    padding:18px;
    border:1px solid #e5e7eb;
    margin-top:15px;
}

.feature-inner{
    display:flex;
    gap:15px;
    align-items:center;
}

.feature-icon{
    width:75px;
    height:75px;
    background:#eef2f3;
    border-radius:18px;
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:36px;
}

.feature h3{
    font-size:19px;
    margin-bottom:5px;
}

.feature p{
    color:#777;
    font-size:13px;
}

/* FOOTER */
footer{
    background:#111827;
    color:#cbd5e1;
    text-align:center;
    padding:30px 15px;
}

footer h3{
    color:white;
    margin-bottom:8px;
}

footer p{
    font-size:13px;
    margin:5px 0;
}

/* MOBILE */
@media(max-width:650px){

    .apps{
        grid-template-columns:1fr;
    }

    .hero h1{
        font-size:25px;
    }

    .logo{
        font-size:21px;
    }

    .container{
        padding-top:15px;
    }
}

@media(min-width:900px){

    .apps{
        grid-template-columns:repeat(3,1fr);
    }
}
</style>
</head>

<body>

<!-- HEADER -->

<header class="header">

    <div class="header-top">

        <div class="logo">
            📱 My APK Store
        </div>

        <div class="menu">
            ☰
        </div>

    </div>

    <div class="hero">

        <h1>Download Android Apps</h1>

        <p>
            Discover useful apps, games and tools for Android.
        </p>

    </div>

</header>


<!-- SEARCH -->

<div class="search-area">

    <div class="search">

        <span>🔍</span>

        <input
            type="text"
            id="search"
            placeholder="Search apps..."
            onkeyup="searchApps()"
        >

    </div>

</div>


<main class="container">


<!-- CATEGORIES -->

<div class="section-title">

    <h2>Categories</h2>

</div>

<div class="categories">

    <div class="category active" onclick="filterCategory('all',this)">
        All
    </div>

    <div class="category" onclick="filterCategory('games',this)">
        🎮 Games
    </div>

    <div class="category" onclick="filterCategory('tools',this)">
        🛠️ Tools
    </div>

    <div class="category" onclick="filterCategory('education',this)">
        📚 Education
    </div>

    <div class="category" onclick="filterCategory('entertainment',this)">
        🎬 Entertainment
    </div>

</div>


<!-- FEATURED -->

<div class="section-title">

    <h2>Featured App</h2>

</div>

<div class="feature">

    <div class="feature-inner">

        <div class="feature-icon">
            ⭐
        </div>

        <div>

            <h3>Featured App</h3>

            <p>
                A sample application for your APK directory.
            </p>

        </div>

    </div>

    <a class="download" href="#" onclick="demoDownload()">
        View App
    </a>

</div>


<!-- POPULAR APPS -->

<div class="section-title">

    <h2>Popular Apps</h2>

    <a href="#">View All</a>

</div>


<div class="apps" id="appList">


    <!-- APP 1 -->

    <div class="app-card" data-category="tools">

        <div class="app-info">

            <div class="icon">
                📱
            </div>

            <div>

                <div class="app-name">
                    Sample App
                </div>

                <div class="app-meta">
                    Version 1.0<br>
                    25 MB • Tools
                </div>

            </div>

        </div>

        <a
            class="download"
            href="#"
            onclick="demoDownload()"
        >
            Download APK
        </a>

    </div>


    <!-- APP 2 -->

    <div class="app-card" data-category="games">

        <div class="app-info">

            <div class="icon">
                🎮
            </div>

            <div>

                <div class="app-name">
                    Sample Game
                </div>

                <div class="app-meta">
                    Version 2.0<br>
                    80 MB • Games
                </div>

            </div>

        </div>

        <a
            class="download"
            href="#"
            onclick="demoDownload()"
        >
            Download APK
        </a>

    </div>


    <!-- APP 3 -->

    <div class="app-card" data-category="education">

        <div class="app-info">

            <div class="icon">
                📚
            </div>

            <div>

                <div class="app-name">
                    Learning App
                </div>

                <div class="app-meta">
                    Version 1.5<br>
                    32 MB • Education
                </div>

            </div>

        </div>

        <a
            class="download"
            href="#"
            onclick="demoDownload()"
        >
            Download APK
        </a>

    </div>


    <!-- APP 4 -->

    <div class="app-card" data-category="entertainment">

        <div class="app-info">

            <div class="icon">
                🎬
            </div>

            <div>

                <div class="app-name">
                    Media App
                </div>

                <div class="app-meta">
                    Version 3.0<br>
                    45 MB • Entertainment
                </div>

            </div>

        </div>

        <a
            class="download"
            href="#"
            onclick="demoDownload()"
        >
            Download APK
        </a>

    </div>


</div>

</main>


<!-- FOOTER -->

<footer>

    <h3>📱 My APK Store</h3>

    <p>
        Android application directory
    </p>

    <p>
        © 2026 My APK Store
    </p>

</footer>


<script>

/* SEARCH */

function searchApps(){

    let search =
        document.getElementById("search")
        .value
        .toLowerCase();

    let cards =
        document.querySelectorAll(".app-card");

    cards.forEach(function(card){

        let name =
            card.querySelector(".app-name")
            .innerText
            .toLowerCase();

        if(name.includes(search)){
            card.style.display="";
        }
        else{
            card.style.display="none";
        }

    });

}


/* CATEGORY FILTER */

function filterCategory(category,button){

    let buttons =
        document.querySelectorAll(".category");

    buttons.forEach(function(btn){
        btn.classList.remove("active");
    });

    button.classList.add("active");

    let cards =
        document.querySelectorAll(".app-card");

    cards.forEach(function(card){

        if(
            category === "all" ||
            card.dataset.category === category
        ){

            card.style.display="";

        }else{

            card.style.display="none";

        }

    });

}


/* DEMO DOWNLOAD */

function demoDownload(){

    alert(
        "Demo button. Add an authorized APK download link here."
    );

    return false;
}

</script>

</body>
</html># lusi26

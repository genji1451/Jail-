<html>

<head>
    <title>Jailbirds</title>
</head>

<body>
    <div id="jailbirds">
        <div id="text">Тюряга:</div>
    </div>
    <script>
        let jailed = ""; // Add hero names separated by commas inside of the quotes for manual entry
        const jb = document.querySelector("#jailbirds");
        const getJailed = async () => {
            const heroesPage = await (await fetch("https://cors-anywhere.herokuapp.com/https://www.under.tools", { headers: { "X-Requested-With": "XMLHttpRequest" } })).text()
            const em = document.createElement("DIV");
            em.innerHTML = heroesPage;
            return Array.from(em.querySelectorAll(".hero div b")).map(x => x.innerText.toLowerCase());
        }
        const getAllHeroes = async () => {
            const heroesPage = await (await fetch("https://cors-anywhere.herokuapp.com/https://dotaunderlords.gamepedia.com/Category:Hero_mini_icons", { headers: { "X-Requested-With": "XMLHttpRequest" } })).text()
            const em = document.createElement("DIV");
            em.innerHTML = heroesPage;
            const allUn = Array.from(em.querySelectorAll(".image img"));
            all = {};
            allUn.forEach(x => all[x.alt.replace(" mini icon.png", "").toLowerCase()] = x.src);
            return all;
        }
        (async () => {
            jailed = jailed.length ? jailed.split(',').map(x => x.trim().toLowerCase()) : await getJailed();
            const all = await getAllHeroes();
            const finalImages = jailed.map(x => all[x]).filter(x => x);
            finalImages.forEach(x => jb.innerHTML += `<img src='${x}' height=32 width=32></img>`);
        })();
    </script>
</body>
<style>
    img {
        margin-right: 4px;
    }

    #jailbirds {
        display: flex;
        align-items: center;
    }

    #text {
        font-size: 25px;
        color: white;
        margin-right: 4px;
    }
</style>

</html>

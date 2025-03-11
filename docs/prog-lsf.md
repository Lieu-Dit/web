# <span class="middle img-3rem">![](assets/lsf.png)</span>Programmes en Langue des signes française (LSF)

## Mars 2025
<ul id="lsf-03-25"></ul>

<link href="stylesheets/video-js.css" rel="stylesheet" />
<link href="stylesheets/extra.video-js.css" rel="stylesheet" />

<video
    id="my-video"
    class="video-js"
    controls
    muted
    preload="auto"
    width="600px"
    height="400px"
  >
    <p class="vjs-no-js">
      To view this video please enable JavaScript, and consider upgrading to a
      web browser that
      <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
    </p>
  </video>
 
## Remerciements

Merci à Carole et Fabienne pour les vidéos LSF du programme !


<script src="https://vjs.zencdn.net/8.16.1/video.min.js"></script>

<script>
    document.getElementsByClassName("vjs-no-js")[0].style.display = "none";
    const baseUrl = "https://cloud.laucarre.com/s/LD-LSF-prog/download?path=%2Fmars2025&files="
    
    const player = videojs("my-video", {responsive: true});

    let playlist = [
    {
        title: "Jeudi 13 mars",
        url: "01 Jeudi 13 mars.mp4",
    },
    {
        title: "Samedi 22 mars",
        url: "02 Samedi 22 mars.mp4",
    },
    {
        title: "Mercredi 26 mars",
        url: "03 Mercredi 26 mars.mp4",
    },
    {
        title: "Jeudi 27 mars",
        url: "04 Jeudi 27 mars.mp4",
    },
    {
        title: "Samedi 29 mars",
        url: "05 Samedi 29 mars.mp4",
    },
    {
        title: "Mercredi 19, 26 mars",
        url: "06 Mercredi 19, 26 mars.mp4",
    }
    ];

    function populate_list (data, elemId) {
        elem = document.getElementById(elemId)
        let i = 0;
        for (let item of data) {
            let cls = i==0 ? " active" : ""
            i++;
            elem.insertAdjacentHTML('beforeend', 
            `<li><button class="prog-button` + cls +
            `" onclick="doo(this,'` + 
            baseUrl + item.url+`')">` + 
            item.title+'</button></li>');
        }
    }
    function populate_playlist () {
        populate_list(playlist, "lsf-03-25");
    }
    function doo (e,url) {
        player.pause()
        player.src(url)
        // player.load()
        player.play()
        // add class "active" to item
        if (e != null) {
            elem = document.getElementById("lsf-03-25")
            for (let b of elem.children) {
                b.firstElementChild.classList.remove("active")
            }
            e.classList.add("active")
            }
    }
    populate_playlist();
    doo(null, baseUrl + playlist[0].url)
</script>
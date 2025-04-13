# <span class="middle img-3rem">![](assets/lsf.png)</span>Programmes en Langue des signes française (LSF)

## Avril 2025
<ul class="playlist_lsf" id="lsf-04-25"></ul>

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

## Programmes précédents

### Mars
<ul class="playlist_lsf" id="lsf-03-25"></ul>

<script src="https://vjs.zencdn.net/8.16.1/video.min.js"></script>
<script src="programme/programme-lsf.js"></script>
<script>
    document.getElementsByClassName("vjs-no-js")[0].style.display = "none";
<!--     const baseUrl = "https://cloud.laucarre.com/s/LD-LSF-prog/download?path=%2Fmars2025&files=" -->
    const player = videojs("my-video", {responsive: true, fluid: true});
    function populate_list (data, elemId, baseUrl) {
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
    function doo (e,url) {
        player.pause()
        player.src(url)
        // player.load()
        player.play()
        // add class "active" to item
        if (e != null) {
            console.log("pou")
            elems = document.getElementsByClassName("playlist_lsf")
            console.log(elems)
            for (let elem of elems) {
                for (let b of elem.children) {
                    b.firstElementChild.classList.remove("active");
                }
                e.classList.add("active");
            }
        }
    }
    populate_list(playlist_04_2025, "lsf-04-25", "https://cloud.laucarre.com/s/LD-LSF-prog/download?path=%2Favril2025&files=");
    populate_list(playlist_03_2025, "lsf-03-25", "https://cloud.laucarre.com/s/LD-LSF-prog/download?path=%2Fmars2025&files=");
    doo(null, "https://cloud.laucarre.com/s/LD-LSF-prog/download?path=%2Favril2025&files=" + playlist_04_2025[0].url)
</script>

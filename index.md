#### INTRODUCTION

_We present Okutama-Action, a new video dataset for aerial view concurrent human action detection. It consists of 43 minute-long fully-annotated sequences with 12 action classes. Okutama-Action features many challenges missing in current datasets, including dynamic transition of actions, significant changes in scale and aspect ratio, abrupt camera movement, as well as multi-labeled actors. As a result, our dataset is more challenging than existing ones, and will help push the field forward to enable real-world applications._

---

#### HIGHLIGHTS
* An aerial view dataset that contains representative samples of actions in real-world airborne scenarios
* Dynamic transition of actions where, in each video, up to 9 actors sequentially perform a diverse set of actions
* A real-world challenge of multi-labeled actors where an actor performs more than one action at the same time.
* A significant increase compared to previous datasets, in number of actors and concurrent actions (up to 10 actions/actors), as well as video resolution (3840x2160) and sequence length (one minute on average).
* Dataset can be used for multiple tasks: 1- pedestrian detection 2- spatio-temporal action detection 3- (under development) multi-human tracking.

---

#### CITATION
If you find this dataset useful, please cite the following paper:
<img style="float: left; margin-top:5px; width:30%" src="images/teaser.png" alt="arXiv">

Okutama-Action: An Aerial View Video Dataset for Concurrent Human Action Detection
                    <br>
                    <a href="http://barekatain.me/" target="_blank">M. Barekatain</a>,
                    <a href="https://miquelmarti.github.io" target="_blank">M. Martí</a>,
                    <a href="https://www.linkedin.com/in/hsueh-fu-shih-621616b5/" target="_blank">H. Shih</a>,
                    <a href="https://samuelmurray.github.io/" target="_blank">S. Murray</a>,
                    <a href="http://knakayama.com/" target="_blank">K. Nakayama</a>,
                    <a href="http://ymatsuo.com/" target="_blank">Y. Matsuo</a>, and
                    <a href="http://research.nii.ac.jp/~prendinger/" target="_blank">H. Prendinger</a>
                    <br>
                    The IEEE Conference on Computer Vision and Pattern Recognition (CVPR) Workshops, 2017, pp. 28-35
                                       <a href="https://arxiv.org/abs/1706.03038">arXiv:1706.03038</a><br>
                    [<a href="https://arxiv.org/pdf/1706.03038.pdf" target="_blank">PDF</a>]

---

#### ANNOTATION EXAMPLES (downscaled to 720p)

<iframe width="853" height="480" src="https://www.youtube.com/embed/ZXJCN9zrXPM?rel=0" frameborder="0" allowfullscreen></iframe>

---

#### ACTION CATEGORIES
<img style="margin-top:5px; width:60%" src="images/actions.jpg" alt="arXiv">

---

#### DATASET DOWNLOAD

**Video Names**: each video name consists of 3 integers separated by dots. The
definition of these integers from left to right are:


1.   Drone number. Each scenario, with the exception of one, was captured using 2 drones (of different configuration) at the same time.
2.   Part of the day. "1" indicates *morning* and "2" indicates *noon*.
3.   Scenario number.

Hence, the pair of videos with the same last two integers are the same scenario with different drones configuration.

**Labels**:  Each line contains 10+ columns, separated by spaces. The
definition of these columns are:

1.   Track ID. *please check the below part for details*
2.   xmin. The top left x-coordinate of the bounding box.
3.   ymin. The top left y-coordinate of the bounding box.
4.   xmax. The bottom right x-coordinate of the bounding box.
5.   ymax. The bottom right y-coordinate of the bounding box.
6.   frame. The frame that this annotation represents.
7.   lost. If 1, the annotation is outside of the view screen.
8.   occluded. If 1, the annotation is occluded.
9.   generated. If 1, the annotation was automatically interpolated.
10.  label. The label for this annotation, enclosed in quotation marks. This field is always "Person".
11. (+)  actions. Each column after this is an action.


There are three label files for each videos: 1- MultiActionLabels: labels for *multi-*action detection task. 2- SingleActionLabels: labels for *single*-action detection task which has been created from the *multi*-action detection labels (for more details please refer to our publication). In both of these files, all rows with the same "Track ID" belong to the same person for 180 frames. Then the person gets a new ID for the next 180 frames. 3- SingleActionTrackingLabels: same labels as 2, but here the ID's are consistent. This means that each person has a unique ID in the video but will get a new one if he/she is absent for more than 90 frames.

For pedestrian detection task, the columns describing the actions should be ignored.

**Sample (one 4K video and labels)** [link (540 MB)](https://okutama-action.s3.eu-central-1.amazonaws.com/Sample.zip)

Full dataset:

**Training set (1280x720 frames & labels)** [link (5.3 GB)](https://okutama-action.s3.eu-central-1.amazonaws.com/TrainSetFrames.zip)

**Test set (1280x720 frames & labels)**
[link (1.5 GB)](https://okutama-action.s3.eu-central-1.amazonaws.com/TestSetFrames.zip)

**Training set (4K videos & labels)** [link (14 GB)](https://okutama-action.s3.eu-central-1.amazonaws.com/TrainSetVideos.zip)

**Test set (4K videos & labels)**
[link (4 GB)](https://okutama-action.s3.eu-central-1.amazonaws.com/TestSetVideos.zip)

---

#### MODELS DOWNLOAD
**Final trained Caffe models** [link](https://okutama-action.s3.eu-central-1.amazonaws.com/FinalModels.zip).

---

#### UPDATES
- We will soon release the metadata for each video sequence, namely camera angle, speed and altitude of the drones.
- Test set labels are now available.
- Links have been updated, now hosted on AWS for easier download.

---

#### DEVELOPERS TEAM
The creation of this dataset was supported by [Prendinger Lab](http://research.nii.ac.jp/~prendinger/) at the [National Institute of Informatics](http://nii.ac.jp/en/), Tokyo, Japan. We are also grateful for financial support and the provision of GPU power from [Matsuo Lab](http://weblab.t.u-tokyo.ac.jp) at the [University of Tokyo](http://www.u-tokyo.ac.jp/en/).

<dl>
<head>
<style>
 .wrapper--team {
  margin: 0;
  padding: 2rem 1rem;
  background-color: #E9E7D0;
}

.l-container {
  margin: 0 auto;
}

@media screen and (min-width: 64em) {
  .l-container {
    max-width: 64rem;
  }
}
@media screen and (min-width: 75em) {
  .l-container {
    max-width: 75rem;
  }
}
.team-grid {
  margin: 0;
  text-align: center;
  *zoom: 1;
}
.team-grid:before, .team-grid:after {
  content: " ";
  display: table;
}
.team-grid:after {
  clear: both;
}

.team-grid__member {
  font-family: ff-tisa-web-pro;
  max-width: 100%;
  padding: 0.5rem;
  margin: 0 0 0.5rem;
  display: inline-block;
  float: none;
  width: 100%;
  text-align: center;
  box-sizing: border-box;
}

@media screen and (min-width: 28em) {
  .team-grid__member {
    width: 49%;
    max-width: none;
  }
}
@media screen and (min-width: 42em) {
  .team-grid__member {
    width: 32.5%;
  }
}
@media screen and (min-width: 62em) {
  .team-grid__member {
    width: 19.45%;
  }
}
.team-grid__member {
  position: relative;
  overflow: hidden;
}

.team-grid__member img {
  width: 100%;
  height: auto;
  border: 8px solid #fff;
  box-sizing: border-box;
  display: block;
}

.member__info {
  color: #fff;
  height: auto;
  width: auto;
  opacity: 0;
  position: absolute;
  top: 1rem;
  left: 1rem;
  right: 1rem;
  bottom: 1rem;
  background: rgba(0, 0, 0, 0.85);
  backface-visibility: hidden;
  transition: opacity 0.4s ease-in-out;
}

.member__name {
  color: #D9BC55;
  font-size: 1rem;
  letter-spacing: 1px;
  line-height: 1.2rem;
  margin-bottom: 0;
  padding: 0 12px;
}

.member__title {
  margin-bottom: 0.75rem;
  font-size: 0.8rem;
  font-weight: normal;
  line-height: 1rem;
  padding: 0 1.5rem;
}

a.member__link {
  background: #D68D2C;
  color: #FFF;
  border-radius: 2px;
  border: 0;
  cursor: pointer;
  display: inline-block;
  font-size: 16px;
  padding: 8px;
  text-align: center;
  text-decoration: none;
}

.team-grid__member:hover .member__info {
  opacity: 1;
}

.member__info:before {
  content: '';
  display: inline-block;
  height: 100%;
  vertical-align: middle;
  margin-right: -0.25em;
}

.center-vert-content {
  display: inline-block;
  vertical-align: middle;
}
</style>
</head>

<body>
<script type="text/javascript" src="//use.typekit.net/npe3lft.js"></script>
<script type="text/javascript">try{Typekit.load();}catch(e){}</script>

<div class="wrapper--team">
<div class="l-container">

  <div class="team-grid">

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h5 class="member__name">Mohammadamin Barekatain</h5>
          <p class="member__title">Technical University of Munich</p>
          <a class="member__link" href="http://barekatain.me/">Read More</a>
        </div>
      </div>
      <img src="images/amin.jpg" alt="Mohammadamin Barekatain" height="300" width="300">
    </div>

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h5 class="member__name"> Miquel Marti </h5>
          <p class="member__title">KTH Royal Institute of Technology</p>
          <a class="member__link" href="https://miquelmarti.github.io">Read More</a>
        </div>
      </div>
      <img src="images/miquel.jpg" alt="Miquel Marti" height="300" width="300">
    </div>

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h5 class="member__name">Hsueh-Fu Shih</h5>
          <p class="member__title">National Taiwan University</p>
          <a class="member__link" href="https://www.linkedin.com/in/hsueh-fu-shih-621616b5/">Read More</a>
        </div>
      </div>
      <img src="images/jeff.jpg" alt="Hsueh-Fu Shih" height="300" width="300">
    </div>

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h5 class="member__name">Samuel Murray</h5>
          <p class="member__title">KTH Royal Institute of Technology</p>
          <a class="member__link" href="https://samuelmurray.github.io/">Read More</a>
        </div>
      </div>
      <img src="images/samuel.png" alt="Samuel Murray" height="300" width="300">
    </div>

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h5 class="member__name">Helmut Prendinger</h5>
          <p class="member__title">National Institute of Informatics</p>
          <a class="member__link" href="http://research.nii.ac.jp/~prendinger/">Read More</a>
        </div>
      </div>
      <img src="images/prendinger.jpg" alt="Helmut Prendinger" height="300" width="300">
    </div>

</div>
</div>
</div>

</body>
</dl>

---

#### LICENSE

<dl>
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/3.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/">Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License</a>.
</dl>
**If you are interested in commercial usage you can contact us for further options.**

---

###### Contact : m.barekatain at tum dot de
###### Last update : 23/06/2018

<!-- Global Site Tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-106875508-1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments)};
  gtag('js', new Date());

  gtag('config', 'UA-106875508-1');
</script>

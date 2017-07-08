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
If you find this dataset useful, please cite the following paper
<img style="float: left; margin-top:5px; width:30%" src="images/teaser.png" alt="arXiv">

Okutama-Action: An Aerial View Video Dataset for Concurrent Human Action Detection
                    <br>
                    <a href="http://barekatain.me/" target="_blank">M. Barekatain</a>,
                    <a href="https://miquelmarti.github.io" target="_blank">M. Martí</a>,
                    <a href="https://www.linkedin.com/in/hsueh-fu-shih-621616b5/" target="_blank">H. Shih</a>,
                    <a href="https://www.linkedin.com/in/samuel-murray-6012545a" target="_blank">S. Murray</a>,
                    <a href="http://knakayama.com/" target="_blank">K. Nakayama</a>,
                    <a href="http://ymatsuo.com/" target="_blank">Y. Matsuo</a>, and
                    <a href="http://research.nii.ac.jp/~prendinger/" target="_blank">H. Prendinger</a>
                    <br>
                                       <i>arXiv:1706.03038, 2017</i><br>
                    [<a href="https://arxiv.org/abs/1706.03038" target="_blank">PDF</a>]

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

1.   Track ID. *All rows with the same ID belong to the same person for 180 frames. Then the person gets a new idea for the next 180 frames. We will soon release an update to make the IDs consistant.*
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


There are two label files for each video; one for *single*-action detection and one for *multi-*action detection. Note that labels for *single*-action detection has been created from the *multi*-action detection labels (for more details please refer to our publication). For pedestrian detection task, the columns describing the actions should be ignored.

**Training set (videos & labels)** [link](https://drive.google.com/drive/folders/0B6O3GZcCIFuDaUs4dG1HWWEyUWM?usp=sharing).

---

#### MODELS DOWNLOAD
**Final trained Caffe models** [link](https://drive.google.com/drive/folders/0BydaU2Imk1zjSUpCdFpmbmtEeHc?usp=sharing).

---

#### UPDATES
We will soon release the metadata for each video sequence, namely camera angle, speed and altitude of the drones.

---

#### ABOUT

The creation of this dataset was supported by [Prendinger Lab](http://research.nii.ac.jp/~prendinger/) at the [National Institute of Informatics](http://nii.ac.jp/en/), Tokyo, Japan.

###### Contact : m.barekatain at tum dot de

###### Last update : 07/07/2017

---
#### DEVELOPERS TEAM
<dl>
<style>
$tisa: ff-tisa-web-pro;

$burlywood: #D9BC55;
$title-on-black: $burlywood;

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

  &:before, &:after {
    content: " ";
    display: table;
  }

  &:after {
    clear: both;
  }

}

.team-grid__member {
  font-family: $tisa;

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

//////////////////////
// MODULE GRID
//////////////////////
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
  color: $title-on-black;
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

// FIX THE TOUCH METHOD
//.no-touch .team-grid__member:hover .member__info,
//.team-grid__member.cs-hover .member__info {
//  opacity: 1;
//}

.team-grid__member:hover .member__info {
  opacity: 1;
}


// ----- Middle Alignment Vertical ----- //
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

<body>
<script type="text/javascript" src="//use.typekit.net/npe3lft.js"></script>
<script type="text/javascript">try{Typekit.load();}catch(e){}</script>

<div class="wrapper--team">
<div class="l-container">

  <div class="team-grid">

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h3 class="member__name">Robert Finkel</h3>
          <p class="member__title">Rootmaster</p>
          <a class="member__link" href="javascript:void(0)">Read More</a>
        </div>
      </div>
      <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/3393/robert-finkel_2.jpg" alt="Robert Finkel">
    </div>

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h3 class="member__name">Randy Mosher</h3>
          <p class="member__title">Alchemist</p>
          <a class="member__link" href="javascript:void(0)">Read More</a>
        </div>
      </div>
      <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/3393/randy-mosher.jpg" alt="Randy Mosher">
    </div>

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h3 class="member__name">BJ Pichman</h3>
          <p class="member__title">Operations Manager</p>
          <a class="member__link" href="javascript:void(0)">Read More</a>
        </div>
      </div>
      <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/3393/mrch8596.jpg" alt="BJ Pichman">
    </div>

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h3 class="member__name">Jacqueline Armanetti</h3>
          <p class="member__title">Brand Ambassador</p>
          <a class="member__link" href="javascript:void(0)">Read More</a>
        </div>
      </div>
      <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/3393/jacqueline-armanetti.jpg" alt="Jacqueline Armanetti">
    </div>

    <div class="team-grid__member hover">
      <div class="member__info">
        <div class="center-vert-content">
          <h3 class="member__name">Romy Seth</h3>
          <p class="member__title">Analyst</p>
          <a class="member__link" href="javascript:void(0)">Read More</a>
        </div>
      </div>
      <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/3393/romy-seth.jpg" alt="Romy Seth">
    </div>

  </div>

</div>
</div>



</body>

</dl>

---
title: CMBC Fintech Problem
date: 2019-08-21
category: [project]
tags: [XGBoost, competition]
aside:
  toc: false
---

<html>
<head><meta charset="utf-8" />

<title>CMBC Fintech Problem 1-1</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">

/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  }
  div.output_wrapper {
    display: block;
    page-break-inside: avoid;
  }
  div.output {
    display: block;
    page-break-inside: avoid;
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Do some imports</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">matplotlib</span>
<span class="kn">from</span> <span class="nn">IPython.display</span> <span class="k">import</span> <span class="n">display</span>
<span class="kn">import</span> <span class="nn">datetime</span>

<span class="kn">import</span> <span class="nn">sys</span>
<span class="n">sys</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s2">&quot;D:/Edward/Documents/Assignments/Scripts/Python/generic&quot;</span><span class="p">)</span>
<span class="kn">from</span> <span class="nn">plots</span> <span class="k">import</span> <span class="n">SetFont</span> <span class="c1"># helps us fix some font problem for displaying Chinese characters</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>D:\Anaconda3\lib\site-packages\matplotlib\__init__.py:1405: UserWarning:
This call to matplotlib.use() has no effect because the backend has already
been chosen; matplotlib.use() must be called *before* pylab, matplotlib.pyplot,
or matplotlib.backends is imported for the first time.

  warnings.warn(_use_error_msg)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[64]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">excelsheet_X_train</span> <span class="o">=</span> <span class="s2">&quot;./data/X序列_train.xls&quot;</span>
<span class="n">excelsheet_y_train</span> <span class="o">=</span>  <span class="s2">&quot;./data/Y序列_train.xls&quot;</span>

<span class="c1"># Training data</span>
<span class="n">X_train_original</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="n">excelsheet_X_train</span><span class="p">,</span> <span class="s2">&quot;Sheet1&quot;</span><span class="p">,</span> <span class="n">skiprows</span><span class="o">=</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span>
<span class="n">y1_train</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="n">excelsheet_y_train</span><span class="p">,</span> <span class="s2">&quot;Y1&quot;</span><span class="p">,</span> <span class="n">header</span><span class="o">=</span><span class="kc">None</span><span class="p">)</span>
<span class="n">y2_train</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="n">excelsheet_y_train</span><span class="p">,</span> <span class="s2">&quot;Y2&quot;</span><span class="p">,</span> <span class="n">header</span><span class="o">=</span><span class="kc">None</span><span class="p">)</span>
<span class="n">y3_train</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="n">excelsheet_y_train</span><span class="p">,</span> <span class="s2">&quot;Y3&quot;</span><span class="p">,</span> <span class="n">header</span><span class="o">=</span><span class="kc">None</span><span class="p">)</span>

<span class="c1"># Test data</span>
<span class="n">excelsheet_X_train</span> <span class="o">=</span> <span class="s2">&quot;./data/X序列_test.xls&quot;</span>
<span class="n">X_test_original</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="n">excelsheet_X_train</span><span class="p">,</span> <span class="s2">&quot;Sheet1&quot;</span><span class="p">,</span> <span class="n">skiprows</span><span class="o">=</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[62]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">X_train_original</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[62]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>GDP:实际同比增长:全球</th>
      <th>美国:GDP:现价:环比折年率:季调</th>
      <th>欧元区:GDP平减指数:季调</th>
      <th>全球商品贸易量增长率:出口金额:全球</th>
      <th>工业增加值:当月同比</th>
      <th>工业增加值:累计同比</th>
      <th>固定资产投资完成额:累计同比</th>
      <th>房地产开发投资完成额:累计同比</th>
      <th>产量:发电量:当月同比</th>
      <th>产量:发电量:累计同比</th>
      <th>...</th>
      <th>市净率:中证200</th>
      <th>滚动市盈率(TTM):沪深两市</th>
      <th>滚动市盈率(TTM):深圳市场</th>
      <th>滚动市盈率(TTM):深市主板</th>
      <th>滚动市盈率(TTM):中小板</th>
      <th>滚动市盈率(TTM):创业板</th>
      <th>中债总指数</th>
      <th>中债国债总指数</th>
      <th>中债金融债券总指数</th>
      <th>中债信用债总指数</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>36.000000</td>
      <td>275.000000</td>
      <td>84.000000</td>
      <td>20.000000</td>
      <td>312.000000</td>
      <td>210.000000</td>
      <td>261.000000</td>
      <td>187.000000</td>
      <td>251.000000</td>
      <td>311.000000</td>
      <td>...</td>
      <td>3273.000000</td>
      <td>1136.000000</td>
      <td>1136.000000</td>
      <td>1136.000000</td>
      <td>1136.000000</td>
      <td>1136.000000</td>
      <td>3502.000000</td>
      <td>3502.000000</td>
      <td>3502.000000</td>
      <td>2248.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>3.517139</td>
      <td>6.588000</td>
      <td>92.173143</td>
      <td>5.100000</td>
      <td>12.758590</td>
      <td>12.716571</td>
      <td>24.687356</td>
      <td>24.162567</td>
      <td>8.636828</td>
      <td>9.025223</td>
      <td>...</td>
      <td>3.223309</td>
      <td>15.913327</td>
      <td>29.539789</td>
      <td>21.149058</td>
      <td>35.858248</td>
      <td>54.809419</td>
      <td>125.261976</td>
      <td>124.936082</td>
      <td>126.800902</td>
      <td>119.904897</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.248717</td>
      <td>4.746882</td>
      <td>9.065830</td>
      <td>5.374403</td>
      <td>5.479889</td>
      <td>4.431903</td>
      <td>11.468376</td>
      <td>9.269454</td>
      <td>6.915276</td>
      <td>5.479765</td>
      <td>...</td>
      <td>1.335584</td>
      <td>4.276788</td>
      <td>9.118093</td>
      <td>4.954066</td>
      <td>11.299075</td>
      <td>22.798515</td>
      <td>17.983413</td>
      <td>18.305711</td>
      <td>17.451678</td>
      <td>15.502401</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.013000</td>
      <td>-7.700000</td>
      <td>77.300000</td>
      <td>-12.000000</td>
      <td>-21.100000</td>
      <td>-2.930000</td>
      <td>5.500000</td>
      <td>1.000000</td>
      <td>-13.700000</td>
      <td>-11.800000</td>
      <td>...</td>
      <td>1.601100</td>
      <td>11.690000</td>
      <td>18.970000</td>
      <td>15.720000</td>
      <td>21.770000</td>
      <td>27.090000</td>
      <td>99.771300</td>
      <td>97.860100</td>
      <td>99.338200</td>
      <td>97.377500</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2.719000</td>
      <td>4.200000</td>
      <td>83.047000</td>
      <td>2.875000</td>
      <td>9.200000</td>
      <td>9.400000</td>
      <td>17.300000</td>
      <td>19.600000</td>
      <td>4.800000</td>
      <td>5.560000</td>
      <td>...</td>
      <td>2.196900</td>
      <td>13.020000</td>
      <td>24.080000</td>
      <td>17.840000</td>
      <td>28.280000</td>
      <td>37.607500</td>
      <td>109.332775</td>
      <td>108.730825</td>
      <td>111.480550</td>
      <td>109.335050</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>3.497500</td>
      <td>6.100000</td>
      <td>92.497500</td>
      <td>5.250000</td>
      <td>12.650000</td>
      <td>11.650000</td>
      <td>24.500000</td>
      <td>24.300000</td>
      <td>8.310000</td>
      <td>9.040000</td>
      <td>...</td>
      <td>2.972400</td>
      <td>14.165000</td>
      <td>25.955000</td>
      <td>19.370000</td>
      <td>31.990000</td>
      <td>49.020000</td>
      <td>127.947800</td>
      <td>127.369550</td>
      <td>128.846600</td>
      <td>115.906500</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>4.188750</td>
      <td>8.850000</td>
      <td>100.235500</td>
      <td>8.625000</td>
      <td>16.100000</td>
      <td>16.475000</td>
      <td>29.500000</td>
      <td>31.200000</td>
      <td>13.500000</td>
      <td>12.600000</td>
      <td>...</td>
      <td>3.697400</td>
      <td>17.930000</td>
      <td>31.087500</td>
      <td>23.792500</td>
      <td>37.962500</td>
      <td>61.940000</td>
      <td>139.943875</td>
      <td>140.425800</td>
      <td>140.846175</td>
      <td>130.304275</td>
    </tr>
    <tr>
      <th>max</th>
      <td>5.673000</td>
      <td>26.800000</td>
      <td>106.491000</td>
      <td>14.000000</td>
      <td>29.400000</td>
      <td>29.200000</td>
      <td>65.500000</td>
      <td>57.100000</td>
      <td>36.462500</td>
      <td>36.462500</td>
      <td>...</td>
      <td>8.098700</td>
      <td>33.100000</td>
      <td>68.350000</td>
      <td>42.050000</td>
      <td>84.110000</td>
      <td>147.060000</td>
      <td>167.752800</td>
      <td>167.477800</td>
      <td>169.529000</td>
      <td>154.893300</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 44 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">X_train_original</span><span class="o">.</span><span class="n">info</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>&lt;class &#39;pandas.core.frame.DataFrame&#39;&gt;
RangeIndex: 7764 entries, 0 to 7763
Data columns (total 45 columns):
指标名称                  7764 non-null datetime64[ns]
GDP:实际同比增长:全球         36 non-null float64
美国:GDP:现价:环比折年率:季调    275 non-null float64
欧元区:GDP平减指数:季调        84 non-null float64
全球商品贸易量增长率:出口金额:全球    20 non-null float64
工业增加值:当月同比            312 non-null float64
工业增加值:累计同比            210 non-null float64
固定资产投资完成额:累计同比        261 non-null float64
房地产开发投资完成额:累计同比       187 non-null float64
产量:发电量:当月同比           251 non-null float64
产量:发电量:累计同比           311 non-null float64
M0:同比                 257 non-null float64
M1:同比                 250 non-null float64
M2:同比                 250 non-null float64
中债国债到期收益率:3个月         3494 non-null float64
中债国债到期收益率:1个月         3493 non-null float64
中债国债到期收益率:1年          3494 non-null float64
中债国债到期收益率:5年          3494 non-null float64
中债国债到期收益率:10年         3494 non-null float64
CPI:当月同比              312 non-null float64
PPI:全部工业品:当月同比        231 non-null float64
PPI:全部工业品:累计同比        156 non-null float64
RPI:当月同比              396 non-null float64
RPI:累计同比              168 non-null float64
上证综合指数                6125 non-null float64
沪深300指数               3392 non-null float64
上证50指数                2914 non-null float64
中证500指数               2671 non-null float64
恒生AH股溢价指数             2536 non-null float64
国泰君安个人投资者投资景气指数       88 non-null float64
市盈率:沪深300             1068 non-null float64
市盈率:中证100             1068 non-null float64
市盈率:中证200             1068 non-null float64
市净率:沪深300             3920 non-null float64
市净率:中证100             3649 non-null float64
市净率:中证200             3273 non-null float64
滚动市盈率(TTM):沪深两市       1136 non-null float64
滚动市盈率(TTM):深圳市场       1136 non-null float64
滚动市盈率(TTM):深市主板       1136 non-null float64
滚动市盈率(TTM):中小板        1136 non-null float64
滚动市盈率(TTM):创业板        1136 non-null float64
中债总指数                 3502 non-null float64
中债国债总指数               3502 non-null float64
中债金融债券总指数             3502 non-null float64
中债信用债总指数              2248 non-null float64
dtypes: datetime64[ns](1), float64(44)
memory usage: 2.7 MB
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[22]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">X_train_original</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">y1_train</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>

<span class="c1"># not the same size. Need to split the data</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>(7764, 45)
(3392, 2)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">X_train_original</span><span class="o">.</span><span class="n">columns</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[5]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Index([&#39;指标名称&#39;, &#39;GDP:实际同比增长:全球&#39;, &#39;美国:GDP:现价:环比折年率:季调&#39;, &#39;欧元区:GDP平减指数:季调&#39;,
       &#39;全球商品贸易量增长率:出口金额:全球&#39;, &#39;工业增加值:当月同比&#39;, &#39;工业增加值:累计同比&#39;, &#39;固定资产投资完成额:累计同比&#39;,
       &#39;房地产开发投资完成额:累计同比&#39;, &#39;产量:发电量:当月同比&#39;, &#39;产量:发电量:累计同比&#39;, &#39;M0:同比&#39;, &#39;M1:同比&#39;,
       &#39;M2:同比&#39;, &#39;中债国债到期收益率:3个月&#39;, &#39;中债国债到期收益率:1个月&#39;, &#39;中债国债到期收益率:1年&#39;,
       &#39;中债国债到期收益率:5年&#39;, &#39;中债国债到期收益率:10年&#39;, &#39;CPI:当月同比&#39;, &#39;PPI:全部工业品:当月同比&#39;,
       &#39;PPI:全部工业品:累计同比&#39;, &#39;RPI:当月同比&#39;, &#39;RPI:累计同比&#39;, &#39;上证综合指数&#39;, &#39;沪深300指数&#39;, &#39;上证50指数&#39;,
       &#39;中证500指数&#39;, &#39;恒生AH股溢价指数&#39;, &#39;国泰君安个人投资者投资景气指数&#39;, &#39;市盈率:沪深300&#39;, &#39;市盈率:中证100&#39;,
       &#39;市盈率:中证200&#39;, &#39;市净率:沪深300&#39;, &#39;市净率:中证100&#39;, &#39;市净率:中证200&#39;, &#39;滚动市盈率(TTM):沪深两市&#39;,
       &#39;滚动市盈率(TTM):深圳市场&#39;, &#39;滚动市盈率(TTM):深市主板&#39;, &#39;滚动市盈率(TTM):中小板&#39;,
       &#39;滚动市盈率(TTM):创业板&#39;, &#39;中债总指数&#39;, &#39;中债国债总指数&#39;, &#39;中债金融债券总指数&#39;, &#39;中债信用债总指数&#39;],
      dtype=&#39;object&#39;)</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">display</span><span class="p">(</span><span class="n">X_train_original</span><span class="o">.</span><span class="n">head</span><span class="p">())</span>
<span class="n">display</span><span class="p">(</span><span class="n">X_train_original</span><span class="o">.</span><span class="n">tail</span><span class="p">())</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>



<div class="output_html rendered_html output_subarea ">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>指标名称</th>
      <th>GDP:实际同比增长:全球</th>
      <th>美国:GDP:现价:环比折年率:季调</th>
      <th>欧元区:GDP平减指数:季调</th>
      <th>全球商品贸易量增长率:出口金额:全球</th>
      <th>工业增加值:当月同比</th>
      <th>工业增加值:累计同比</th>
      <th>固定资产投资完成额:累计同比</th>
      <th>房地产开发投资完成额:累计同比</th>
      <th>产量:发电量:当月同比</th>
      <th>...</th>
      <th>市净率:中证200</th>
      <th>滚动市盈率(TTM):沪深两市</th>
      <th>滚动市盈率(TTM):深圳市场</th>
      <th>滚动市盈率(TTM):深市主板</th>
      <th>滚动市盈率(TTM):中小板</th>
      <th>滚动市盈率(TTM):创业板</th>
      <th>中债总指数</th>
      <th>中债国债总指数</th>
      <th>中债金融债券总指数</th>
      <th>中债信用债总指数</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1947-06-30</td>
      <td>NaN</td>
      <td>5.3</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1947-09-30</td>
      <td>NaN</td>
      <td>6.4</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1947-12-31</td>
      <td>NaN</td>
      <td>17.3</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1948-03-31</td>
      <td>NaN</td>
      <td>9.3</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1948-06-30</td>
      <td>NaN</td>
      <td>10.5</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 45 columns</p>
</div>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>



<div class="output_html rendered_html output_subarea ">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>指标名称</th>
      <th>GDP:实际同比增长:全球</th>
      <th>美国:GDP:现价:环比折年率:季调</th>
      <th>欧元区:GDP平减指数:季调</th>
      <th>全球商品贸易量增长率:出口金额:全球</th>
      <th>工业增加值:当月同比</th>
      <th>工业增加值:累计同比</th>
      <th>固定资产投资完成额:累计同比</th>
      <th>房地产开发投资完成额:累计同比</th>
      <th>产量:发电量:当月同比</th>
      <th>...</th>
      <th>市净率:中证200</th>
      <th>滚动市盈率(TTM):沪深两市</th>
      <th>滚动市盈率(TTM):深圳市场</th>
      <th>滚动市盈率(TTM):深市主板</th>
      <th>滚动市盈率(TTM):中小板</th>
      <th>滚动市盈率(TTM):创业板</th>
      <th>中债总指数</th>
      <th>中债国债总指数</th>
      <th>中债金融债券总指数</th>
      <th>中债信用债总指数</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7759</th>
      <td>2015-12-27</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>3.0719</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7760</th>
      <td>2015-12-28</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>2.9855</td>
      <td>22.75</td>
      <td>44.89</td>
      <td>26.14</td>
      <td>54.99</td>
      <td>91.62</td>
      <td>167.7263</td>
      <td>167.4778</td>
      <td>169.4162</td>
      <td>154.7450</td>
    </tr>
    <tr>
      <th>7761</th>
      <td>2015-12-29</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>3.0084</td>
      <td>23.08</td>
      <td>45.99</td>
      <td>26.45</td>
      <td>57.46</td>
      <td>92.36</td>
      <td>167.7528</td>
      <td>167.4174</td>
      <td>169.5290</td>
      <td>154.8247</td>
    </tr>
    <tr>
      <th>7762</th>
      <td>2015-12-30</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>2.9765</td>
      <td>23.26</td>
      <td>46.64</td>
      <td>27.00</td>
      <td>57.98</td>
      <td>93.77</td>
      <td>167.7114</td>
      <td>167.4101</td>
      <td>169.4554</td>
      <td>154.8933</td>
    </tr>
    <tr>
      <th>7763</th>
      <td>2015-12-31</td>
      <td>3.398</td>
      <td>1.3</td>
      <td>106.491</td>
      <td>NaN</td>
      <td>5.9</td>
      <td>6.1</td>
      <td>10.0</td>
      <td>1.0</td>
      <td>-3.7</td>
      <td>...</td>
      <td>2.9336</td>
      <td>22.96</td>
      <td>45.80</td>
      <td>26.55</td>
      <td>57.00</td>
      <td>91.50</td>
      <td>167.7430</td>
      <td>167.4459</td>
      <td>169.4835</td>
      <td>154.8913</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 45 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[25]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">X_train_original</span><span class="p">[</span><span class="s1">&#39;指标名称&#39;</span><span class="p">][</span><span class="mi">0</span><span class="p">])</span>
<span class="nb">print</span><span class="p">(</span><span class="n">y1_train</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span><span class="mi">0</span><span class="p">][</span><span class="mi">0</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>1947-06-30 00:00:00
2002-01-04 00:00:00
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">X_train_original</span><span class="p">[</span><span class="s2">&quot;IsInY1&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">nan</span>
<span class="n">X_train_original</span><span class="p">[</span><span class="s2">&quot;IsInY2&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">nan</span>
<span class="n">X_train_original</span><span class="p">[</span><span class="s2">&quot;IsInY3&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">nan</span>

<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">X_train_original</span><span class="o">.</span><span class="n">index</span><span class="p">:</span>
    <span class="n">Current_Index</span> <span class="o">=</span> <span class="n">X_train_original</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">i</span><span class="p">,</span> <span class="s1">&#39;指标名称&#39;</span><span class="p">]</span>
    <span class="n">X_train_original</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">i</span><span class="p">,</span> <span class="s2">&quot;IsInY1&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">any</span><span class="p">(</span><span class="n">y1_train</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span> <span class="mi">0</span><span class="p">]</span> <span class="o">==</span> <span class="n">X_train_original</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="n">i</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
    <span class="n">X_train_original</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">i</span><span class="p">,</span> <span class="s2">&quot;IsInY2&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">any</span><span class="p">(</span><span class="n">y2_train</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span> <span class="mi">0</span><span class="p">]</span> <span class="o">==</span> <span class="n">X_train_original</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="n">i</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
    <span class="n">X_train_original</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">i</span><span class="p">,</span> <span class="s2">&quot;IsInY3&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">any</span><span class="p">(</span><span class="n">y3_train</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span> <span class="mi">0</span><span class="p">]</span> <span class="o">==</span> <span class="n">X_train_original</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="n">i</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[67]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Y1&quot;</span><span class="p">,</span> <span class="nb">int</span><span class="p">(</span><span class="n">X_train_original</span><span class="p">[</span><span class="s2">&quot;IsInY1&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">values</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;int&quot;</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">()),</span> <span class="s2">&quot;/&quot;</span><span class="p">,</span> <span class="n">X_train_original</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Y2&quot;</span><span class="p">,</span> <span class="nb">int</span><span class="p">(</span><span class="n">X_train_original</span><span class="p">[</span><span class="s2">&quot;IsInY2&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">values</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;int&quot;</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">()),</span> <span class="s2">&quot;/&quot;</span><span class="p">,</span> <span class="n">X_train_original</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Y3&quot;</span><span class="p">,</span> <span class="nb">int</span><span class="p">(</span><span class="n">X_train_original</span><span class="p">[</span><span class="s2">&quot;IsInY3&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">values</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;int&quot;</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">()),</span> <span class="s2">&quot;/&quot;</span><span class="p">,</span> <span class="n">X_train_original</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Y1 3392 / 7764
Y2 3494 / 7764
Y3 2822 / 7764
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Look-at-only-Y1-now">Look at only Y1 now<a class="anchor-link" href="#Look-at-only-Y1-now">&#182;</a></h3><p>Make <code>X1_train</code></p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Drop some rows</span>
<span class="n">X1_train</span> <span class="o">=</span> <span class="n">X_train_original</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">where</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">logical_not</span><span class="p">(</span><span class="n">X_train_original</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span> <span class="s2">&quot;IsInY1&quot;</span><span class="p">]))[</span><span class="mi">0</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Find out which columns only have NaNs: Count number of NaNs in each column</span>
<span class="c1">#print(X1_train.isnull().sum())</span>

<span class="c1"># Drop anything that has greater than 100 NaNs</span>
<span class="n">count_NaNs</span> <span class="o">=</span> <span class="n">X1_train</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>
<span class="n">drop_columns</span> <span class="o">=</span> <span class="n">count_NaNs</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">count_NaNs</span> <span class="o">&gt;</span><span class="mi">100</span><span class="p">]</span><span class="o">.</span><span class="n">index</span>
<span class="n">X1_train</span> <span class="o">=</span> <span class="n">X1_train</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">drop_columns</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Fill the NaNs</span>
<span class="n">X1_train</span> <span class="o">=</span> <span class="n">X1_train</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">method</span><span class="o">=</span><span class="s1">&#39;ffill&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[102]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">X1_train</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">y1_train</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
<span class="n">np</span><span class="o">.</span><span class="n">all</span><span class="p">([</span><span class="n">x</span> <span class="o">==</span> <span class="n">y</span> <span class="k">for</span> <span class="n">x</span><span class="p">,</span> <span class="n">y</span> <span class="ow">in</span> <span class="nb">zip</span><span class="p">(</span><span class="n">X1_train</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span><span class="mi">0</span><span class="p">],</span><span class="n">y1_train</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span><span class="mi">0</span><span class="p">])])</span> <span class="c1"># there is 1 to 1 correpsondence in X1_train, y1_train</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>(3392, 14)
(3392, 2)
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[102]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>True</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[41]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Save cleaned data</span>
<span class="n">X1_train</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">&quot;IsInY1&quot;</span><span class="p">,</span><span class="s2">&quot;IsInY2&quot;</span><span class="p">,</span><span class="s2">&quot;IsInY3&quot;</span><span class="p">],</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">X1_train</span><span class="o">.</span><span class="n">to_csv</span><span class="p">(</span><span class="s2">&quot;./data/Cleaned_X1_序列_train.csv&quot;</span><span class="p">,</span> <span class="n">index</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">encoding</span><span class="o">=</span><span class="s1">&#39;utf-8&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Load data for next session</span>
<span class="n">X1_train</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s2">&quot;./data/Cleaned_X1_序列_train.csv&quot;</span><span class="p">,</span> <span class="n">encoding</span><span class="o">=</span><span class="s2">&quot;utf&quot;</span><span class="p">,</span> <span class="n">engine</span><span class="o">=</span><span class="s1">&#39;python&#39;</span><span class="p">)</span>
<span class="n">headers</span> <span class="o">=</span> <span class="p">[</span><span class="sa">u</span><span class="s1">&#39;指标名称&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;中债国债到期收益率:3个月&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;中债国债到期收益率:1个月&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;中债国债到期收益率:1年&#39;</span><span class="p">,</span>
       <span class="sa">u</span><span class="s1">&#39;中债国债到期收益率:5年&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;中债国债到期收益率:10年&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;上证综合指数&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;沪深300指数&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;中债总指数&#39;</span><span class="p">,</span>
       <span class="sa">u</span><span class="s1">&#39;中债国债总指数&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;中债金融债券总指数&#39;</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[141]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Find out if dates are even </span>
<span class="n">dates</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">asarray</span><span class="p">([</span><span class="n">matplotlib</span><span class="o">.</span><span class="n">dates</span><span class="o">.</span><span class="n">date2num</span><span class="p">(</span><span class="n">i</span><span class="o">.</span><span class="n">date</span><span class="p">())</span> <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">X1_train</span><span class="p">[</span><span class="s2">&quot;指标名称&quot;</span><span class="p">]])</span> <span class="c1"># convert to num first</span>

<span class="n">intervals</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">diff</span><span class="p">(</span><span class="n">dates</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">unique</span><span class="p">(</span><span class="n">intervals</span><span class="p">))</span> <span class="c1"># dates are not even intervals. Most of the data is continuous</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span><span class="mi">3</span><span class="p">))</span>
<span class="n">sns</span><span class="o">.</span><span class="n">distplot</span><span class="p">(</span><span class="n">intervals</span><span class="p">,</span> <span class="n">kde</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">bins</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">unique</span><span class="p">(</span><span class="n">intervals</span><span class="p">))</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>[ 1.  2.  3.  4.  5.  6.  8.  9. 10. 11. 12. 13. 17.]
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Combine data for ease of plotting</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">X1_train</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>
<span class="n">df</span><span class="p">[</span><span class="s2">&quot;Y&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">y1_train</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[44]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Do some histogram plots for the features</span>
<span class="n">df</span><span class="o">.</span><span class="n">hist</span><span class="p">(</span><span class="n">bins</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">20</span><span class="p">,</span><span class="mi">15</span><span class="p">))</span>
<span class="c1"># Fix some font issues with Chinese titles in pandas</span>
<span class="n">SetFont</span><span class="p">(</span><span class="n">axes</span><span class="p">,</span> <span class="n">plt</span><span class="o">.</span><span class="n">gcf</span><span class="p">(),</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">8</span><span class="p">,</span> <span class="n">fontname</span><span class="o">=</span><span class="s1">&#39;c:</span><span class="se">\\</span><span class="s1">windows</span><span class="se">\\</span><span class="s1">fonts</span><span class="se">\\</span><span class="s1">simsun.ttc&#39;</span><span class="p">,</span> <span class="n">items</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;title&quot;</span><span class="p">])</span>
<span class="p">[</span><span class="n">ax</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="n">ax</span><span class="o">.</span><span class="n">get_title</span><span class="p">(),</span> <span class="n">fontproperties</span><span class="o">=</span><span class="n">fontprop</span><span class="p">)</span> <span class="k">for</span> <span class="n">ax</span> <span class="ow">in</span> <span class="n">plt</span><span class="o">.</span><span class="n">gcf</span><span class="p">()</span><span class="o">.</span><span class="n">axes</span><span class="p">]</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
laWsrCxFRUXpypUrOn78uP75z3/q1VdflZeXlyZMmKCXX37Z+torV67IYrHI399fCQkJ2r59u65c
uaITJ05o+fLlSkhI0MCBA+Xv7y9Jql27dpHXS9KXX36pH3/8Uc8995x127BhwzR58mT169dPwcHB
GjFihJo3b67NmzcrLi5O586dU9++fbVnzx4dOHBAX375paSCi/23335bffv2lY+Pj9566y2tX79e
t956q+68804ZhqGkpCT9+c9/1v33368JEyZowYIF1h9WAOAMvv32W61evVr169eXJJ05c0YfffSR
9VybkpKiQYMGaezYsUpJSdGZM2fUuHFjnT9/XiNHjpSPj4+1J0+tWrW0dOlSBQYGWo/v4eGhtWvX
SpI++OAD3XLLLfrDH/6g3Nxc7dmzp8i8cRU9/v79+7V161Z17dpVycnJ+uKLL9SgQQMFBwcXSzaZ
TCbdeeed8vb21urVq5WRkaG7775b999/v95++21r25Wammp9zcGDB609SiXpq6++UlxcnLZt2yap
IJHStm1b3X333apfv76Cg4PVp08f+fj4aOXKlRoyZIgaNGigHTt2qEOHDsWSNvXq1dOECRMUGRmp
HTt2KCIiQnFxcdq3b5+GDx+u2NhYTZw4scx2pUWLFho4cKC++eYb67b//Oc/qlWrlvVmSPPmzbV/
/3794Q9/UHx8vDIzMxUbG2vdf8yYMXr99dclFfQ6oi1zDCSF4NJuuOEGXblyRWlpaWSgAcBFNGzY
0HpRea2bb75ZW7dutXbj9/Pzk6enp/Lz8xUWFqYzZ87onnvu0dKlS9W6dWutWLFCBw8e1MMPPyxJ
atOmjTZv3lzkmAcPHlSHDh2UkZGh7du3q1GjRtq3b5/27t1rvYiXpGbNmunJJ59UbGxskYvyCxcu
6PDhw7rnnnvUqVMntWvXzvpDIjk5WW+++aZq166t8+fPKyEhQU899ZQWLVqkRx99VJcvX5afn5/1
IpyLaADOyMPDQ+PGjbMO8Vq3bp3atWunLl26SJJiY2PVoEEDSVJ0dLTMZrOSk5OVnJysRYsWSZIO
HDige++9Vzk5OYqLi1Pfvn2tyQhJ2rBhg7Zt22btKSRJHTp00EMPPVQklooe39vbW3379tX58+eV
mpqqyMhILVy4sNSJqc1ms15++WUlJibqk08+kVSQnFm2bJkkWXvxFG6XChJKubm5ysjI0PPPP6/u
3bvr0qVLWrp0qXUomyR5e3vLMAwtWLBAt956q2644QbVqlVLvXv31pw5c2SxWDRnzhz5+PhIKri5
MXHiRHl4eCgvL0/fffedUlJS9OKLL+rQoUOaMWNGsfhnzZqlJk2a6K9//Wupn+vx48etvbsk6aab
blJSUpI6dOigpKQkPfrooxoyZIj1czp69KjCwsKUl5en06dP64MPPlDDhg1LfQ9UP5JCcHldu3ZV
Tk6OvcMAANiRh4eHoqKiimwzmUyqU6eO0tLS1LJlS128eFEjR45UvXr1dPnyZWVnZ6tRo0aSpBkz
Zuimm26yzhvUqlUr63OFTp48qSZNmqhXr16SCuZSWLVqlY4fP64//vGPatGihbZu3aoVK1ZYJ8o+
e/asRowYoZEjRyo3N1dr1qzR6tWrlZCQoKNHjyo/P1/vvvuuzp8/r/Pnzxf5AQQAzqK0ueCudurU
KbVs2VK///67br75ZlksFo0ZM8Z6vv3kk0+UlJSkN954o9j58LHHHtOwYcMUGxur2rVrq3v37qpf
v77i4uIqdfzCSf7j4uKUm5srwzCsQ4NLcuXKFYWFhSkrK8s67Ku0/Qvt379fTz75pA4cOCCpYAjz
1cOjpYL5ir777jtFREQU6S1Vp04dLVy4UHPmzNFPP/2k++67z/pcamqqcnNz1a9fPyUmJio4OFif
f/65vL29tXLlSj311FPWJJJU0Pu1tDmfCl2+fLnI51C3bl1duHBBderU0YABAxQfH69evXpp3Lhx
kor2FILjICkEl8cFNAC4p5JWDSuUmZmpyMhI9evXT1999ZVatWql6OhoXbp0Sb/++qtOnDihP/7x
j9bhDlcbNGiQWrRoUWRb4R3hwjnsCueySE1NtQ5d8PT01F/+8hf16dNHkrRlyxbdcccdkqQbb7xR
r7zyirZu3apJkybJ39/f2uupc+fOmjBhgoYPH17pegGAmpafn6/XXntNGzZskFQwfMzHx6fI8LGp
U6fKz89PwcHB+uqrryQVnDMHDhyo0aNHKyoqSuHh4Zo+fbrNOXCuvuYPDAzUggULrMO1Cl3P8adM
maJTp04pNTVVOTk5+sc//qGGDRtaexjZUrt2ba1evVqJiYl67733lJqaqqysLP3www+SVOJqX0FB
QfLz89OBAwd09uxZ7du3T6NGjSqyT8uWLRUTE6OPP/642OstFotuvfXWIgmhefPmqWvXrmrbtq2e
fvppBQUFKTMzU/v379eMGTNksVi0b9++Ij2q7rrrrhLLdrV69eopMzPT+jgzM9Pa86k8jhw5otat
W5d7f1QPkkIAAMCl5Ofna+XKlRoxYkSp+9WtW1ehoaF64IEH5OPjo7y8PK1cuVI+Pj666667ZDab
tWnTJgUFBRW7U3vfffdZJwwtFBkZWWRRA19fXwUFBRW5S+3h4aHs7GzrRbTFYilyjPr168vHx0fx
8fH66KOPrN36a9Wqpfj4eM2aNaviFQIAdtaoUSOtXLlSzZs3lyS9+eabuvvuu63Dx77//nsFBARY
k0TXKpwzrrw8PDw0fvx4HTp0SH5+ftbt13P8OXPmyGw2W+eHK+wxmpycXGwI2aVLlzR27FgZhqGw
sDBZLBaZzWbFxMSoTp06uvvuuyUV9OqRCtqA77//Xu+//77S09Otsfbp00cvvfSSvLy8rMPqrmax
WPTmm2/qf//3f9W0aVOdOnVKN910k2655ZZiQ6AnTJhgfb/Y2Fht3rxZAQEBmj9/vsxmsx588EHt
3bu3zDq15bbbblN0dLT18e+//64ePXooOTlZERER8vDwUHp6unUIdOHwsUJHjx7V8uXLWVHTzkgK
waVdunTJ2v3yoYceqlDmGgDgHK5cuaLY2FiFhobKMAx9/vnnmjVrVpFu9VfbsWOH+vbtq9zcXDVq
1EibNm1Sw4YNrT2C/t//+3/as2ePJOnPf/6zhgwZopUrV6pZs2bWY3z33XfF7kDb6pm0c+dO/fDD
D7rtttskFUws/d577+nTTz+VVDB8rF27dkVe06JFC33xxReaPn263n//fWVmZurrr7/W5s2b9fzz
zyssLEz9+/cvdVU1AHAk1ybWr3XPPfcUeVw41CovL0+enp765Zdf1LRpU0kFCZX8/PwiQ9LS09O1
Z88e+fn5qUmTJvLy8tL58+eVl5dn89xckeNfOy9pfn6+Tpw4ofr166t///5FnqtXr57ee+89LVu2
TK1atdJNN91kHQJmawid2WzWvHnz1L59ex06dMi63dfXV2fPnrUm0a5V2nC8q+e6+/nnnzVx4sQi
7eG5c+dkNpuLJcgaNWpk7QH7008/ydfX11onJWnatKmys7OVlZWlOnXq6Pjx43r++efl6elpnbvp
agwfc0wkheDS6tWrp/nz59s7DADAdbJ1QSupWEJGku699161bt1a06ZNk8ViUUhIiLy9va37Xv2a
G2+8US1bttTu3bsVHh6u9PR0xcXFady4cfrkk0+0ZcsWPfroozKbzRo9erTOnTtXJCk0ePDgIhOF
SgUTp14rICBA//73v/XEE09IKhiqMHv2bOvd8R07dlhvWFy4cEFHjhyRv7+/xo0bp4yMDD300EPK
zc3VhAkTJEkrV67Um2++qXvuuafI5J4A4EwMwyh1jp3CHjg333yzwsPDtWDBAg0fPlz/+te/VL9+
faWmploT+fn5+Xr77bdtDvWVCubTGTly5HUd32Kx6JtvvlFSUpISEhLk7++vbdu2qX379goMDFR+
fr4uXbpUpNfn999/L19fXz3yyCOSCpaY37p1q/7+979bew5dPd9p4ZxFV3v77bf1zDPP6F//+pfG
jRunp59+Wq1bt7YmfK5O/NjyxRdfqFevXrrzzjuLDTPbtGmTGjdubG2HbImOji420fSRI0f0r3/9
Sz///LOCgoKscyVNnDhRy5cvl5+fn0aOHGldSMHWIj+GYZQaN+zDZPDJAAAAN3ftql6fffaZevXq
ZV3FzB6uvRMOAK5izZo1atu2rR544AGbz0+fPl3z58/X6dOn9cUXX6hdu3YKCgqSVJB02bhxo3VF
rk2bNsnf318PPvigzWN98803SktLKzJnTnmPbxiGli1bpvvvv1+dOnUqtgT9sWPHtGTJErVp00bP
PfecUlJS9MsvvxQZDrVjxw61a9dOjRs31oULF/T6668rIyND8+bNK3Ks559/XvPnz9e2bdt0zz33
6LbbblNeXp5efPFFxcbGatasWWrdurVmzJhRZKhySV544YVic99J0saNG3XzzTfbZchWWFhYsUUf
YH8khQAAAAAANeY///mPGjduXGLiPT8/X6mpqbp48aLNxMbVrk3ql0dFjl+WnJycEofzGoahnJyc
Ir1mDMOw2dNn7969uvHGG9W8efNiz//2229lDuUqryNHjqh+/fp2WQr+u+++U8eOHWv8fVE6kkIA
AAAAHFpOTo6mTZumU6dOyWKxKCIiQo0bN9aYMWOsc3YNHz5cDz/8sGJiYhQdHS0vLy9FRESod+/e
9g0eABwYSSEAAAAADm3jxo1KSEjQ9OnTlZqaqkGDBunpp59WWlqawsPDrfulpKQoPDxcGzduVHZ2
tkJDQ7Vx40ab85sAAOw80XRKStp1vS4wsK4uXsys4miqD/FWL2eLV3K+mIm3/Bo29Ct7J1Qpd2lL
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
hIQoNTVVvXr10nvvvafMzEx9/fXXio6ObvYjw2QyyWQyadu2bTKZTPrss8+0Y8cORUZG6plnnpHD
4XA/d8SIEbJarfrqq6/01VdfacqUKQoKCtLAgQPd+92xY4euuOKKbjgSAGAcnsw9ErkBvo+ikEH8
61//0rp169SvXz9J0uHDh/XKK68oMjJSklReXq6bbrpJd9xxh8rLy3X48GENGDBAR44c0e23366w
sDB3BTwkJESPPfaYoqOj3fsPCgrSM888I0n685//rAsvvFD/7//9P9XW1mr79u1NRrh0dP9FRUV6
7bXXdPnll6usrEzvvvuu+vfvr6lTpzY7gTeZTLr44osVGhqqdevWyW6365JLLtGVV16pDRs2KCUl
RZJUVVXlfs3HH3/s/vKVpPfee0+FhYV6/fXXJTUUWMaMGaNLLrlE/fr109SpU3XttdcqLCxMa9as
0c9+9jP1799fb775psaPH68BAwY0ialv376aN2+eMjIy9OabbyotLU2FhYX64IMPNGvWLL344oua
P3++OxF1VHFxsU6cOKEXX3zRvW3u3Ll6+umnJUkOh6PT+waAnuTPuUqSSktLlZWVpQEDBugPf/iD
e3tZWZlmz56tWbNmSZK++eYbpaWlqb6+XjU1NTrvvPM0fvx49e/fX//zP//j/jHyyiuvaNq0abLb
7ZozZ46Cg4P18ccfa/To0erdu7fCwsL05ZdfKiUlRV9++aUuvPBCRUdHt+tCAwCggadzD7kBvo6i
kEEEBQXprrvucg+bf+655zR27FhNnDhRkvTiiy+qf//+kqS8vDxZLBaVlZWprKxMy5cvlyTt3LlT
P/jBD1RTU6PCwkJNmTJFffr0cb/HH//4R73++uvuq6+SNH78eP34xz9uEktH9x8aGqopU6boyJEj
qqqqUkZGhh555JFWJ3SzWCx6/PHHVVpaqldffVVSQ3Fm1apVkuQexXNqu9RQUKqtrZXdbtc999yj
SZMm6dixY3rssceaDAENDQ2Vy+Vy3751zjnnKCQkRAkJCXrooYfkdDr10EMPKSwsTJLUq1cvzZ8/
X0FBQaqrq9NHH32k8vJyPfjgg9q1a5eys7ObxZ+Tk6OBAwfqv//7v93bjh07pjVr1shmsykiIkLp
6ek6efKkDh48qJ/+9Kf62c9+5j4e+/fvV0pKiurq6vTNN9/oz3/+s3uYKQD4Kn/OVVJD7pk1a5bm
zJnTZF8bN27UiBEj3H9fcMEF2rJliwoLC1VRUaEpU6Zo+/bt2rlzp/7xj39IahilumHDBk2ZMkVh
YWF6/vnntXHjRg0aNEgXX3yxXC6XDh48qJ///Oe68sorNW/ePC1btoyLAADQQZ7OPeQG+DqKQgbR
eAhkaw4dOqQRI0bo22+/1QUXXCCn06m5c+fq3HPPlSS9+uqrOnjwoH73u981OcmWGm6Tmjlzpl58
8UX16tVLkyZNUr9+/VRYWNil/Y8bN05SwwTNtbW1crlc7ir62Xz//fdKSUnRyZMn3bd9tfb8U4qK
ivSLX/xCO3fulCTt2rVL8fHxTZ7z2Wef6aOPPlJaWlqTqwC9e/fWI488ooceekj79u3TD3/4Q/dj
VVVVqq2t1XXXXafS0lJNnTpV77zzjkJDQ7VmzRrNnj3bXUSSpJkzZzYbStq3b1/Nnj1bkrRgwQId
PHhQgwcP1rRp01RcXKxrrrlGd911l6SmI4UAwF/4c66SGm5h7oijR49q7969uvTSSxUfH6+xY8e6
R8CWlZXp2WefVa9evXTkyBGVlJRo9uzZWr58uX7605/q+PHjioiI0IcffiiJUaEA0Fmezj3kBvg6
ikIGUV9fr6eeekp//OMfJTUMiwwLC2syLHLBggWKiIjQ1KlT9d5770mSgoODdeONN+rXv/61cnNz
lZqaqvvvv7/F4YeNv/yio6O1bNky9+1ap3Rm/1lZWTp06JCqqqpUU1Oj//u//1NMTIy7Mt+SXr16
ad26dSotLdWmTZtUVVWlkydP6t///rcknXW1L6vVqoiICO3cuVPfffedPvjgg2ZV/REjRig/P19/
/etfm73e6XRq0KBBTQpCS5cu1eWXX64xY8YoPT1dVqtVJ06cUFFRkbKzs+V0OvXBBx80uUo9evTo
ZvtuPJ/Q2LFj9cknn2jw4MFn7YPGPv30U40cObJdzwUAb/HnXCVJNTU12rRpk9599125XC73bcll
ZWV68MEH3c87duyY1q5dqy+++ELXX3+9hg8frtdee01PPvmkzjnnHEnSd999p9tuu0233367amtr
tX79eq1bt04lJSXav3+/6uvr9Yc//EFHjhzRkSNHmhW/AADt4+ncQ26Ar6MoZBDnnnuu1qxZo6FD
h0qSnn32WV1yySXuYZG7d+9WVFSU+8vvTN9//72++OKLdr9fUFCQMjMztWvXLkVERLi3d2b/Dz30
kCwWi3so5aniSFlZWbNbyI4dO6Y77rhDLpdLKSkpcjqdslgsys/PV+/evXXJJZdIahjVIzUUcXbv
3q0XXnjBfVuWJF177bV69NFHZTab3cNFG3M6nXr22Wf1t7/9TbGxsTp06JDOP/98XXjhhdqyZUuT
586bN8/9fi+++KK2bNmiqKgoPfzww7JYLJo8ebJ27NjRan/a7XatXbtW8+fPl9SQvHr16qWysjKl
paUpKChINpvNfVXg1O1jp+zfv1+rV69mkjkAPs2fc5UkDRo0SDk5ORo5cqQ2bdqkKVOmaMyYMTp8
+HCTE/NTE1tXVVW55zEKDg7WL3/5S1177bWSpK1bt+qiiy6SJJ133nl64okn9Nprr+nee+9VZGSk
XnvtNZnNZk2YMEHz5s1zz0kBAOgYT+cecgN8HUUhgzjzFqgzXXrppU3+PnWrVV1dnYKDg/X5558r
NjZWUkNBpb6+vslQS5vNpu3btysiIkIDBw6U2WzWkSNHVFdXp6NHjzZ7v47s/8wVs+rr63XgwAH1
69dPiYmJTR7r27evNm3apFWrVikuLk7nn3+++xawloaGWiwWLV26VOPGjdOuXbvc28PDw/Xdd9+5
k8OZWhtmeqr6L0mffPKJ5s+f3+Q2s4qKClkslmaJ5dxzz9Xw4cMlSfv27VN4eLi7T06ePKmSkhL3
cz/77DPdcMMNOuecc9z3NjfG7WMA/JE/56qSkhJVVlaqpKREvXv31u23366HH35Yjz32mKqqqvT8
889r5MiRmjFjhsLDw2W1WpvcshYUFCSHw6ETJ05Iarj40Fi/fv0UFham4uJivfLKK+756EJCQlRc
XKycnJw2ehcA0BJP5h5yA/wBRSGDcrlcrc6xc2oEzgUXXKDU1FQtW7ZMs2bN0ksvvaR+/fqpqqrK
PUN/fX29NmzY4P77TFVVVbr99ts7tX+n06kPP/xQBw8eVElJiSIjI/X6669r3Lhxio6OVn19vY4d
O9bkC3L37t0KDw/XT37yE0kNq3O99tpr+s1vfuMeOVRTU+N+/qk5ixrbsGGD7rzzTr300ku66667
lJ6erpEjR7oLPo0LPy159913dc011+jiiy9udpvZyy+/rAEDBrivPrQkLy+vyUTT/fv3d8+BUVdX
p8suu8w9jLSlZeY7eu8yAPgif8lVNptN9957rzZs2KB9+/bJYrGoX79++t///V9J0rZt23TPPfdo
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
NPka7Nmzx/tHsGS+9xlNC8a+QjLfzxj9hu+ZLafZ+48GVupHbAaTbwAAAAAAAFhOaD9DBAAAAAAA
gEZRFAIAAAAAALAgikIAAAAAAAAWRFEIAAAAAADAgigKAQAAAAAAWBBFIQAAAAAAAAuiKAQAAAAA
AGBBFIUAAAAAAAAsiKIQAAAAAACABVEUAgAAAAAAsCCKQgAAAAAAABZEUQgAAAAAAMCCKAoBAAAA
AABYEEUhAAAAAAAAC6IoBAAAAAAAYEEUhQAAAAAAACyIohAAAAAAAIAFURQCAAAAAACwIIpCAAAA
AAAAFkRRCB2mrq7uvF/7m9nyAAB8h3s8AABA61EUQou88847Kisra/L7LpdLt99++1m/lN9zzz2S
pNraWrlcriZfu3r1an3zzTctzvLJJ594//3II4/ou+++a3eeiooK1dfXS5KefvppHTx4UIZh6PPP
P28yx9dff629e/d6v167dq3++c9/NrrvP/7xD7377ruSpNLS0rOuZcN5Gxw+fFiStG7dOm3fvl27
d+9WbW2t1qxZo7/97W9N5gEAKzh+/Ljefvvtc7avWbNG//rXv87advToUe+/9+zZ02hftH///o4P
Ke77AAAgOIQHOgCCw549exQTE9Pk99977z395Cc/0TPPPKN//OMf3tdkZWXp0KFDuvLKK/Xoo4+e
87rdu3frgw8+UO/evdW9e/dzvn/o0CH96le/UnR0tHeb3W7Xk08+qR/84Aey2+3q1KlTu/M4HA7d
c889WrFihT7++GPdf//9evXVV3XkyBENHjy40Tb36NFDd9xxh1atWqWoqCiVl5drwoQJje77n//8
R//5z3+8be7du7ek0380LFy4UKtWrVJiYqIk6ciRI/rd736nuLg4RUVF6Xe/+53uueceffzxx0pP
T2/0+ABgFZ07d9auXbtkGIbS0tJUW1srh8OhUaNGadOmTZowYYJOnDihqKgonTp1Svfff7+WLl2q
Tz75RK+88ooiIiK8x6qrq9OJEyf0yiuvyGaz6e2339bx48e1a9cu3Xbbbbr00kslnS7qbN68WXa7
XWlpaRowYMB5t0vc9wEAQHCgKIRGffvtt0pISFBkZKQkKSwsTGFh/x1Ytnv3bkVERKhnz56SpLfe
ekszZ85UfHy8HA6HHA6HZs+erccee0xlZWVyOp2Nnuepp57So48+qk8//VSlpaW6+uqrz/p+165d
9fDDD+vYsWO66KKL9MEHHygjI+Oc4xw8eFAXXXSR9+vW5unbt69GjhypvXv3atanjPkAACAASURB
VMCAAXK73br44ouVlpamd955R6mpqWftX11drYiICGVnZ6tTp0768MMPlZubq3379ikhIeGcAprN
ZpPNZtPmzZtls9n0z3/+U6WlpYqLi9Pq1avl8Xi8+/br109Op1Nff/21vv76a6WmpiosLEw9evTw
HrexawUAVjFx4kTV1tZq586dWr9+vSoqKmSz2SRJf/3rX3XixAn96U9/UteuXTVmzBh99dVX+vLL
L5Wfn6+vv/5a119/vTZs2KCamhpdfvnlstlscrlc+stf/qJnn31WbrdbDz30kFauXKn6+nqtXLlS
v//971VfX6977rlHq1atanJ7A+77AAAgGFAUQqM+/fRTrVy5Ul26dJEkHThwQK+99pri4uIkSVVV
Vbrtttt01113qaqqSgcOHFC3bt10+PBhTZw4UdHR0d6ROREREXryySeVkJBw1jleeuklXX/99erb
t6/69Omjhx56SDt37tQdd9whh8Ph3a+mpkbx8fEaPHiwPvzwQ0VGRqqgoEC7d+/W3r179cUXX+jo
0aPasGGDbDZbq/OsWbNG7777rux2u55//nlFR0crJyfHe36Hw6Err7xS8fHx3m2VlZXKy8tTt27d
9Ic//MG7/eDBg5o0aZK3cPXNN98oJydH9fX1OnnypC666CINGTJEXbt21QMPPOAttL322msaM2aM
3G63Jk+eLLvdrn/84x8aMGCAoqKiFB0dra+++kpZWVn66quvdPHFFyshIUH9+/fvyLcdAExt165d
2rZtm/73f/9XJ0+eVGVlperq6vTss896+ytJmjVrlv75z39q48aNmjJlikpLS/Xwww/rueee0003
3aSdO3fqpptu0gMPPOAdDRoREaGUlBRJUnR0tNxutyTp73//u5KTk70fjjgcDu3du1cHDhxodHtE
RAT3fQAAEDQoCqFRYWFhuvfeezV69GhJ0gsvvKBBgwZp2LBhkqRXXnlFXbt2lSQVFRXJ4XDo4MGD
OnjwoBYvXixJ2rp1q6644gqdPHlSmzZtUmpqqjp37izp9Ce5DodDt912m6TTn6g+9NBDys3NVWFh
oW644QaNHz9effr0UWxsrI4fP66dO3eqe/fuOn78uCIiIlRYWKjHHnvMOwKo4VPi1uTZtm2bNm7c
KLvdLun0XEQ//OEPz7oW1dXVys/P169//Wvvfg6HQxkZGZo8efJZ+65du1b9+vXzft29e3e9+uqr
2rRpkw4dOqTU1FR99NFH2rp1qz744ANJpx9f+N3vfqfU1FRFR0drzZo1Wrt2rXr27KnLLrtMhmFo
7969uuOOO3TNNdfowQcf1KJFi7yjuADAKi699FIVFRXpiy++UFVVla644gq98cYb5+xns9mUnJys
d999V0eOHNHJkye1c+dO3X///QoPD9evfvUrLV++XAsXLvTOOxQZGak77rhD0ul55oYMGSLp9MjY
Hj16eI/9wx/+UHv37tW+ffsa3T5ixAju+wAAIGhQFEKjznxU7Hz279+vfv366dtvv1X37t1VW1ur
KVOm6MILL5QkvfHGG9q7d69+85vfqHPnzjp+/Lg2bdqknj176vXXX9ftt9+ugwcPqmvXrurUqZOu
u+469ejRQxs3blSfPn109OhRzZ07V926dfOe8w9/+IP309z25klJSdHll1+uzp07a926derSpYvS
0tIkSS+++KKuueYa9erV65zzGIbRqut55MgRlZeX6/LLL9fQoUM1aNAgb4Hp4MGD+u1vf6tOnTrp
8OHDqqio0KRJk7R48WLdcsstOnbsmGJjY/X3v/9dkuTxePjDAIBlPfDAA+rUqZN27NihqKgo1dXV
aerUqQoP/++vNA3F/bvvvltvvfWWrr76aj377LN68sknJZ0ecZSdnS3DMPTVV1/p9ddf1wUXXCBJ
2rhxo4qKirRw4UJJ0rFjx/SDH/zAe+yoqCgdO3asye0NuO8DAIBgQFEIjaqvr9fy5cv14osvSjr9
+Fh0dPRZj4/NnDlTsbGxGj16tD788ENJpyeBvvXWW/XLX/5ShYWFys7O1uzZs73D3evr672jjwYO
HCjp9LxCY8eO9RZfdu3apZtvvvms4w0cOFAJCQkyDENvvvmm6urq9Omnn+rf//63Pv30U++KMq3N
Y7fb1blzZ73yyit66qmn9KMf/Uhr166VJJ04cUKPPvqoRo8erWuuuUbDhg1TUlKSJOnkyZNat26d
3n//fRmG4R2ldPDgQT3yyCPe6/if//xHK1as0O7du/U///M/uuSSS/Tmm29q2bJl3j8m/v3vf2vC
hAmaOHGiTp06pVWrVmnlypWqqKjQl19+qfr6ev3hD3/Q4cOHdfjwYe9oKwCwos6dO+ubb77xLkDg
drtVWFh4VlHo9ddf9/579+7dSktL07333quoqCjNmDFDYWFhmjRpkq677rpzjj9y5EilpKTovvvu
0/PPP68LLrjA+yiZdLpvuOCCC1RTU9Podu77AAAgmFAUQqMuvPBCPffcc+rTp48k6be//a3+3//7
f97Hx7Zt26b4+Hhvkej7vvvuO+3evfuc7TExMaqurtbEiRN1wQUXyGazad++ffroo4+8q4h17txZ
Tz75pGJiYmSz2fTNN9/oueee06WXXqrbb79dkjRo0CBddtll6tKliy677DJvoam1eQ4ePKiysjJd
ddVV+tvf/qaFCxdq6tSpuuiii1RaWqp9+/YpKSlJb731lkaOHOl9Xc+ePTVv3jz96Ec/0rp165Sa
mqqBAwfqwIEDZ/3ybrfbddNNN+no0aM6dOiQd9udd96pn/70p5KkDRs2eFe4ueiii/TMM8/ozTff
1PTp0xUXF6c333xT4eHhSklJ0YMPPtjoRNsAYAWGYai+vl5r167VvffeK+n0KJozC0KSdNNNN+mb
b77R9u3bdfLkSUnSBRdcoI0bN+rHP/6xtm7dqqNHj2r//v26+OKLJZ3+0OKrr75S3759vR+C7Ny5
U71799Z7773nPfa3336r3r17Kzw8vNHt3PcBAEAwadkzQrCcoUOHegtCjbn88svPeqyqvr5e0ul5
Eux2u3bt2uUdVRMVFeX9viQlJCRo1apVuvvuu1VYWKhbbrlFTzzxhFauXKmePXtq2bJl3tVWbDab
unfvri1btujqq69WVlaWJGns2LGKjo5WeHi4PB6Pd1nf1uZJTExUamqqunfvrpMnT6qmpsa7itmh
Q4d04YUXatiwYZo3b553DqWKigrt3r1bFRUV+vrrrzVx4kStWbNGknT06FE999xzevnllyWdLoJ9
f6WzsLAweTweHT9+XMePH1dtbe1Z3+/SpYuio6NVVlamGTNm6JprrpF0ehLUsrKys+YsAgArqaur
0/r167Vz505FRUXpyJEj58wD1+Ciiy7S5s2bvff+/fv3q7S01NuPpKamauHChd7Cza5du5Sfn+99
/eHDh3XxxRcrJSVFX3zxhQzD0KlTp1RbW6uePXs2uZ37PgAACCYUhdAiDZ/ONqWurk7S6YmVs7Oz
tWHDBl133XX6v//7P3Xp0sU7kWeDiy++WK+99preffdd77bi4mL94he/OGvlsYa5e+Lj48/5Jfrk
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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[48]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Plot as time series</span>
<span class="n">axes</span><span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s2">&quot;指标名称&quot;</span><span class="p">,</span> <span class="n">kind</span><span class="o">=</span><span class="s1">&#39;line&#39;</span><span class="p">,</span> <span class="n">subplots</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">grid</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">layout</span><span class="o">=</span><span class="p">(</span><span class="mi">4</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">10</span><span class="p">))</span>
<span class="n">SetFont</span><span class="p">(</span><span class="n">axes</span><span class="p">,</span> <span class="n">plt</span><span class="o">.</span><span class="n">gcf</span><span class="p">(),</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">8</span><span class="p">,</span> <span class="n">fontname</span><span class="o">=</span><span class="s1">&#39;c:</span><span class="se">\\</span><span class="s1">windows</span><span class="se">\\</span><span class="s1">fonts</span><span class="se">\\</span><span class="s1">simsun.ttc&#39;</span><span class="p">,</span> <span class="n">items</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;legend&quot;</span><span class="p">,</span> <span class="s2">&quot;xlab&quot;</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
zAAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># A lot of features seems to be higly correlated. Do a correlation matrix</span>
<span class="kn">from</span> <span class="nn">pandas.plotting</span> <span class="k">import</span> <span class="n">scatter_matrix</span>
<span class="n">sns</span><span class="o">.</span><span class="n">set_style</span><span class="p">(</span><span class="n">style</span><span class="o">=</span><span class="s2">&quot;white&quot;</span><span class="p">,</span> <span class="n">rc</span><span class="o">=</span><span class="kc">None</span><span class="p">)</span>
<span class="c1"># do correlation those columns</span>
<span class="n">headers</span> <span class="o">=</span> <span class="p">[</span><span class="sa">u</span><span class="s1">&#39;中债国债到期收益率:3个月&#39;</span><span class="p">,</span><span class="sa">u</span><span class="s1">&#39;中债国债到期收益率:10年&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;沪深300指数&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;中债总指数&#39;</span><span class="p">]</span>
<span class="n">axes</span><span class="o">=</span> <span class="n">scatter_matrix</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="n">headers</span><span class="p">],</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">9</span><span class="p">,</span><span class="mi">9</span><span class="p">))</span>
<span class="n">SetFont</span><span class="p">(</span><span class="n">axes</span><span class="p">,</span> <span class="n">plt</span><span class="o">.</span><span class="n">gcf</span><span class="p">(),</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">fontname</span><span class="o">=</span><span class="s1">&#39;c:</span><span class="se">\\</span><span class="s1">windows</span><span class="se">\\</span><span class="s1">fonts</span><span class="se">\\</span><span class="s1">simsun.ttc&#39;</span><span class="p">,</span> <span class="n">items</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;ylab&quot;</span><span class="p">,</span> <span class="s2">&quot;xlab&quot;</span><span class="p">])</span>

<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Ideas-for-forecasting-this-time-series-with-4-selected-features">Ideas for forecasting this time series with 4 selected features<a class="anchor-link" href="#Ideas-for-forecasting-this-time-series-with-4-selected-features">&#182;</a></h3><ul>
<li>Can also do dimensionality reduction on the 10 features and select the first 4 PCs to train (perhaps for later)</li>
<li>Simple ARIMA model for forecasting</li>
<li>XGBoost with regression</li>
<li>Deep neural network using RNN / (GRD / LSTM)</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="XGBoost-regression">XGBoost regression<a class="anchor-link" href="#XGBoost-regression">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[38]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Taking only these features</span>
<span class="n">headers</span> <span class="o">=</span> <span class="p">[</span><span class="sa">u</span><span class="s1">&#39;中债国债到期收益率:3个月&#39;</span><span class="p">,</span><span class="sa">u</span><span class="s1">&#39;中债国债到期收益率:10年&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;沪深300指数&#39;</span><span class="p">,</span> <span class="sa">u</span><span class="s1">&#39;中债总指数&#39;</span><span class="p">]</span>
<span class="n">df_sub</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">headers</span><span class="p">]</span>
<span class="n">X1_train_mat</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">asarray</span><span class="p">(</span><span class="n">df_sub</span><span class="p">)</span>
<span class="n">y1_train_mat</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">asarray</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;Y&quot;</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[45]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Separating data into X_train, y_train, X_val, y_val</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="k">import</span> <span class="n">TimeSeriesSplit</span>
<span class="n">tscv</span> <span class="o">=</span> <span class="n">TimeSeriesSplit</span><span class="p">(</span><span class="n">n_splits</span><span class="o">=</span><span class="mi">50</span><span class="p">)</span> <span class="c1"># for 10 folds of crossvalidation</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[48]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Start with a simple xgboost, ignoring the time information and see what it does</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="k">import</span> <span class="n">mean_squared_error</span>
<span class="kn">from</span> <span class="nn">xgboost</span> <span class="k">import</span> <span class="n">XGBRegressor</span>
<span class="n">accuracy_scores_list</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">xgb_reg</span> <span class="o">=</span> <span class="n">XGBRegressor</span><span class="p">()</span>
<span class="k">for</span> <span class="n">epoch</span><span class="p">,</span> <span class="p">(</span><span class="n">train_index</span><span class="p">,</span> <span class="n">test_index</span><span class="p">)</span> <span class="ow">in</span> <span class="nb">enumerate</span><span class="p">(</span><span class="n">tscv</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="n">X1_train_mat</span><span class="p">)):</span>
    <span class="c1"># Get data</span>
    <span class="n">X_train</span><span class="p">,</span> <span class="n">X_test</span> <span class="o">=</span> <span class="n">X1_train_mat</span><span class="p">[</span><span class="n">train_index</span><span class="p">],</span> <span class="n">X1_train_mat</span><span class="p">[</span><span class="n">test_index</span><span class="p">]</span>
    <span class="n">y_train</span><span class="p">,</span> <span class="n">y_test</span> <span class="o">=</span> <span class="n">y1_train_mat</span><span class="p">[</span><span class="n">train_index</span><span class="p">],</span> <span class="n">y1_train_mat</span><span class="p">[</span><span class="n">test_index</span><span class="p">]</span>
    <span class="c1"># Train the XGBoost</span>
    <span class="n">xgb_reg</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    <span class="n">y_pred</span> <span class="o">=</span> <span class="n">xgb_reg</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>
    <span class="n">acs</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">mean_squared_error</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span>
    <span class="c1">#print(&quot;RMSE:&quot;, acs)</span>
    <span class="n">accuracy_scores_list</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">acs</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">accuracy_scores_list</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>[0.05574110536573941, 0.016619024135980067, 0.033881089297445995, 0.013101490564228898, 0.007774167837661698, 0.008569569113488041, 0.005166861410345484, 0.007832514961462039, 0.10005812582163125, 0.058317227561839116, 0.2211929768332808, 0.014995624191141943, 0.008868785821808294, 0.008205008667429285, 0.00576499377245283, 0.00802906259572069, 1.2052946434474727, 0.8126311930967228, 0.15654579347225767, 1.750743392239421, 0.044947404216504394, 0.21488408349684798, 0.2582022184042565, 0.042088168768110695, 0.026614885513594116, 0.01723346169905295, 0.008961623272351706, 0.005099523525062128, 0.00442548052878379, 0.017016211342525782, 0.009355822744739896, 0.0065087937224623344, 0.004312519221825024, 0.013912412268863143, 0.01962128467142125, 0.02687753017935029, 0.019629388004812065, 0.01798221459584771, 0.015101587288185747, 0.01878468314918182, 0.017443180140183975, 0.019159339317003296, 0.018499472288233895, 0.02056343811438474, 0.012219307694427372, 0.016117898906048884, 0.0048321426922448155, 0.03204277687340917, 0.011639229400366083, 0.005903663363517704]
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[110]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">accuracy_scores_list</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[110]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>0.1089862479122226</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[51]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">xgboost</span> <span class="k">as</span> <span class="nn">xgb</span>
<span class="n">xgb</span><span class="o">.</span><span class="n">plot_importance</span><span class="p">(</span><span class="n">xgb_reg</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAeoAAAFlCAYAAAAki6s3AAAABHNCSVQICAgIfAhkiAAAAAlwSFlz
AAALEgAACxIB0t1+/AAAIABJREFUeJzt3XtUVWX+x/HPEcEbouIgmsdamZcpGa1U0l9ZmuM1DTOb
vIRlWWpZmXlLE9SgpLS8VepklzFaZnnLZgrFyq5aUVo0YXkrUeKiqYggcHh+f7A8RagxM2zOE+f9
Wsu1zn724Tzf/VXXh2efffZxGWOMAACAlWr4ugAAAHB2BDUAABYjqAEAsBhBDQCAxQhqAAAsRlAD
AGAxghr4H7Vt21YDBw5UVFSU98+MGTP+69f76quvFBMTU4kVlrVlyxbFxcU59vpnc+DAAd17771V
Pi/wR1fT1wUA1cFLL72k0NDQSnmt3bt3KzMzs1Je60x69uypnj17Ovb6Z3Po0CHt27evyucF/uhc
3PAE+N+0bdtWn3zyyRmDes+ePYqPj9fRo0fl8XgUHR2tIUOGqKSkRI8++qh27typvLw8GWMUFxen
8847T8OGDVNubq569+6tQYMG6ZFHHtGbb74pSdq+fbt3e/HixdqxY4eysrLUtm1bzZs3T88++6w2
bdqkkpISNW/eXLGxsQoPDy9T09q1a5WUlKRly5YpOjpa7dq107Zt23T48GGNHDlShw8f1qeffqr8
/HwtWLBAbdu2VXR0tC666CKlpqbq559/VlRUlO677z5JUnJyspYsWSKPx6Pg4GA99NBDat++fZn6
Wrdura+//lqZmZnq3LmzVqxYoaVLlyo5OVmnTp1Sfn6+pk6dql69emnx4sU6ePCgsrOzdfDgQYWG
huqpp55SeHi49u3bp5iYGB05ckQ1atTQuHHj1L9/f2VmZmrOnDnKyMhQUVGRrrvuOo0dO9b5v3yg
KhgA/5M2bdqYAQMGmOuvv977JycnxxQVFZn+/fub1NRUY4wxx48fN/369TNffvml+eKLL8y9995r
PB6PMcaYZcuWmTFjxhhjjFmzZo256667jDHGbNu2zVx33XXeuX69vWjRItOnTx9TVFRkjDFm3bp1
ZsKECd7tVatWmdGjR5er99evf8stt5jx48cbY4zZsWOHadOmjdmyZYsxxpj4+Hjz8MMPe5935513
msLCQnPs2DHTp08f884775jdu3eb//u//zM//vijMcaYjz/+2Fx55ZUmNze3XH2/rj09Pd1ER0eb
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
jhypHTt2+F0vPvzwQ7Vp00b33HOPxo4dq+7du/tdD06zJqhPnDjhPc0jSQEBASouLvZhRc7r06eP
atb85d0HY4xcLpckqV69esrNzdWJEydUv35973Pq1aunEydOVHmtTqlXr56Cg4N14sQJ3XfffZow
YYJf9kGSatasqalTp+qRRx7RwIED/a4Pa9euVWhoqPcXdsk//09IUu3atXXHHXdoxYoVmj17tiZN
muR3vfj555+VmpqqhQsX+m0PTrMmqIODg5WXl+fdLikpKRNi/qBGjV/+OvLy8hQSElKuL3l5eWX+
UVYHGRkZGjlypKKiojRw4EC/7YNUuqJMSkrSzJkzderUKe+4P/RhzZo1+vjjjxUdHa1vv/1WU6dO
1ZEjR7z7/aEHp1144YW6/vrr5XK5dOGFF6phw4Y6fPiwd78/9KJhw4a66qqrFBQUpJYtW6pWrVrK
zc317veHHpxmTVBffvnlev/99yVJO3bsUJs2bXxcUdW75JJLtH37dknS+++/r06dOql9+/ZKSUnR
qVOnlJubqz179lSr3uTk5Oj222/X5MmTNWTIEEn+2Yf169dr2bJlkqQ6derI5XIpIiLCr/qQmJio
l19+WStXrtTFF1+shIQEXX311X7Vg9Nef/11zZ07V5KUmZmpEydO6Morr/SrXnTs2FEffPCBjDHK
zMxUfn6+unbt6lc9OM2aW4ievur7u+++kzFGjz76qC666CJfl+W49PR0TZw4UatXr9a+ffs0c+ZM
FRUVqWXLloqLi1NAQIBWr16tV199VcYYjRkzRn369PF12ZUmLi5Ob731llq2bOkdmzFjhuLi4vyq
DydPntRDDz2knJwcFRcX684779RFF13kd/8eTouOjtasWbNUo0YNv+xBYWGhHnroIR06dEgul0uT
Jk1So0aN/K4Xjz/+uLZv3y5jjB544AG53W6/64FkUVADAIDyrDn1DQAAyiOoAQCwGEENAIDFCGoA
ACxGUAMAYDH/uqMIUE2lp6erb9++5T7SuHTpUjVr1sxHVQGoDAQ1UE00adJEGzZs8HUZACoZQQ34
kY0bN+q5555TQECA3G63nnjiCQUFBWnevHlKTk5WQECAbr75Zt16663at2+fYmJidPToUdWtW1cz
ZsxQ+/btNW3aNB09elQ//PCDJk+erD/96U967LHHVFBQoEaNGmn27Nlq0aKFrw8VqDYIaqCayMrK
UlRUlHd74MCBGj16dJnnLFiwQKtXr1bjxo311FNPae/evdq/f7+++OILbdy4UUVFRRo+fLj69++v
yZMn6678PA4fAAAB1UlEQVS77lLv3r21Y8cO3X///UpKSpJUeh/mpUuXqrCwUEOGDNHSpUt13nnn
6YMPPtDMmTP14osvVuWhA9UaQQ1UExU59d2jRw8NGzZMPXv2VJ8+fXTxxRfrtddeU79+/RQUFKSg
oCBt2LBBeXl5+vHHH9W7d29JpV8926BBA+3du1eS1L59e0nS/v37deDAAY0bN847R3X75iLA1whq
wI88/PDDSktL09atWzV58mSNHz++3LfUpaenq0GDBvrt3YWNMfJ4PJJKv4ZRKr1Hv9vt9v6C4PF4
lJOTUwVHAvgPPp4F+Ini4mL17t1bjRo10pgxYxQVFaVvv/1WnTt31ubNm1VUVKT8/HyNHj1aOTk5
atGihTZt2iSp9BvtcnJy1Lp16zKv2bJlSx07dkyff/65pNKvqpw0aVKVHxtQnbGiBvxEzZo1dd99
92nUqFGqXbu2QkJClJCQoPDwcKWmpmrw4MEqKSnRyJEjdeGFF+qJJ57QrFmztHjxYgUGBmrx4sUK
Cgoq85pBQUFauHCh4uPjderUKQUHByshIcFHRwhUT3x7FgAAFuPUNwAAFiOoAQCwGEENAIDFCGoA
ACxGUAMAYDGCGgAAixHUAABYjKAGAMBi/w8yFTkw4qcJNgAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[59]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Plot prediction vs. actual data</span>
<span class="n">y1_pred_all</span> <span class="o">=</span> <span class="n">xgb_reg</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X1_train_mat</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">plot_date</span><span class="p">(</span><span class="n">X1_train</span><span class="p">[</span><span class="sa">u</span><span class="s1">&#39;指标名称&#39;</span><span class="p">],</span> <span class="n">y1_train_mat</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;#1f77b4&#39;</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s2">&quot;original&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot_date</span><span class="p">(</span><span class="n">X1_train</span><span class="p">[</span><span class="sa">u</span><span class="s1">&#39;指标名称&#39;</span><span class="p">],</span> <span class="n">y_pred_all</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;#ff7f0e&#39;</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s2">&quot;predicted&quot;</span><span class="p">,</span> <span class="n">alpha</span><span class="o">=</span><span class="mf">0.2</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">&quot;Year&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">&quot;Y1&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
AAAAAElFTkSuQmCC
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[70]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Make predictions using the trained XGBoost Regressor</span>
<span class="n">X1_test</span> <span class="o">=</span> <span class="n">X_test_original</span><span class="p">[[</span><span class="sa">u</span><span class="s1">&#39;指标名称&#39;</span><span class="p">]</span> <span class="o">+</span> <span class="n">headers</span><span class="p">]</span>
<span class="n">X1_test</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>
<span class="c1"># has some missing data. Need to later fit with spline</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[70]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>指标名称               0
中债国债到期收益率:3个月    259
中债国债到期收益率:10年    259
沪深300指数          275
中债总指数            260
dtype: int64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[84]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Fit the features with spline</span>
<span class="n">X1_test_filled</span> <span class="o">=</span> <span class="n">X1_test</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>
<span class="n">X1_test_filled</span><span class="p">[</span><span class="n">headers</span><span class="p">]</span> <span class="o">=</span> <span class="n">X1_test_filled</span><span class="p">[</span><span class="n">headers</span><span class="p">]</span><span class="o">.</span><span class="n">interpolate</span><span class="p">(</span><span class="n">method</span><span class="o">=</span><span class="s2">&quot;cubic&quot;</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>

<span class="n">X1_test_filled</span><span class="p">[</span><span class="n">headers</span><span class="p">]</span> <span class="o">=</span><span class="n">X1_test_filled</span><span class="p">[</span><span class="n">headers</span><span class="p">]</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">method</span><span class="o">=</span><span class="s2">&quot;bfill&quot;</span><span class="p">)</span>
<span class="n">X1_test_filled</span><span class="p">[</span><span class="n">headers</span><span class="p">]</span> <span class="o">=</span><span class="n">X1_test_filled</span><span class="p">[</span><span class="n">headers</span><span class="p">]</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">method</span><span class="o">=</span><span class="s2">&quot;ffill&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[87]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Plot as time series</span>
<span class="n">axes</span><span class="o">=</span> <span class="n">X1_test</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s2">&quot;指标名称&quot;</span><span class="p">,</span> <span class="n">kind</span><span class="o">=</span><span class="s1">&#39;line&#39;</span><span class="p">,</span> <span class="n">subplots</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">grid</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">layout</span><span class="o">=</span><span class="p">(</span><span class="mi">4</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">10</span><span class="p">))</span>
<span class="n">SetFont</span><span class="p">(</span><span class="n">axes</span><span class="p">,</span> <span class="n">plt</span><span class="o">.</span><span class="n">gcf</span><span class="p">(),</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">8</span><span class="p">,</span> <span class="n">fontname</span><span class="o">=</span><span class="s1">&#39;c:</span><span class="se">\\</span><span class="s1">windows</span><span class="se">\\</span><span class="s1">fonts</span><span class="se">\\</span><span class="s1">simsun.ttc&#39;</span><span class="p">,</span> <span class="n">items</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;legend&quot;</span><span class="p">,</span> <span class="s2">&quot;xlab&quot;</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">suptitle</span><span class="p">(</span><span class="s2">&quot;Original&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>

<span class="n">axes</span><span class="o">=</span> <span class="n">X1_test_filled</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s2">&quot;指标名称&quot;</span><span class="p">,</span> <span class="n">kind</span><span class="o">=</span><span class="s1">&#39;line&#39;</span><span class="p">,</span> <span class="n">subplots</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">grid</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">layout</span><span class="o">=</span><span class="p">(</span><span class="mi">4</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">10</span><span class="p">))</span>
<span class="n">SetFont</span><span class="p">(</span><span class="n">axes</span><span class="p">,</span> <span class="n">plt</span><span class="o">.</span><span class="n">gcf</span><span class="p">(),</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">8</span><span class="p">,</span> <span class="n">fontname</span><span class="o">=</span><span class="s1">&#39;c:</span><span class="se">\\</span><span class="s1">windows</span><span class="se">\\</span><span class="s1">fonts</span><span class="se">\\</span><span class="s1">simsun.ttc&#39;</span><span class="p">,</span> <span class="n">items</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;legend&quot;</span><span class="p">,</span> <span class="s2">&quot;xlab&quot;</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">suptitle</span><span class="p">(</span><span class="s2">&quot;Filled&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
oVMyAAAAAElFTkSuQmCC
"
>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[96]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">X1_test_filled_mat</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">asarray</span><span class="p">(</span><span class="n">X1_test_filled</span><span class="p">[</span><span class="n">headers</span><span class="p">])</span>
<span class="n">Y1_pred</span> <span class="o">=</span> <span class="n">xgb_reg</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X1_test_filled_mat</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[109]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">plot_date</span><span class="p">(</span><span class="n">X1_test_filled</span><span class="p">[</span><span class="s2">&quot;指标名称&quot;</span><span class="p">],</span> <span class="n">Y1_pred</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">&quot;Time&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">&quot;Y1_Predicted_XGBoost&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s2">&quot;./results/Y1_prediction_XGBoostReg.png&quot;</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">&#39;tight&#39;</span><span class="p">,</span> <span class="n">dpi</span><span class="o">=</span><span class="mi">300</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
p07ZElw4Uco6iYjIXhky1VdZldWfbBJQXl6OkpIS77oBhw4dwl133YURI0agtLTUtgDDBbNOIiLn
kKu+yqqs/mS7A9auXYvnnnvOu6xvXFwcRo0ahe985zu46aabbAswXMgtJsSsk4jIfmI3LKuyKpNN
AgRB8CYAALwX/oSEBMTFxVkfWZiRW0yIWScRUWiwKmtwsklAe3s72traEB8fDwCYM2cOAOCrr75C
R0eHPdGFEWadREQUbmSTgGuuuQYrVqzAkiVLEBMTA6CrdWDVqlW45pprbAswnDDrJCKicCKbBNx9
99246667kJeXh+985ztwuVyorq7GRRddhKeeesrOGImIiMgCsklAUlISnn32WVRVVeGf//wnAGD2
7Nm44oorbAuOiIiIrCObBOzfvx/Dhw9HTk4OcnJy/J7bsGEDZsyYYXlwREREWihVbmVV1+5kk4CF
Cxdi1qxZmDt3rvexM2fO4P7778cXX3zBJICIiBxFqXIrAFZ1lSBbLOill17C+++/j/nz56O+vh7v
vvsuJk+ejMzMTLzyyit2xkhERBSUUuVWVnWVJtsS0KtXLzz99NN47rnnMGHCBMTFxaG4uBhXXnml
nfERERGpolS5VZDZJtqruiquHfCvf/0LL7/8MsaOHYuUlBS88847aGtrsys2IiIi1ZTWC+BaAtJk
k4CnnnoK8+fPxz333INHH30Ur7zyChoaGnDzzTfj4MHobj4hIiLnUVovgGsJSJPtDvjHP/6BjRs3
on///gCA5ORkrFy5Elu2bMGtt96K3bt32xYkERFRMGoqt7Kqqz/ZJOD555+XfHzKlCneKYNPPvkk
FixYYElgREREWilVbmVV1+4UxwTIycjIAAC8/fbbpgZDRERE9tGVBIgEQW68JRERETmdoSTA5XKZ
FQcRERHZzFASQEREROGLSQAREVGUkp0doMbQoUPNioOIiMiQ0k3VeGN3DTo9XePVUpLj8P2R6dh3
6DSOnGhAbIwbHZ0eZA5I5fTAr8kmAb/85S8VN3zkkUewevVq0wMiIiLSqnRTNbbuPOz3WGNLu99j
7R0eAFw8yJdsd8CoUaMwatQoNDc347///S/GjBmDcePGoaGhgbMCiIjIUd784IjmbaJ98SBAoSVg
2rRpAIAXX3wRL730Etzurnzh+uuvx/Tp0+2JjoiISAXxLl+LaF88CFAxJqCxsRH19fXo06cPAODU
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
KgAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[98]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Writing the Y1 prediction to csv</span>
<span class="n">Y1_pred_df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">({</span><span class="s2">&quot;Date&quot;</span><span class="p">:</span><span class="n">X1_test_filled</span><span class="p">[</span><span class="s2">&quot;指标名称&quot;</span><span class="p">],</span> <span class="s2">&quot;Y1&quot;</span><span class="p">:</span><span class="n">Y1_pred</span><span class="p">})</span>
<span class="n">Y1_pred_df</span><span class="o">.</span><span class="n">to_csv</span><span class="p">(</span><span class="s2">&quot;./results/Y1_prediction_XGBoostReg.csv&quot;</span><span class="p">,</span> <span class="n">index</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">sep</span><span class="o">=</span><span class="s2">&quot;</span><span class="se">\t</span><span class="s2">&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[112]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># save the model</span>
<span class="kn">import</span> <span class="nn">pickle</span>
<span class="n">pickle</span><span class="o">.</span><span class="n">dump</span><span class="p">(</span><span class="n">xgb_reg</span><span class="p">,</span> <span class="nb">open</span><span class="p">(</span><span class="s2">&quot;./results/XGBoostReg_y1.model&quot;</span><span class="p">,</span> <span class="s2">&quot;wb&quot;</span><span class="p">))</span>

<span class="c1">#loaded_model = pickle.load(open(&quot;./results/XGBoostReg_y1.model&quot;, &quot;rb&quot;))</span>
</pre></div>

    </div>
</div>
</div>

</div>
    </div>
  </div>
</body>




</html>

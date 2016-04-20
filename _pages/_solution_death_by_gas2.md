<!DOCTYPE html>
<html>
<head>

  <script src="{% jquery 1.10.2 %}"></script>
  {% common_header %}
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <!-- Bootstrap core CSS -->
  <link href="{% asset_path css/bootstrap/3.1.1/css/bootstrap.min.css %}" rel="stylesheet" type="text/css">
  <link rel="stylesheet" href="//netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.min.css">
  <link href="//d1y0v6ricksqp.cloudfront.net/themes/viralrewards/bootstrap-cls.css" rel="stylesheet">

  <!-- Loading custom fonts -->
  {% load_custom_fonts %}

  <script src="{% kol_submit_response %}"></script>
  <script src="{% kol_external %}"></script>
  <script>
  jQuery(document).ready(function(){
    new KOLValidation("{{content.validation_failed_message}}");
  });
  </script>
  <!-- Add custom CSS here -->
  <style>

  body {
    color: {{content.text_color}};
    background-color: {{content.background_color}};
    {{ content.body_font | font_family}}
  }

  img {
    display: inline-block;
    height: auto;
    max-width: 100%;
  }
  .fr-fin {
    width: 200px;
  }

  div embed,
  div object,
  div iframe,
  p embed,
  p object,
  p iframe {
    max-width:100% !important;
  }

  h1, h2, h3, h4, h5, h6{
    {{ content.headline_font | font_family}}

  }

  a{
    color:{{content.link_color}};
  }

  a:hover{
    color:{{content.link_color | darker_color}};
  }

  .top-row{
    padding:10px 0;margin-top:10px;
  }
  .top-row .signin{
    display:inline-block;
    text-align:right;
    float:right;
  }
  .banner{
    width:100%;
  }
  .backstretch{
    opacity:0.5;
  }
  .top_right{
    margin-top:10px;
  }
  .banner.thanks-banner,
  .banner{
    color:{{content.header_text_color}};
    background-size: cover;
  }
  .banner h1, .banner h2, .banner h3,.banner h4,.banner h5,.banner h6{
    color:{{content.header_text_color}};
    {{ content.headline_font | font_family}}
  }
  .banner h1{
    text-align:center;
    {{ content.title_font | font_family}}
  }
  .banner p{
    color:{{content.header_text_color}};
    font-size:25px;
    text-align:center;
    line-height:150%;
    padding:0px 0 10px;
    margin:0px;
    font-family: {{ content.body_font | font_family}}
  }
  .img-overlay {
    padding:100px 0;
    background-color: {{ content.header_background_color }};
    {% case content.header_background_transparency %}
    {% when '1' %}
    opacity: 1;
    {% when '.9' %}
    opacity: 0.9;
    {% when '.8' %}
    opacity: 0.8;
    {% when '.7' %}
    opacity: 0.7;
    {% when '.6' %}
    opacity: 0.6;
    {% when '.5' %}
    opacity: 0.5;
    {% when '.4' %}
    opacity: 0.4;
    {% when '.3' %}
    opacity: 0.3;
    {% when '.2' %}
    opacity: 0.2;
    {% when '.1' %}
    opacity: 0.1;
    {% when '0' %}
    opacity: 0;
    {% endcase %}
  }
  .banner .navbar-form{display:block; text-align:center;}
  .footer_banner{background:#e2e2e2; color:#272727; border:none;}

  .footer_banner h2{font-size: 38px; color:#272727;  text-align: center;}
  .footer_banner p{color:#272727;}
  .footer{background-color:{{content.footer_background_color}}; text-align:center; display:block; padding:50px 0; color:{{content.footer_text_color}};}

  .footer p a{color:{{content.footer_text_color}}; text-decoration:none;}
  .footer p a:hover{
    color:{{content.footer_text_color | darker_color}};
    text-decoration:none;
  }
  .nospace{padding-bottom:0px; margin:0px;}
  .section, .section-colored, .rewards-section{padding: 50px 0;}
  .longer-rewards h2 {
    margin-bottom: 3rem;
  }
  iframe {
    margin-bottom: 1rem;
  }
  .section-colored{background-color: {{content.prize_background_color}}; }
  .section-colored ul{margin:0; padding:0px; list-style-type:none; display:block; text-align:center;}
  .section-colored ul li{ margin:0px -5px 8px; padding:0px; display:inline-block; min-width:160px; max-width:160px;text-align:left; font-weight:bold; font-size:12px; vertical-align:middle;}
  .section-colored ul li:first-child, .reward-span{text-align:right; padding-right:30px;font-size:18px;}
  .banner .invite-btn{padding:15px 0 30px;}
  .banner-share .form-control{font-size:18px;}
  .banner-share .form-control::-moz-placeholder{color:#525252;}
  .banner-share p{font-size:22px;}
  .banner {
    position: relative;
    padding: 7em 0 8em;
    width: 100%;
    /*background-size: 100%;*/
  }
  .banner .img-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }


  .lime-green{color:{{content.referral_color}};}
  .img-placeholder h2{text-align:center; padding:65px 0; font-size:24px; }
  .img-placeholder p{text-align:center; padding:60px 0; font-size:16px;  clear:both;}
  .img-placeholder img{margin-bottom:20px;}
  .sm_device{display:none;}
  .circle-text {
    margin-right: -3px;
    width: 25%;
    float:left;
  }
  p.share_links{
    margin-bottom:20px;
  }
  .circle-text:after {
    content: "";
    display: block;
    width: 100%;
    height:0;
    padding-bottom: 100%;
    background: #a8a8a8;
    -moz-border-radius: 50%;
    -webkit-border-radius: 50%;
    border-radius: 50%;
  }
  .circle-text div {
    float:left;
    width:100%;
    padding-top:50%;
    line-height:1em;
    margin-top:-0.5em;
    text-align:center;
    color:white;
    font-size:18px;
  }
  .circle-first-text{
    margin-right: -3px;
    width: 25%;
    float:left;
  }
  .circle-first-text:after {
    content: "";
    display: block;
    width: 100%;
    height:0;
    padding-bottom: 100%;
    background:{{content.referral_color}};
    -moz-border-radius: 50%;
    -webkit-border-radius: 50%;
    border-radius: 50%;
  }
  .circle-first-text div {
    float:left;
    width:100%;
    padding-top:50%;
    line-height:1em;
    margin-top:-0.5em;
    text-align:center;
    color:white;
    font-size:18px;
  }

  .100_dollars_circle{
    margin-top:-6px;
  }
  .social{
    margin:10px;
  }
  .social a {
    background: {{content.link_color}};
    color:  {{content.link_color | font_color_from_background : '#FFFFFF', '#000000'}} !important;
    font-size: 1em;
    text-decoration: none;
    display: inline-block;
    width: 1.6em;
    height: 1.6em;
    line-height: 1.6em;
    text-align: center;
    margin-right: 5px;
    border-radius: 50%;
  }

  .form-inline{
    text-align:center;
    padding-top:10px;
  }

  .btn-primary, .btn-primary:focus {
    color: #fff;
    background-color: {{content.button_color}};
    border-color:{{content.button_color}};
    border-radius: 0px;
  }

  .form-control{
    border-radius:0px;
  }

  .fa{
    line-height:1.6;
  }

  .btn-primary:hover {

    background-color: {{content.button_color | darker_color}};
    border-color:{{content.button_color | darker_color}};
  }

  .section, .section-colored {
    padding-bottom: 0px;
  }

  .banner .btn{float: none;}


  .slider.slider-horizontal {
    width: 100%;
  }

  .slider.slider-vertical {
    height:400px;
    margin-left: auto;
    margin-right: auto;
    position:static;
  }

  .sm_device .row-friends-joined {
    margin-bottom:2rem;
  }

  .lg_device .row-rewards-texts,
  .lg_device .row-friends-joined {
    margin-right:0;
    padding-right:80px;
  }

  .lg_device .row-rewards-texts {
    margin-top:3rem;
  }

  .lg_device .row-rewards-texts,
  .lg_device .row-friends-joined {
    margin-left:-60px;
  }

  .row-main-label {
    margin:0 0 8px;
    display:block;
    font-size:18px;
    text-align:right;
    font-weight:bold;
    width:100%;
    vertical-align:middle;
  }

  .sm_device .row-friends-joined .left .row-main-label {

  }

  .sm_device .row-friends-joined .right .row-main-label {
    text-align:left;
  }

  .sm_device .slider-selection.tick-slider-selection {
    top:15px !important;
  }

  .slider-handle {
    display:none;
  }

  .slider-tick {
    height:40px;
    width:40px;
  }

  .slider-tick.round {
    padding-top:7px;
  }

  .slider-tick.round,
  .slider.slider-horizontal .slider-tick-label-container .slider-tick-label {
    color:#fff;
    font-size:18px;
    font-weight:600;
    text-align:center;
    vertical-align:middle;
  }

  .slider-selection.tick-slider-selection {
    background-image:none;
    background-color: {{content.referral_color}};
  }

  .slider.slider-horizontal .slider-top-label,
  .slider.slider-vertical .slider-top-label {
    color:#333;
    font-size: 14px;
    font-weight: normal;
    text-align:left;
    display:inline-block;
    position:absolute;
    min-width:99px;
  }

  .slider.slider-horizontal .slider-top-label {
    top:-30px;
    left:0;
  }

  .slider.slider-vertical .slider-top-label {
    left:115px;
    top:11px;
  }

  .slider.slider-horizontal .slider-tick-label-container .slider-tick-label {
    margin-left:-5px;
    position:relative;
  }

  .slider.slider-horizontal .slider-tick,
  .slider.slider-horizontal .slider-handle {
    margin-top:-15px;
  }

  .slider.slider-vertical .slider-tick,
  .slider.slider-vertical .slider-handle {
    margin-left:-15px;
    margin-top:-10px;

  }

  .slider-tick,
  .lg_device .slider-tick {
    background:#A8A8A8;
    opacity:1;
  }

  .lg_device .slider-tick.in-selection,
  .lg_device .slider-selection.tick-slider-selection,
  .sm_device .slider-tick.in-selection,
  .sm_device .slider.slider-vertical .slider-tick.in-selection .slider-tick-value {
    background:{{content.referral_color}};
  }
/*
  .slider-tick.round.in-selection > .slider-top-label {
    color:{{content.referral_color}};
  }
  */
  .reward-earned .panel,
  .reward-earned .reward-head-text {
    border-color:{{content.referral_color}} !important;
  }

  .slider-tick-label-container {
    margin-left:0px !important;
    width:98% !important;
  }

  .slider.slider-disabled .slider-track {
    cursor: default;
  }

  .inner-rewards {

  }

  .lg_device .slider-tick.round,
  .reward-head-text,
  .slider-tick-value {
    -webkit-border-radius:50%;
    -moz-border-radius:50%;
    -ms-border-radius:50%;
    -o-border-radius:50%;
    border-radius:50%;
  }

  .lg_device .row-rewards-texts .rewards-boxes div.col-sm-2,
  .lg_device .row-rewards-texts .rewards-boxes div.col-sm-3,
  .lg_device .row-rewards-texts .rewards-boxes div.col-sm-4,
  .lg_device .row-rewards-texts .rewards-boxes div.col-sm-6 {
    padding-left:5px;
    padding-right:0;
  }

  .lg_device .row-rewards-texts .rewards-boxes .panel-body {
    padding-top:2rem;
  }

  .sm_device .row-rewards-texts .rewards-boxes .panel-body {
    padding-left: 2rem;
    padding-top: 1rem;
  }

  .reward-head-text {
    background: none repeat scroll 0 0 #fff;
    border-color: #ddd;
    color: {{content.text_color}};
    display: block;
    font-weight: 600;
    height: 35px;
    padding-top: 6px;
    position: absolute;
    text-align: center;
    vertical-align: middle;
  }

  .lg_device .reward-head-text {
    width: 4rem;
    left: 6px;
    top: -13px;
    font-size: 18px;
    border-top: 3px solid #ddd;
  }

  .sm_device .reward-head-text {
    border-left: 3px solid #ddd;
    font-size: 16px;
    left: -2px;
    top: 5px;
    width: 3.7rem;
  }

  .reward-earned .panel,
  .reward-earned .reward-head-text {
    border-color:{{content.referral_color}};
  }

  {% if content.dynamic_spacing == 'false' %}
  .sm_device .reward-content {
    position: relative;
    z-index: 5;
  }

  .sm_device .slider-selection.tick-slider-selection {
    top:35px !important;
  }

  .slider.slider-vertical .slider-top-label {
    top:-9px;
  }

  .slider.slider-vertical .slider-tick,
  .slider.slider-vertical .slider-handle {
    margin-top:auto;
  }

  .sm_device .slider-tick,
  .sm_device .slider-tick.in-selection {
    background:none;
  }

  .sm_device .slider-tick .slider-tick-value {
    background:#A8A8A8;
  }

  .sm_device .reward-head-text {
    left: -5px;
  }

  .slider.slider-horizontal {
    height: 40px;
    left: -10px;
    overflow: hidden;
    position: relative;
    top: -5px;
  }

  .slider.slider-disabled .slider-track {
    left: 10px;
    position: absolute;
  }

  .lg_device .row-rewards-texts .rewards-boxes div.col-sm-2 {
    width:19.0417%;
  }

  .lg_device .slider.slider-horizontal.slider-track-2 {
    width: 460px;
  }

  .lg_device .slider.slider-horizontal.slider-track-2 .slider-track {
    width: 2100px;
  }

  .lg_device .slider.slider-horizontal.slider-track-3 {
    width: 600px;
  }

  .lg_device .slider.slider-horizontal.slider-track-3 .slider-track {
    width: 1400px;
  }

  .lg_device .slider.slider-horizontal.slider-track-4 {
    width: 670px;
  }

  .lg_device .slider.slider-horizontal.slider-track-4 .slider-track {
    width: 1050px;
  }

  .lg_device .slider.slider-horizontal.slider-track-5 {
    width: 680px;
  }

  .lg_device .slider.slider-horizontal.slider-track-5 .slider-track {
    width: 800px;
  }

  .slider.slider-vertical .slider-track {
    cursor: default;
    left: 50%;
    position: absolute;
    top:0;
  }

  .sm_device .rewards-boxes .reward-box {
    margin-bottom: 5rem;
  }

  .sm_device .slider-tick-label-container .slider-tick-label {


  }

  .sm_device .slider-tick {
    top: auto !important;
    left: auto !important;
    height:auto;
    width:auto;
    position:relative;
  }

  .slider.slider-vertical {
    width: 100%;
    height:auto !important;
    display:block;
  }

  .slider.slider-vertical .slider-top-label {
    max-width: 350px;
    min-width: 280px;
    position: relative;
    display: table;
    left:95px;
  }

  .slider.slider-vertical .slider-tick.in-selection {
    background: none;
  }

  .sm_device .row-rewards-texts .left {
    overflow: visible;
  }

  .slider.slider-vertical .slider-track {
    position:relative;
    left:20%;
    height: 100%;
  }

  .slider-tick-value {
    height: 40px;
    width: 40px;
    color: #FFF;
    position: absolute;
    top: 0px;
    padding-top: 6px;
  }

  .sm_device .slider-track-overlay {
    background: {{content.prize_background_color}};
    position:absolute;
    width:50px;
    bottom:0;
    left: -15px;
  }

  .slider-tick-0 {
    left:0 !important;
    top: 0 !important;
  }


  @media (min-width: 768px) and (max-width: 1199px) {

    .lg_device .slider.slider-horizontal.slider-track-2 {
      width: 385px;
    }

    .lg_device .slider.slider-horizontal.slider-track-2 .slider-track {
      width: 1726px;
    }

    .lg_device .slider.slider-horizontal.slider-track-3 {
      width: 501px;
    }

    .lg_device .slider.slider-horizontal.slider-track-3 .slider-track {
      width: 1153px;
    }

    .lg_device .slider.slider-horizontal.slider-track-4 {
      width: 557px;
    }

    .lg_device .slider.slider-horizontal.slider-track-4 .slider-track {
      width: 863px;
    }

    .lg_device .slider.slider-horizontal.slider-track-5 {
      width: 566px;
    }

    .lg_device .slider.slider-horizontal.slider-track-5 .slider-track {
      width: 657px;
    }
  }
  {% endif %}

  @media (min-width: 600px) {
    .form-control#email{width: auto; display: inline-block; vertical-align: middle;}
    .banner button.btn{width: 20% !important; display: inline-block; padding: 6px !important; margin-top: 0 !important; margin-bottom: 0;}
  }

  @media (min-width: 768px) {

    .banner h1 {
      font-size:4.5rem;
    }

    .sm_device {
      margin: 0 auto;
      width: 360px;
    }

    .sm_device .inner-rewards {
      padding:0 15px;
      width:270px;
    }

    .social_share_link{
      width:50px;
    }
  }

  @media (max-width: 999px) {
    .lg_device{display:none;}
    .sm_device{display:block;}
    .section-colored ul li{margin-bottom:0px; vertical-align:top;}
    .invite-frnd p{padding:0px 0 30px;}

    .progress {
      width:40%;
      height:10px;
      margin:15px auto 0;
      overflow: hidden;
      background-color: #e2e2e2;
      /*border-radius: 4px;*/
      -webkit-box-shadow: none;
      box-shadow: none;
      -webkit-transform: rotate(90deg);
      -moz-transform: rotate(90deg);
      -o-transform: rotate(90deg);
      -ms-transform: rotate(90deg);
      transform: rotate(90deg);
    }
    .circle-first-text{float:none; margin: 0 auto;}
    .circle-text{float:none; margin:0 auto; position:relative; z-index:99;}
    .section-colored ul li:first-child{padding-bottom:20px;}
  }

  @media (max-width: 767px) {
    .footer-text, #privacy_link {
      text-align: center;
      width:100%;
      margin-top:2rem;
    }
    .banner p{font-size: 0;}
    .banner .btn{ float: left;}
    .banner .btn:first-child, .banner .btn:nth-child(4){border-left: none;}
    .banner .btn:last-child, .banner .btn:nth-child(3){border-right: none;}
    .banner button.btn{margin-top: 12px; width: 100%; padding: 8px; float: none;}

    .banner h1 {
      font-size:28px;
    }

    .banner p {
      font-size:18px;
    }

    .sm_device {
      display: block;
      margin: 0 auto;
      width: 360px;
    }

    .sm_device .inner-rewards {
      padding:0 15px;
      width:270px;
    }

    .section .img-responsive{margin:0 auto;}
    .section-colored .img-responsive{margin:0 auto;}
    .section-colored ul li:first-child, .reward-span{padding-right:10px; min-width: 140px;}
  }
  @media (min-width: 600px) {
    .banner{
      background-image: url({{content.header_background_image}});
      background-position: 100% 50%;
    }
  }

  @media (max-width: 599px) {
    .banner {
      {% if content.header_image_on_mobile == "" %}
        background-image: url({{content.header_background_image}});
      {% elsif content.header_image_on_mobile != "" %}
        background-image: url({{content.header_image_on_mobile}});
      {% endif %}
      background-position: center center;
    }
  }
  @media (max-width:480px) {
    .slider.slider-vertical .slider-top-label {
      max-width: 300px;
      min-width: 220px;
      left: 90px;
    }

    .banner h1 {
      font-size:25px;
    }

    .banner p {
      font-size:16px;
    }

    .sm_device {
      width:100%;
    }

    .panel-default {
      margin-right: 0 !important;
    }

    .row-main-label {
      text-align: left;
    }
  }


  @media (max-width:400px) {

    .slider.slider-vertical .slider-track {
      left: 9%;
    }

    .slider.slider-vertical .slider-top-label {
      left: 90px;
      min-width: 220px;
    }
  }


  @media (max-width:360px) {

    .slider.slider-vertical .slider-top-label {
      left: 70px;
      min-width: 220px;
    }
  }


  @media (max-width:300px) {

    .slider.slider-vertical .slider-top-label {
      left: 60px;
      min-width: 200px;
    }
  }


  @media (max-width:260px) {

    .slider.slider-vertical .slider-top-label {
      left: 55px;
      min-width: 170px;
    }
  }


  .form-control[disabled], .form-control[readonly], fieldset[disabled] .form-control {
    cursor: auto;
    background-color: #FFF; */
    opacity: 1;
  }

  .common_thank_you_message{
    margin-bottom:20px;
  }


  .progress{
    height:10px;
    margin-top:16px;
    overflow: hidden;
    background-color: #e2e2e2;
    border-radius: 0px;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
  .progress-bar{
    float: left;
    width: 0;
    height: 100%;
    font-size: 12px;
    color: #ffffff;
    text-align: center;
    background-color: {{content.referral_color}};
    box-shadow: none;
  }

  .simple-share{
    text-align:center;
  }

  #referred{
    color:{{content.referral_color}};
    font-size: 36px;
  }

  #subscribe{
    text-align:center;
  }

  .invite-frnd{padding:45px 0 60px;}
</style>

{% integrations header %}
</head>
<body>
  <div class="banner header-banner">
    <div class="img-overlay"></div>
    <div class="container">
      <div id="top-container" class="col-md-10 col-md-offset-1">
        <!-- Logo -->
        {% if content.show_logo == true %}
        <div class="top_centered" data-mercury="froala" data-content-name="top_centered">{{ content.top_centered }}</div>
        {% endif %}
        <div id="subscribe" >
          <div class="common_thank_you_message" data-mercury="froala" data-content-name="top_thanks_message">
           {{content.top_thanks_message}}
         </div>
          {% if content.show_social_share_links == true %}
          <p id="share_links" class="share_links row"></p>

          {% if content.show_share_link == true %}
          <div class="row">
            <div class="col-sm-6 col-sm-offset-3">
              <div>
                <span id="kol-social-url">{{social_url}}</span>
              </div>
            </div>
          </div>
          {% endif %}
          <div class="share-link-text" data-mercury="froala" data-content-name="share_link_text">{{content.share_link_text}}</div>
          {% endif %}

        </div>

        <div id="kol_fade"></div>
      </div>
    </div>

  </div>

  <!-- request an invite -->

  <div class="section-colored invite-frnd">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 col-md-12 col-sm-12">
          <h4 style="text-align:center; margin-bottom:20px;"><span id="referred">0</span> {{content.friends_joined}}</h4>
          <div class="lg_device">

            <div class="row row-friends-joined">
              <div class="col-sm-3">
                <div class="row-main-label">{{content.friends}}</div>
              </div>
              <div class="col-sm-9">
                <input type="text" id="slider-track" style="display: none;" data="value:'0'" value="0" data-slider-enabled="false">
              </div>
            </div>
            <div class="row row-rewards-texts">

                <div class="col-sm-3">
                  <div class="row-main-label">{{content.reward_text}}</div>
                </div>
                <div class="col-sm-9">

                  <div class="row rewards-boxes">

                  {% assign num_levels = content.number_of_rewards_levels %}

                  {% for i in (1..num_levels) %}
                  {% assign prize_text = 'prize_text_' | append: i %}
                  {% assign prize_level = 'prize_level_' | append: i %}
                  {% assign col_class = 'col-sm-2' %}

                  {% if num_levels == 2 %}
                  {% assign col_class = 'col-sm-6' %}
                  {% endif %}

                  {% if num_levels == 3 %}
                  {% assign col_class = 'col-sm-4' %}
                  {% endif %}

                  {% if num_levels == 4 %}
                  {% assign col_class = 'col-sm-3' %}
                  {% endif %}

                  <div class="{{ col_class }} reward-box" data-rewardlevel="{{ content.[prize_level] }}">
                    <div class="panel panel-default">
                      <div class="panel-body">
                        <span class="reward-head-text">{{ content.[prize_level] }}</span>
                      {{ content.[prize_text] }}
                      </div>
                    </div>
                  </div>
                  {% endfor %}

                  </div>

                </div>

            </div>

          </div>

          <div class="sm_device">
            <div class="row row-friends-joined">
              <div class="col-xs-5 left">
                <div class="row-main-label">{{content.friends}}</div>
              </div>
              <div class="col-xs-7 right">
                <div class="row-main-label">{{content.reward_text}}</div>
              </div>
            </div>
            <div class="row row-rewards-texts">

              <div class="{% if content.dynamic_spacing == 'false' %}col-xs-12 left{% else %}col-xs-5 left{% endif %}">
                <input type="text" id="slider-track-vertical" style="display: none;" data="value:'0'" value="0" data-slider-enabled="false" data-slider-orientation="vertical">
              </div>
              <div class="col-xs-7 right">
                <div class="row rewards-boxes">
                {% assign num_levels = content.number_of_rewards_levels %}

                {% for i in (1..num_levels) %}
                {% assign prize_text = 'prize_text_' | append: i %}
                {% assign prize_level = 'prize_level_' | append: i %}
                {% assign col_class = 'col-xs-12' %}

                <div class="{{ col_class }} reward-box reward-box-{{ i }}" data-rewardlevel="{{ content.[prize_level] }}" data-slider-tick=".slider-tick-{{ forloop.index0 }}">
                  <div class="panel panel-default">
                    <div class="panel-body">
                      <span class="reward-head-text">{{ content.[prize_level] }}</span>
                      <div class="reward-content">{{ content.[prize_text] }}</div>
                    </div>
                  </div>
                </div>

                {% assign last_prize_level = 'prize_level_' | append: i %}
                {% endfor %}

                </div>
              </div>

            </div>
          <!-- for handheld device -->
        </div>
      </div>
    </div>
  </div>
</div>
{% if content.show_bottom_text == true %}
  <div class="rewards-section gift-cards">
    <div class="container">
      <div class="col-lg-12">
        <div class="longer-rewards"  data-mercury="froala" data-content-name="longer_reward_description">
          {{content.longer_reward_description}}
        </div>
      </div>
    </div>
  </div>
{% endif %}
  <div class="footer">
    <div class="container">
      <footer>
        <div class="row">
          <div class="col-xs-12">
            <div class="social social-bottom">
              {% if content.facebook_url != '' %}
              <a class="facebook" href="{{content.facebook_url}}" target="_blank">
                <i class="fa fa-facebook"></i>
              </a>
              {% endif %}
              {% if content.twitter_url != '' %}
              <a class="twitter" href="{{content.twitter_url}}" target="_blank">
                <i class="fa fa-twitter"></i>
              </a>
              {% endif %}
              {% if content.pinterest_url != '' %}
              <a class="twitter" href="{{content.pinterest_url}}" target="_blank">
                <i class="fa fa-pinterest"></i>
              </a>
              {% endif %}
              {% if content.googleplus_url != '' %}
              <a class="googleplus" href="{{content.googleplus_url}}" target="_blank">
                <i class="fa fa-google-plus"></i>
              </a>
              {% endif %}
              {% if content.instagram_url != '' %}
              <a class="twitter" href="{{content.instagram_url}}" target="_blank">
                <i class="fa fa-instagram"></i>
              </a>
              {% endif %}
              {% if content.linkedin_url != '' %}
              <a class="linkedin" href="{{content.linkedin_url}}" target="_blank">
                <i class="fa fa-linkedin"></i>
              </a>
              {% endif %}
              {% if content.youtube_url != '' %}
              <a class="youtube" href="{{content.youtube_url}}" target="_blank">
                <i class="fa fa-youtube"></i>
              </a>
              {% endif %}
              {% if content.blog_url != '' %}
              <a class="rss" href="{{content.blog_url}}" target="_blank">
                <i class="fa fa-rss"></i>
              </a>
              {% endif %}
              {% if content.email_address != '' %}
              <a class="email" href="mailto:{{content.email_address}}">
                <i class="fa fa-envelope"></i>
              </a>
              {% endif %}
            </div> <!--// .social -->
          </div>
        </row>
        <div class="row">
          <div class="col-xs-12 col-sm-6">
            <div class="footer-text pull-left"  data-mercury="froala" data-content-name="the_footer_text">
              {{content.the_footer_text}}
            </div>
          </div>

          <div class="col-xs-12 col-sm-6">
            <p><a class="pull-right" id="privacy_link" href="{{page_url}}/privacy" >{{content.privacy_link_text}}</a>
            </p>
          </div>
        </div>
      </footer>
    </div>
  </div>
  <!-- footer -->
  <script src="//d1y0v6ricksqp.cloudfront.net/themes/viralrewards/2_0_scripts/boostrap.cls.js"></script>
  <script src="{% asset_path js/jquery-libs/fitvid/1.1/jquery.fitvids.js %}"></script>
  <script>
  if (typeof kolInsertFroalaImage === 'undefined')
      $(".container, .container-fluid").fitVids();
  </script>

  {% if content.header_background_image != '' or content.header_image_on_mobile != '' %}
    <script src="{% asset_path js/jquery-libs/backstretch/2.0.4/jquery.backstretch.min.js %}"></script>
    <!-- <script>
      /* Header background slideshow */
      $(function($){
        // If mobile image exists show it on small screens
        if (window.innerWidth >= 600) {
          {% if content.header_image_on_mobile != "" %}
            $('.header-banner').backstretch(['{{content.header_background_image}}']);
          } else if (window.innerWidth < 600) {
            $('.header-banner').backstretch(['{{content.header_image_on_mobile}}'], {duration:4000, fade: 'normal'});
          {% endif %}
        };

        // If mobile image doesn't exist show it normal
        {% if content.header_image_on_mobile == "" %}
          $('.header-banner').backstretch(['{{content.header_background_image}}']);
        {% endif %}
      });
    </script> -->
  {% endif %}
  <script>

    var total_ref = 0, rewardBoxHeight = 0;

    function kol_got_data(data) {

      setInterval(function() {
        $(".header-banner").data("backstretch") && $(".header-banner").data("backstretch").resize();
      }, 100);

      {% assign num_levels = content.number_of_rewards_levels %}

      total_ref = data.influence.direct;

      $('.reward-box').each( function(i, obj) {

        rewardlevel = $( this ).data('rewardlevel');

        if ( total_ref >= rewardlevel )
          $( this ).addClass('reward-earned');

      });

      showSlider( total_ref );
    }


    function showSlider( totalReferences ) {

      var slider_data = {
        ticks: [
          {% for i in (1..num_levels) %}
          {% assign prize_level = 'prize_level_' | append: i %}
          {{ content.[prize_level] }},
          {% endfor %}
        ],
        {% if content.dynamic_spacing == 'false' %}
        ticks_positions: [1, 20, 40, 60, 80, 100],
        {% endif %}
        ticks_values: [
          {% for i in (1..num_levels) %}
          {% assign prize_level = 'prize_level_' | append: i %}
          '{{ content.[prize_level] }}',
          {% endfor %}
        ],
        ticks_innerLabels: [
          {% for i in (1..num_levels) %}
          {% assign prize_text = 'prize_text_' | append: i %}
          '',
          {% endfor %}
        ],
        ticks_snap_bounds: 0,
        tooltip: 'hide',
        value: totalReferences
      };

      $('#referred').html(' ' + totalReferences);

      $("#slider-track").slider(slider_data);


      slider_data['orientation'] = 'vertical';
      slider_data['ticks_positions'] = null;

      $("#slider-track-vertical").slider( slider_data );

      {% if content.dynamic_spacing == 'false' %}

        adjustSliderOnMobile();

      {% endif %}
    }


    $(document).on('kol:knownlead', function(e, lead){
      kol_got_data(lead);
    });

    $(document).on('kol:unknownlead', function(url){
      showSlider(0);
    });


    {% if content.dynamic_spacing == 'false' %}

    $(window).resize( adjustSliderOnMobile );

    function adjustSliderOnMobile() {

        var totalReferences = total_ref,
        sliderVerticalTrack = $( '.slider.slider-vertical .slider-track' ),
        sliderVerticalHeight = 0,
        sliderTickFirstHeight = $( '.slider.slider-vertical .slider-tick.slider-tick-0' ).height();

        if ( rewardBoxHeight == 0 ) {

          if ( $(".sm_device .rewards-boxes .reward-box").length ) {

            rewardsBoxes = ".sm_device .rewards-boxes .reward-box";

          } else {

            rewardsBoxes = ".sm_device .slider-track .reward-box";
          }
        }

        totalRewardsBoxes = ( rewardsBoxes.length ) - 1;

        $( rewardsBoxes ).each(function( index ) {

            rewardBoxHeight = $( this ).height();

            var sliderTick = $( this ).data('slider-tick'),
            sliderTickEl = $( '.sm_device ' + sliderTick ),
            sliderTickSpan = $( '.sm_device ' + sliderTick + ' .slider-top-label' );


            if ( ! $( '.sm_device ' + sliderTick + ' .slider-tick-value' ).length ) {

              sliderTickSpan.remove();

              var sliderTickInnerHTML = sliderTickEl.html();

              sliderTickEl.empty();

              sliderTickEl.append( '<div class="slider-top-label"></div><div class="slider-tick-value">' + sliderTickInnerHTML + '</div>' );

              sliderTickSpan = $( '.sm_device ' + sliderTick + ' .slider-top-label' );

              $( this ).appendTo( sliderTickSpan );
            }


            if ( index < totalRewardsBoxes ) {

              rewardBoxHeight = $( this ).height();
              sliderVerticalHeight = sliderVerticalHeight + rewardBoxHeight;
            }
        });


        // Refresh distance between slider ticks
        var sliderSelection = $( '.sm_device .slider-selection.tick-slider-selection'),
        distanceBetweenRewards,
        rewardLevelBox2,
        rewardLevelBox3,
        sliderSelectionHeight = 0,
        sliderTickHeight = 40,
        rewardLevelBox1 = $( '.sm_device .reward-box-1' ).data('rewardlevel'),
        rewardLevelBox2 = $( '.sm_device .reward-box-2' ).data('rewardlevel'),
        rewardLevelBox3 = $( '.sm_device .reward-box-3' ).data('rewardlevel'),
        rewardLevelBox4 = $( '.sm_device .reward-box-4' ).data('rewardlevel'),
        rewardLevelBox5 = $( '.sm_device .reward-box-5' ).data('rewardlevel');
        $( ".sm_device .slider-track .slider-tick" ).each(function( index ) {

            if ( $( this ).hasClass( 'in-selection' ) ) {

              if ( index === 1 ) {

                sliderTickDistances = $('.sm_device .slider-tick-1').offset().top - $('.sm_device .slider-tick-0').offset().top;

                if (
                  totalReferences > rewardLevelBox2
                  && totalReferences < rewardLevelBox3 ) {

                  distanceInPercentage = ( totalReferences * 100 ) / rewardLevelBox3;

                  distanceBetweenRewardNonEarned = $('.sm_device .slider-tick-2').offset().top - $('.sm_device .slider-tick-1').offset().top;

                  distanceBetweenRewards = ( distanceInPercentage * distanceBetweenRewardNonEarned ) / 100 - sliderTickHeight;

                  sliderSelectionHeight = sliderSelectionHeight + distanceBetweenRewards;
                }

                sliderSelectionHeight = sliderSelectionHeight + sliderTickDistances;
              }


              if ( index === 2 ) {

                sliderTickDistances = $('.sm_device .slider-tick-2').offset().top - $('.sm_device .slider-tick-1').offset().top;

                if (
                  totalReferences > rewardLevelBox3
                  && totalReferences < rewardLevelBox4 ) {

                  distanceInPercentage = ( totalReferences * 100 ) / rewardLevelBox4;

                  distanceBetweenRewardNonEarned = $('.sm_device .slider-tick-3').offset().top - $('.sm_device .slider-tick-2').offset().top;

                  distanceBetweenRewards = ( distanceInPercentage * distanceBetweenRewardNonEarned ) / 100 - sliderTickHeight;

                  sliderSelectionHeight = sliderSelectionHeight + distanceBetweenRewards;
                }

                sliderSelectionHeight = sliderSelectionHeight + sliderTickDistances;
              }


              if ( index === 3 ) {

                sliderTickDistances = $('.sm_device .slider-tick-3').offset().top - $('.sm_device .slider-tick-2').offset().top;

                if (
                  totalReferences > rewardLevelBox4
                  && totalReferences < rewardLevelBox5 ) {

                  distanceInPercentage = ( totalReferences * 100 ) / rewardLevelBox5;

                  distanceBetweenRewardNonEarned = $('.sm_device .slider-tick-4').offset().top - $('.sm_device .slider-tick-3').offset().top;

                  distanceBetweenRewards = ( distanceInPercentage * distanceBetweenRewardNonEarned ) / 100 - sliderTickHeight;

                  sliderSelectionHeight = sliderSelectionHeight + distanceBetweenRewards;
                }

                sliderSelectionHeight = sliderSelectionHeight + sliderTickDistances;
              }


              sliderSelection.height( sliderSelectionHeight );
            }
        });

        if ( !$(".slider-track-overlay")[0] ) {

          sliderVerticalTrack.append( '<div class="slider-track-overlay"></div>' );
        }

        var sliderTrackOverlay = $( '.sm_device .slider-track-overlay' ),
        sliderTickHeightWithPad = 46,
        sliderTickRoundTopPad = 7,
        sliderPanelMarginBottom = 20;

        sliderTrackOverlay.height( rewardBoxHeight - sliderTickHeightWithPad - sliderTickRoundTopPad + sliderPanelMarginBottom);

      }

      {% endif %}

  </script>
  <!-- Placed at the end of the document so the pages load faster -->
  {% integrations footer %}
  {% kol_thankyou_script %}
</body>
</html>

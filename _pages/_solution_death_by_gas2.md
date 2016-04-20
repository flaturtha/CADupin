---
permalink:  /solution_death_by_gas2/
---

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

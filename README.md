# vigaash23.github.io
<html>
    <head>
        <style>
            body{
                background-image: url("mod.png");
		background-repeat: no-repeat;
  background-size: 1800px 800px;
  
  
                height:100%;
                width:95%;
                overflow:hidden;
            }
            
            .mole{
                background-color:rgb(40,40,40);
                border-radius:100px 100px 0px 0px;
                height:100%;
                width:10%;
                position:absolute;
                top:100%;
                background-image: url('mole.png');
                background-size: 100%;
                background-repeat: no-repeat;
		background-image: url("facee.jpg");
            }
		.left_ear{
		background-color:rgb(40,40,40);
		border-radius:100px;
		position;absolute;
		left:0px;
		float:left;
		min-width: 30%;
		padding-top:30%;
		z-index:-1;
		}
		.right_ear{
		background-color:rgb(40,40,40);
		border-radius:100px;
		position;absolute;
		left:0px;
		float:right;
		min-width: 30%;
		padding-top:30%;
		left:70%;
		z-index:-1;
		}
            
            #mole1 {left:5%;}
            #mole2 {left:45%;}
            #mole3 {left:85%;}
            
            .score{font-family:Courier; font-size:25px; position:absolute;right:320px; }
            
        </style>
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
        </script>
        
        <script>
            jQuery(document).ready(function(){
                var score=0;
                
                function game_over(){
                    jQuery('.mole').animate({'top':'100%'},300);
                    jQuery('.score').html('GAME OVER');
                    jQuery('.score').append('<div class="try_again">TRY AGAIN</div>');
                }
                
                function start(){
                    score=0;
                    jQuery('.score').html('Score: ' + score);
                    jQuery('.mole').animate({'top':'0%'},5000,function(){
                        game_over();
                        jQuery('.try_again').click(function(){start();});
                });
                }
                
                jQuery('.mole').hover(function(){
                    
                    jQuery(this).css('background-image','background-image');
                    jQuery(this).stop().animate({'top':'100%'},300,function(){
                        
                        score++;
                        jQuery('.score').html('Score: ' + score);
                        jQuery(this).css('background-image','background-image');
                        jQuery(this).animate({'top':'0%'},5000);
                    }); 
                    
                });
            start();                    
       });
        </script>
    </head>
    <body>
        <div class="score">Score: 0</div>
        <div class="mole" id="mole1">
	<div class="left_ear"></div>
	<div class="right_ear"></div>
	</div>
        <div class="mole" id="mole2">
	<div class="left_ear"></div>
	<div class="right_ear"></div>
	</div>  
        <div class="mole" id="mole3">
	<div class="left_ear"></div>
	<div class="right_ear"></div>
	</div>
    </body>
</html>

# Project-9 Tropical Paradise
SASS / HTML / CSS / JS
Font Awesome 

Google Fonts
+     Dancing Script
      https://fonts.google.com/specimen/Dancing+Script?query=dancing+script
+      Open Sans
       https://fonts.google.com/specimen/Open+Sans
CSS = NAV = burger
+      .burger-btn {
	      position: fixed;
	      top: 20px;
	      right: 20px;
	      padding: 1em;
	      background: none;
	      border: 1px solid transparent;
	      cursor: pointer;
	      z-index: 1000;

+      	&:focus {
	      	outline: none;
		      border: 1px solid rgba(255, 255, 255, 0.5);
      		border-radius: 8px;
	      }

+          &:hover {
              .burger-btn__bars::after, .burger-btn__bars::before {
                  width: 100%;
              }
          }

+      	&__box {
	      	position: relative;
		      width: 40px;
		      height: 30px;
	      }
+      	&__bars,
	      &__bars::after,
	      &__bars::before {
		      @include burgerBtn;
	      }
+          &__bars {
              width: 100%;
        
+              &::after {
                  top: 13px;
                  width: 60%;
              }
+              &::before {
                  top: 27px;
                  width: 30%;
                  transition-delay: .1s;
              }
          }

      }
CSS = Header = _components.scss
+		.wrapper {
			margin: 0 auto;
			width: 100%;
			max-width: 1200px;
		}
+		.white-block {
			position: absolute;
			height: 40px;
			width: 60%;
			background-color: $pure-white;

+			&-left {
				bottom: 0;
				left: -50px;
				transform: skew(45deg);
			}
+			&-right {
				top: 0;
				right: -50px;
				transform: skew(45deg);
			}
		}
+		.btn-special-animation {
			position: relative;
			transition: background-color 0.3s;
			overflow: hidden;
			z-index: 0;

+			&::before {
				display: block;
				content: '';
				position: absolute;
				top: 0;
				left: 0;
				width: 100%;
				height: 100%;
				transform: scaleX(0);
				transform-origin: right;
				transition: transform 0.3s;
				z-index: -1;
			}
+		    &:hover::before {
        		transform: scaleX(1);
        		transform-origin: left;
    		}
             } 

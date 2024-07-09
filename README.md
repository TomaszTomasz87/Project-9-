# Project-9 Tropical Paradise
SASS / HTML / CSS / JS
Font Awesome 

Google Fonts
+     Dancing Script
      https://fonts.google.com/specimen/Dancing+Script?query=dancing+script
+      Open Sans
       https://fonts.google.com/specimen/Open+Sans
CSS = NAV
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

# Shiny Server code for data collection and Feedback Site

The shiny source code for open-source survey adminstration and data collection site the comprises two files, the server and the UI which was used within the publication of the paper and Conal Monaghan's PhD thesis. You will need a shiny.io account (only get the free version -> you do not need server level access), R and Rstudio. To find out more information about the Machiavellianism site, scale, or research feel free to visit the website (https://conalmonaghan.shinyapps.io/two-dimensional_machiavellianism/), and or contact me at:
       Conal.Monaghan@anu.edu.au

## Website Code

The code is well annotated and should take minimal Shiny Server skills to impliment. You will require a Google account with Googlesheets. The code will make a new file in there which will be amended whenever a user completes the survey. The code links using the Key (this is better than filename which you shouldn't use, trust me) which you can find in googlesheets or the googlesheets package can get it for you. Below is how to set up the file through R. 


 First, one needs to setup the authorisation token and a worksheet in googlesheets to use. See below for the setup that works with the app below. 

Note that before this will work you will need to run the following in your console (once installed googlesheets() ) 
                 1)   ttt <- gs_auth()                               # now follow the html. prompts to login
                 2)   saveRDS(ttt, "ttt.rds")                        # then copy ttt.rds file to the app's Dir() 
                 3) Now one needs to create a worksheet to use using the following code:

         Data <- gs_new("Data") %>% 
                    gs_ws_rename(from = "Sheet1", to = "Data")      
 
                 4) Insert the titles that we want
           Data <- Data %>% 
                       gs_edit_cells(ws = "Data", input = cbind("Score1", "Score2", "Time", "Mean"), trim = TRUE)                # Note! you will need to have manually add one row of data to your google sheet otherwise it will error


## Machiavellianism Website

The Machiavellianism website contains many more functions, including downloadable .pdf of participant info sheets, IRT estimations, admin section with data stats and download options etc. If you are interested in these options, please first search the helpful repos at googlegroups (https://groups.google.com/forum/#!forum/shiny-discuss) and stackexchange (https://stackexchange.com). If all else fails, contact me at:
       Conal.Monaghan@anu.edu.au



# STA-303-Mixed-Assignment-1
# RUN THIS CHUNK FIRST! You should only need to run it once on your local machine.
# On the JupyterHub, you may need to run it at the beginning of each new session.

# These are the packages you will need for this activity.
packages_needed <- c("tidyverse", "devtools", "lme4", 
                     "lattice", "lmtest", "randomNames")

package.check <- lapply(
  packages_needed,
  FUN = function(x) {
    if (!require(x, character.only = TRUE)) {
      install.packages(x, dependencies = TRUE, 
      repos = "https://cloud.r-project.org/") # you may need to change the mirror if 
      # you're in China (and potentially other countries.)
      # Students in China have reported that 
      # "https://mirrors.tuna.tsinghua.edu.cn/CRAN/" worked for them.
    }
  }
)

# Remove objects no longer needed
rm(packages_needed, package.check)

# You may be prompted to install or update additional packages
# If so, you'll see a message in the console 
# Type a enter/return in the console to skip updating
devtools::install_github("elb0/myStarship", force = TRUE)
# Run libraries for easy access to the functions we'll be using
library(tidyverse)
library(lme4)
library(myStarship)

# Once you've updated the code and are ready to knit
# change this to eval = TRUE
knitr::opts_chunk$set(eval = FALSE)
# put your student ID in here
get_my_starship(1005120691)

# after you run this function, your unique dataset will appear in the environment
# it will be called crew_data
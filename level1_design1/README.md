#Buggy Adder
###For the buggy mux.First I added some manual values to inputs and checked the outputs for error. Then I did random test where select line and all 31 inputs were varied randomly and we repeated it for 30 iterations at first just to observe any bugs initially. Post that if all iterations are coming error free then we will increase iterations.
###The aim of verification is to see if the select lines are changing input as per the model or not by changing select line randomly and also to verify if the desired inputs are selected w.r.t select line. 
![](https://github.com/vyomasystems-lab/challenges-Santosh3672/blob/master/level1_design1/Pic1.JPG)
###From above we can see that when sel = 30, model output is 3 but DUT output is 0. On checking the design we see that in case statement(line 57) no value has been assigned when select line is 30 hence it assumes the default value 0.
###After fixing the this bug let's verify again.
![](https://github.com/vyomasystems-lab/challenges-Santosh3672/blob/master/level1_design1/Pic2.JPG)
###Now we are seeing issue with sel =  12. Here, model output is 2 abd DUT output is 0, lets check whether it is due to the default output or not. On checking RTL we see that on line 40 whre case statement for inp12 is written there the value of select line is 13 on line 41 also for inp 13 the value of select line is 13. As there are no scenarios for sel value of 12 it is getting default value of 0. 
###Lets verify after fixing the bug.
![](https://github.com/vyomasystems-lab/challenges-Santosh3672/blob/master/level1_design1/Pic3.JPG)
###Now all the test cases have passed, to improve our confidence in it we have run it for 1000 iterations. We can say that all bugs have been fixed.

# Support-Genie-Python-Developer-Intern

**Problem Statement :**

                      Predict agent availability
                      You have the following data for issues.
                      
                      *Issue
                      *start_time
                      *abandoned/resolved
                      *answer_time	(time an agent started working on the issue)
                      *resolved_time (the time an issue was resolved)
                      *abandoned_time (if a customer left before the issue was assigned to an agent)
    Now when a  new issue comes in we need to predict the time the issue will be assigned to an agent. 
    Use your best judgement to solve the above problem. You may/may not want to use all fields. 


**Suggested Solution :**
              
                      Suppose the problem statement belongs to a company that provides broadband connections
                      in different cities of the country. It has an online portal where users can register a 
                      complaint if any. They get back with there support team, sends an engineer to site if 
                      required to resolve the issue. If the issue is resolved by user itself, the issue is 
                      abandoned, either by user or by the support team.
                      
                      Delay can be dependent on many factors like weekday on which issue was raised ( if raised
                      on sunday may take longer to assign ), financial quater in which issue was raised , month 
                      ( number of issues raised may be lower or agents available may be lower in holidays ) , 
                      location where issue was raised, type of issue ( if need some specialized agent to look over ).
                      
                      Data Dictionary :
                           start_time     : Time at which user reports the issue
                           answer_time    : Time at which agent is assigned for the issue ( starts working )
                           resolved_time  : Time at which issue is resolved
                           abandoned_time : Time at whih issue is abandoned before it was assigned to an agent
                           status         : 1 if resolved otherwise 0
                           delay          : delay in assignment of task to agent . Calculated as 
                                            answer_time - start_time ( if issue is resolved )
                                            abandoned_time - start_time ( otherwise )
                       
                      Using Random Forest Classification : 
                          
                            Random forests is a supervised learning algorithm. It is also the most flexible and easy 
                            to use algorithm.Random forests creates decision trees on randomly selected data samples, 
                            gets prediction from each tree and selects the best solution by means of voting.
                            The accuracy we got was 20.5% ONLY !
                            
                      Why such low accuracy ?
                            
                            We have seen, the delay caused in real scenarios is depends on many factor, hence shows a trend 
                            with respect to time ( like hike in delay if there are holidays inbetween, location of issue ). 
                            If we plot trends in data we generated it looks like this :
                            
                            This shows that there is no real trend in the data we are using , because we have generated this
                            data randomly. 
                            The model suggested here is expected to give better result with real scenario data.


                            

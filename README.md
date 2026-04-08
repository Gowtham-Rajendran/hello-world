# 
I would like to highlight some challenges we are currently facing during the C&R feature testing in PSI 51.

One of the main concerns is the number of demos conducted so far. For each demo, additional scenarios were requested, which significantly increased the testing effort compared to the initial estimate. We have already provided multiple demos, and each demo session has taken more than one hour to complete. Due to this, a considerable amount of time has been spent preparing and executing these scenarios.

Because of the increased focus on C&R feature testing and demos, I have been largely occupied with these activities and have not been able to work fully on other features such as Transaction Processing.

As per the comments from yesterday’s demo, there are still two scenarios pending for the Reversal UI:

Exception Scenario – Some SSA Failure
We need to validate the scenario where some SSA processes fail while others succeed.
Currently, we are not able to achieve this SSA failure condition in the environment.
We have already highlighted this limitation to TZ multiple times. However, they requested us to further check if there is any alternative approach to validate this scenario.
Business Validation Scenario – Loader Activity with Mixed Status
We need to validate a scenario where the loader activity contains a mix of positive transactions and SSA not completed cases.
This scenario requires DB developer support to configure or simulate the required data/state in the database before testing can be performed.

Additionally, some scenarios are dependent on validations and execution of other business processes (e.g., FR). For example, during yesterday’s demo, there was a scenario where the Reversal Activity ID was populated as the Activity ID in the Exception dropdown for the SSA failed scenario. To understand how the functionality currently behaves in other business processes, TZ requested us to recreate the same scenario in FR.

Similar validations were performed multiple times. Whenever we were not sure about a behavior, we recreated the same scenario in other business processes like FR to confirm the behavior. This additional cross-process validation effort was not included in our original estimation.

In addition to the above, TZ has requested one more demo to cover business validations and exception scenarios for Loader. The following scenarios need to be demonstrated:

Some SSA failed (currently not achievable).
Some Portfolio Accounting failed (TZ suggested using commit to simulate this scenario – yet to be tested).
Both SSA and Portfolio Accounting failed (TZ suggested using commit – yet to be tested).

Considering the above points, the testing effort for the C&R feature has increased significantly compared to the initial estimate, and several scenarios are dependent on validations. I wanted to highlight these challenges and intimate that the testing of Quantity Adjustment UI and Loader has not yet been fully completed due to these dependencies.

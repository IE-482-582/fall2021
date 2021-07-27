# IE 482/582 -- Robotics

## Quiz 1 (Chapters 1 -- 5)
#### 9/28/2020

--- 

### Name: *ENTER YOUR NAME HERE IF YOU WISH TO RECEIVE CREDIT*

---

1. [*3 points*] Which version of Ubuntu are we running?
    - *your answer goes here*
    
    
2. [*3 points*] Which version of ROS are we running?
    - *your answer goes here*


3. [*3 points*] Which version of Python are we running?
    - *your answer goes here*


4. [*5 points*]  Consider the following Linux terminal command, followed by its output:
    ```
    student@vm:~/catkin_ws/src/custom_message/scripts$ ls
        listener2.py  talker2.py
    ```
    - What is the Linux terminal command that will make `talker2.py` executable?
        - `your answer goes here`


5. [*5 points*] What is the Linux terminal command that will change directories to your home directory?
    - `your answer goes here`


6. [*5 points*] Consider the following sequence of terminal commands (and their outputs):
    ```
    student@vm:~/catkin_ws/src/custom_message$ pwd
        /home/student/catkin_ws/src/custom_message
    student@vm:~/catkin_ws/src/custom_message$ ls
        CMakeLists.txt  msg  package.xml  scripts
    student@vm:~/catkin_ws/src/custom_message$ cd msg
    student@vm:~/catkin_ws/src/custom_message/msg$ ls
        grade_msg.msg
    student@vm:~/catkin_ws/src/custom_message/msg$ cd ..
    student@vm:~/catkin_ws/src/custom_message$ ls
    ```
    
    - What is the output from the last command (`ls`)?
        - `your answer goes here`

    
7. Suppose we have a package named `some_package`, and that we want to run a ROS node defined by a Python script called `do_great_stuff.py`.  We'll use two (2) terminals to run our node.
    1. [*5 points*] In **Terminal 1**, we need to start ROS.
        ```
        student@vm:~$ cd ~
        ```
        - Now, what command do we use to start ROS?
            - `your answer goes here`
        
    
    2. [*5 points*] In **Terminal 2**, we want to run our node.
        ```
        student@vm:~$ cd ~/catkin_ws/src/some_package/scripts
        student@vm:~/catkin_ws/src/some_package/scripts$ ls
            do_great_stuff.py
        ```
     
        - Now, what command do we use to run this node?
            - `your answer goes here`
    

8. [*5 points*] Suppose you want to create a ROS package named `robot_controller`.  Write the Linux terminal commands to create this package.  (Don't forget to navigate to the appropriate directory.)
    ```
    your answer 
    goes here
    ```

9. [*5 points*] Suppose you want to compile (also known as "make" or "build") all of the ROS packages in your catkin workspace.
Write the Linux terminal commands to "make" the ROS packages.  (Don't forget to navigate to the appropriate directory.)
    ```
    your answer 
    goes here
    ```
    

10. [*5 points*] Consider a text file that contains only the following 5 lines: 
    ```
    string robot_name
    float32 weight
    ---
    int32 robot_id
    bool too_heavy
    ```
    
    - Does this file define a **message**, a **service**, or an **action**? Explain how you know your answer is correct.
        - *your answer goes here*


11. Consider the ROS Python node described below:
    ```
    #!/usr/bin/env python
    
    # File: topic_publisher.py
    
    import rospy
    from std_msgs.msg import Int32
    
    rospy.init_node('topic_publisher')
    pub = rospy.Publisher('counter', Int32)
    rate = rospy.Rate(2)
    
    count = 0
    while not rospy.is_shutdown():
        pub.publish(count)
        count += 1
        rate.sleep()
    ```
    
    1. [*3 points*] How long does the code pause in the last line (`rate.sleep()`)?
        - *your answer goes here*

    2. [*3 points*] What is the name of the topic?
        - `your answer goes here`

    3. [*3 points*] What is the message type?
        - `your answer goes here`

    4. [*3 points*] What is the line of code in which the topic is actually published?
        - `your answer goes here`
    

12. [*6 points*] Consider the ROS Python node below: 
    ```
    #!/usr/bin/env python
    
    # File: topic_subscriber.py
    import rospy
    from std_msgs.msg import Int32
    
    def callbk_reg(msg):
        print "Apple"
        # print msg.data
    
    def callbk_count(msg):
        print "Orange"
        # print msg.data
    
    rospy.init_node('topic_subscriber')
    
    print "Hey"
    sub1 = rospy.Subscriber('counter', Int32, callbk_count)
    
    print "Whoa"
    sub2 = rospy.Subscriber('register', Int32, callbk_reg)
    
    rospy.spin()
    ```
    Suppose that the following events occur:
    1. You start `roscore` in a terminal window.
    2.  You start the `topic_subscriber` node in a second (different) terminal window.
    3. You wait several seconds before starting a ROS node that publishes to the `counter` topic (in a third terminal window).
    4. Two (2) messages from the `counter` topic are received by the `topic_subscriber` node.   Assume that there are no messages broadcast on the `register` topic.
    5. You hit `Ctrl`-`C` in the second terminal window.

    What, exactly, is printed to the screen by the `topic_subscriber` node?

    ```
    your answer 
    goes here
    ```

    
13. Briefly explain the following ROS concepts:
    1. [*4 points*] "Node":
        - *your answer goes here*
                    
    2. [*4 points*] "Topic": 
        - *your answer goes here*

    3. [*4 points*] "Service":
        - *your answer goes here*


14. [*6 points*] For each item below, specify whether a **Topic**, **Service**, or **Action** is most appropriate: 
    1. Simple request/response interactions, such as asking a question about a node's current state.
        - *your answer goes here*

    2. Most request/response interactions, especially when servicing the request is not instantaneous (e.g., navigating to a goal location).
        - *your answer goes here*

    3. One-way communication, especially if there might be multiple nodes listening (e.g., streams of sensor data).
        - *your answer goes here*


15. [*5 points*] **True** or **False**:  A node can either be a publisher or a subscriber, but not both.
    - *your answer goes here*


16. [*5 points*] **True** or **False**:  A single node can publish to multiple topics.
    - *your answer goes here*


17. [*5 points*] **True** or **False**:  A single node can subscribe to multiple topics.
    - *your answer goes here*



18. [*5 points*] Consider the following information copied from the terminal:
    ```
    student@vm:~/catkin_ws$ catkin_make
        Base path: /home/student/catkin_ws
        Source space: /home/student/catkin_ws/src
        Build space: /home/student/catkin_ws/build
        Devel space: /home/student/catkin_ws/devel
        Install space: /home/student/catkin_ws/install
        Error(s) in package '/home/student/catkin_ws/src/custom_message/package.xml':
        Error(s):
        - The manifest (with format version 2) must not contain the following tags: run_depend
    ```
    - What was the problem?  How do you fix the problem?    
        - *your answer goes here*

19. Suppose we have a package named `something_new`.  Furthermore, suppose we have a message-definition file, named `my_message.msg`, that contains the following:
    ```
    int32 someNumber
    float32 anotherNumber
    string someTest
    ```

    Now, imagine we are writing a ROS node (a Python script) that will **subscribe** to a topic named `noise`, such that this topic is of the `my_message` type.

    1. [*4 points*] Write the single line of Python code that will import our custom message type.
        ```
        your answer goes here
        ```

    2. [*4 points*] Write the single line of Python code that will subscribe to the `noise` topic.  A callback function named `noiseCallback` should be called whenever a message is published to the `noise` topic.
        ```
        your answer goes here
        ```

    Next, suppose we have a ROS node that **publishes** to the `noise` topic.

    1. [*4 points*] Write the single line of Python code that will define the publisher for the `noise` topic.  Use a queue size of 5.  
        ```
        your answer goes here
        ```

    2. [*4 points*] Write a single line of code that will initialize an empty message of type `my_message`.
        ```
        your answer goes here
        ```
    
    3. [*4 points*] Write a single line of code that will initialize the value of `someNumber`, associated with the message type `my_message`, such that `someNumber` equals `3.14`.
        ```
        your answer goes here
        ```
    
    4. [*4 points*] Write a single line of code that will publish to the `noise` topic.
        ```
        your answer goes here
        ```
    

20. [*5 points*] Consider the following Python code:

    ```
    #!/usr/bin/env python
    import rospy
    
    isMoving = True
    changeTime = rospy.Time.now() + rospy.Duration(5)
    rate = rospy.Rate(1)
    
    while not rospy.is_shutdown():
        print(isMoving)
        if (rospy.Time.now() >= changeTime):
            isMoving = not isMoving
            changeTime = rospy.Time(now) + rospy.Duration(5)
        rate.sleep()
    ```
    
    What is the value of `isMoving` 33 seconds after you start running this script?  
    - `your answer goes here`

    
21. [*10 points*] Suppose we have a ROS package, named `math_service` that implements a simple service.  The client will provide two numbers; the service will return the value of those two numbers multiplied by each other.

    The server node runs in a script named `server.py`.  The code for this node is shown here:

    ```
    #!/usr/bin/env python

    # File:  ~/catkin_ws/src/math_service/scripts/server.py

    import rospy    
    from math_service.srv import simple_math
    
    def handle_multiply(request):
        return {'c': request.a * request.b}
        
    rospy.init_node('server')
    
    s = rospy.Service('multiply', simple_math, handle_multiply)
    
    rospy.spin()
    ```    

    The package uses a custom service type named `simple_math.srv`.  The code specifying the structure of this service is shown here:    
    ```    
    # File: ~/catkin_ws/src/math_service/srv/simple_math.srv
    float32 a
    float32 b
    ---
    float32 c
    ```

    Your task is to edit the client node code below, such that it will call the service and print out the response.  You will need to write two lines of code to make the client node function properly.  Simply edit the code below, as per the instructions in the UPPER CASE comments:
    ```
    #!/usr/bin/env python

    # File:  ~/catkin_ws/src/math_service/scripts/client.py

    import rospy
    from math_service.srv import simple_math
    
    # Define two numbers that we want to multiply:
    number1 = 32.3
    number2 = 49.1
    
    rospy.init_node('client')
    
    rospy.wait_for_service('multiply')
    
    call_multiply = rospy.ServiceProxy('multiply', simple_math)
    
    
    # 1) WRITE ONE LINE OF CODE HERE THAT PROVIDES THE SERVICE WITH THE
    #    TWO NUMBERS WE WANT TO MULTIPLY (number1 and number2), 
    #    AND CAPTURES A RESPONSE.
    
    
    # 2) WRITE ONE LINE OF CODE HERE THAT PRINTS THE SERVICE RESPONSE
    #    (WHICH IS THE RESULT OF MULTIPLYING OUR TWO NUMBERS).
    ```

---

- Your quiz is due by 10:00pm on Monday, September 28.  **Late submissions will not be accepted.**
- To submit your quiz, email the instructor (cmurray3@buffalo.edu) with the following attachments:
    1. The edited markdown file of the quiz, containing your responses, and
    2. A PDF export of your markdown.
- You are welcome to use your class notes, to test code on your computer, or to review lecture videos.
- You are **not** allowed to discuss the quiz with anyone else (including your classmates).
- Neatness counts.  Before submitting, make sure that your responses are properly formatted.  Also make sure that you have addressed typographical and grammatical errors.
- If there is a question that is unclear, please include in your response an explanation of how you are interpreting the question.  The instructor will not be answering questions about the quiz on Monday.

---




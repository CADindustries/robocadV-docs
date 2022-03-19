Camera
================================

Here is examples how to get camera image.

.. tabs::

    .. tab:: Python

        **Location and name:** RT2.bytes_from_camera

        **Inputs:**  

        \-\-\-

        **Output:**

        *bytes* of image from robot

        **OpenCV example:**

        .. code-block:: python
            :linenos:

	    # this code will show you real time image from robot camera for 10 seconds
            from robocadSimPy.robots import RT2
	    import numpy as np
	    import cv2


            robot = RT2.RT2()
	    robot.connect()
            st_time = time.time()

	    while time.time() - st_time < 10:
    		nparr = np.frombuffer(robot.bytes_from_camera, np.uint8)
    		if nparr.size > 0:
        	    img_rgb = nparr.reshape(480, 640, 3)
        	    img_bgr = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2BGR)

        	    cv2.imshow("robot image", img_bgr)
        	    cv2.waitKey(1)
	    robot.disconnect()

        **PIL example:**

        .. code-block:: python
            :linenos:

	    # this code will save image from robot camera
            from robocadSimPy.robots import RT2
	    import numpy as np
	    from PIL import Image


            robot = RT2.RT2()
	    robot.connect()

	    while len(robot.bytes_from_camera) == 0:
		pass

    	    img = Image.frombytes("RGB", (640, 480), robot.bytes_from_camera)
	    img.save(r"image_from_robot.png", "PNG")
	    robot.disconnect()
        
        **Additional info:**
        
        \-\-\-

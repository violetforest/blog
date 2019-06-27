---
layout: post
title:  "OpenCVforUnity Handpose Estimation AR"
date:   2019-06-24 21:01:24 +0200
categories: openCVforUnity
---
OpenCVForUnity Contour Tracking AR using the Handpose Estimation example

<iframe width="560" height="315" src="https://www.youtube.com/embed/MmQNmrI9EPY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
</iframe>  

This demo is a combination of the Handpose Estimation example that comes with OpenCVforUnity & the MarkerBasedAR example found in Unity's Asset Store.

The handpose estimation example prompts you to click on the screen to take a color blob sample of what you clicked on. It then uses this color to detect contours of things with that color. So basically, whatever you click on, it will find the contour of it. There is a bounding box that is also being calculated, to get the four corner points of the contour. I took the four corners of the boundRect that was already being calculated in the Handpose example, and used them as my 2D or image points and fed them into my solvePNP function. For the 3d objects points I used the same points provided in the MarkerBasedAR example.  

{% highlight c# %}
//find the bounding box
OpenCVForUnity.CoreModule.Rect boundRect = Imgproc.boundingRect(new MatOfPoint(contour.toArray()));

//draw a rectangle
Imgproc.rectangle(rgbaMat, boundRect.tl(), boundRect.br(), CONTOUR_COLOR_WHITE, 2, 8, 0);

//store the points of the bounding rect
Point bottomLeft = new Point(boundRect.x, boundRect.y + boundRect.height);
Point topLeft = new Point(boundRect.x, boundRect.y);
Point bottomRight = new Point(boundRect.x + boundRect.width, boundRect.y + boundRect.height);
Point topRight = new Point(boundRect.x + boundRect.width, boundRect.y);

//store the points as MatOfPoint2f so I can use them in the solvePNP function
rectPoints = new MatOfPoint2f(new Point(boundRect.x, boundRect.y), //Top, Left (A)
    new Point(boundRect.x + boundRect.width, boundRect.y), //Top, Right (B)
    new Point(boundRect.x + boundRect.width, boundRect.y + boundRect.height), //Bottom, Right (C)
    new Point(boundRect.x, boundRect.y + boundRect.height) //Bottom, Left (D)
);

//3d object points that I took from MarkerBasedAR example
List<Point3> m_markerCorners3dList = new List<Point3>();

m_markerCorners3dList.Add(new Point3(-0.5f, -0.5f, 0));//Top, Left (A)
m_markerCorners3dList.Add(new Point3(+0.5f, -0.5f, 0));//Top, Right (B)
m_markerCorners3dList.Add(new Point3(+0.5f, +0.5f, 0));//Bottom, Right (C)
m_markerCorners3dList.Add(new Point3(-0.5f, +0.5f, 0));//Bottom, Left (D)
m_markerCorners3d.fromList(m_markerCorners3dList);

//estimate pose
Mat Rvec = new Mat();
Mat Tvec = new Mat();
Mat raux = new Mat();
Mat taux = new Mat();

Calib3d.solvePnP(m_markerCorners3d, rectPoints, camMatrix, distCoeff, raux, taux);
{% endhighlight %}  

You can look at the [github repository](https://github.com/violetforest/OpenCVForUnity-Handpose-AR) to see the full code.

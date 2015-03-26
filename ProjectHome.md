# DirectCV #

The main goal of this project is to provide a small lightweight layer over Intel's OpenCV library. Using this wrapper you can easily access most of the **OpenCV 2.2.0** functions in .NET environment.

## The main features ##

  * Free and open source software
  * Easy and streightforward usage
  * Almost every OpenCV function is available through this wrapper _(only the "C API" is supported)_
  * The signature of wrapper methods is almost the same as at the original functions of OpenCV. _(so that the learning curve is very short)_
  * Default function parameter support _(through overloading)_
  * Exception handling support
  * Detailed documentation and IntelliSense support _(based on the original OpenCV documentation)_
  * Enum types make harder to pass wrong values to a given function and the code will be much easier to read _(contrary to macros)_
  * Written entirely in C# using P/Invoke, interop services and mashalling


## Hello world! ##

For example the source code of a DirectCV 'hello world' program looks like this:

```
        static void Main(string[] args)
        {
            //  Create a new window with the given name.
            CV.NamedWindow("SampleWindow", CvWindowFlags.AutoSize);

            //  Load an image.
            CvImage image = CV.LoadImage("something.jpg", CvLoadImage.Color);

            //  Show the loaded image
            CV.ShowImage("SampleWindow", image);

            //  Position and resize the window.
            CV.MoveWindow("SampleWindow", 100, 200);
            CV.ResizeWindow("SampleWindow", 512, 512);

            //  Wait for keypress.
            CV.WaitKey(0);

            //  Finally we have to release the image and destroy the window.
            CV.ReleaseImage(ref image);
            CV.DestroyWindow("SampleWindow");
        }
```


## Note ##

Note that the only purpose of DirectCV is to provide access to native OpenCV functions and therefore it doesn't follow object oriented approaches in every case. The main goal is to be as similar as possible with the original C OpenCV library. The benefit of this is that if you are familiar with the OpenCV, you can learn
how to use DirectCV in no time and furthermore OpenCV documentation can be used as a reference.

Since a large part of the wrapper is automatically generated code and unfortunetaly I don't have the resources to test everything properly it can happen that some of the methods are buggy. If your find any bug please start a new issue on this site and I'll try to do my best to fix it.


---

The development started in february 2008 because I had to use OpenCV from C# for our project. I looked around on the Internet looking for OpenCV wrappers but there were a large set of functions that I coundn't find in any of these. Finally I decided to write my own simple OpenCV wrapper in which all these necessary functions are available. I hope you can use this library and it'll suit your needs. :)


Best regards,
> Attila Nagy
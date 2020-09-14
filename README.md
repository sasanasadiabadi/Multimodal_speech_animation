# Multimodal_speech_animation

an implementation of "Multimodal Speech Driven Facial Shape Models Using Deep Neural Networks" 

##### System information (version)

- OpenCV => 4.5.0-pre
- Operating System / Platform => Ubuntu 18.04.4 LTS x86_64
- Compiler => gcc-7.5.0, cmake-3.18.0

##### Detailed description

I build opencv dnn with cuda (-D WITH_CUDA=ON -D WITH_CUDNN=ON -D OPENCV_DNN_CUDA=ON) and with openvino IE (-D WITH_INF_ENGINE=ON  -D ENABLE_CXX11=ON) separately and the DNN_BACKEND_CUDA and DNN_BACKEND_INFERENCE_ENGINE options work perfectly fine, for each built.

But when I build it for the combined cuda+openvino case, only the IE backend works but for cuda backend I get the warning (setUpNet DNN module was not built with CUDA backend; switching to CPU). 

    ```
   Other third-party libraries:
     Intel IPP:                   2020.0.0 Gold [2020.0.0]
           at:                   /home/sasan/opencv4/opencv/build/3rdparty/ippicv/ippicv_lnx/icv
     Intel IPP IW:                sources (2020.0.0)
               at:                /home/sasan/opencv4/opencv/build/3rdparty/ippicv/ippicv_lnx/iw
     Lapack:                      NO
     Inference Engine:            YES (2020040000 / 2.1.0)
         * libs:                  /opt/intel/openvino_2020.4.287/deployment_tools/inference_engine/lib/intel64/libinference_engine_legacy.so
         * includes:              /opt/intel/openvino_2020.4.287/deployment_tools/inference_engine/include
     nGraph:                      YES (0.0.0+1007b05)
         * libs:                  /usr/local/lib/libngraph.so
         * includes:              /usr/local/include
     Eigen:                       YES (ver 3.3.4)
     Custom HAL:                  NO
     Protobuf:                    build (3.5.1)
 
   NVIDIA CUDA:                   YES (ver 10.0, CUFFT CUBLAS)
     NVIDIA GPU arch:             30 35 37 50 52 60 61 70 75
     NVIDIA PTX archs:
 
   cuDNN:                         YES (ver 7.6.4)
 
   OpenCL:                        YES (no extra features)
     Include path:                /home/sasan/opencv4/opencv/3rdparty/include/opencl/1.2
     Link libraries:              Dynamic load
 
   Python 3:
     Interpreter:                 /usr/bin/python3 (ver 3.6.9)
     Libraries:                   /usr/lib/x86_64-linux-gnu/libpython3.6m.so (ver 3.6.9)
     numpy:                       /home/sasan/.local/lib/python3.6/site-packages/numpy/core/include (ver 1.19.1)
     install path:                lib/python3.6/dist-packages/cv2/python-3.6
    ```

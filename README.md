# My OPENCL Notes  
***
<p style="text-align: center;">2022-12-25</p>  
<p style="text-align: center;">cgonzalezbrito</p>  

## Introduction  
  TODO
## Host Programming  
The program on the host is responsible for the initialization, coordination of kernels execution and data transfer to the kernels. The host creates the initial data buffers that are used by the kernel in charge of normalizing and writing the data into FIFO buffer channels.  
<img 
    style="display: block; 
           margin-left: auto;
           margin-right: auto;"
    src="images/host_diagram.png"
    alt="Host main diagram"
           >
<p style="text-align:center;">Fig 1:Host functions main daigram</p>
</img>

### Get OpenCL Platform
Platform is related to the vendor. OpenCL defines a mechanism to identify a specific vendor’s OpenCL implementation in code, i.e. the platform on which the program run. This is important for portability property of OpenCL.

```c++
    cl_int clGetPlatformIDs(cl_uint num_entries,
                            cl_platform_id *platforms,
                            cl_uint *num_platforms)
```
<p style="text-align: center;">Normal Use. Scarpino</p>  


```c++
  // Get the OpenCL platform.
  cl_platform_id platform = findPlatform("Altera");
  if(platform == NULL) {
    printf("ERROR:
            Unable to find Altera OpenCL platform.\n");
    return false;
    }
```
<p style="text-align: center;">VPNC use</p>  

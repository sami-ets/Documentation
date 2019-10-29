# Technological services

The lab has a machine dedicated to Visdom. Your code can log directly into this server. 

#### Table 1 : Visdom log serve IP address.

| IP            | Port      |
|---------------|-----------|
| 10.180.113.21 | 8097      |

You code must log into a specific Visdom environment (generally your name) so your experiment will be traceable.


# Department servers 

The ETS LOG/TI department has several deployment server on which you can develop, test and run your GPU-accelerated code.

#### Table 2 : Available development and deployment servers with NVIDIA GPUs.
 
| Hostname	| IP address        | Hostname                          | GPUs                                          | CUDA Version   |
|-----------|-------------------|-----------------------------------|-----------------------------------------------|----------------|
| Koios     | 10.178.8.81	    | koios.logti.etsmtl.ca 	        | 2x NVIDIA Titan XP + 1x NVIDIA Titan X	    | 8.0            |
| Phoebe	| 10.178.8.145	    | phoebe.logti.etsmtl.ca 	        | 2x NVIDIA RTX 2080 Ti	                        | 10.1           |
| Minerva	| 10.178.8.84	    | minerva.logti.etsmtl.ca 	        | 2x NVIDIA RTX 2080 Ti	                        | 10.1           |
| GPU1	    | 10.178.8.86	    | logti-srv-gpu-1.logti.etsmtl.ca   | 3x NVIDIA GTX 1080	                        | 10.1           |
| GPU2      | 10.178.8.87	    | logti-srv-gpu-2.logti.etsmtl.ca	| 1x NVIDIA GTX 1080 + 2x NVIDIA RTX 2080 Ti	| 10.1           |

When using these server for running full experiments, please keep an eye on it ! Failed experiments or processes not
successfully terminated still use RAM and VRAM on GPUs, preventing others of using the resources. Kill your process as
soon as you notice something is wrong or if your code thrown an uncaught exception which prevent the process to 
terminate cleanly.

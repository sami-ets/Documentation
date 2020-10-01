# Visdom

The lab has a machine dedicated to Visdom. Your code can log directly into this server. 

#### Visdom log server IP address.

| IP            | Port      |
|---------------|-----------|
| 10.180.113.44 | 8097      |

You code must log into a specific Visdom environment (generally your name) so your experiment will be traceable.

The `visdom` virtual environment is located under `/home/visdom/venv`. 

To start visdom:
>$ tmux  
>$ source /home/visdom/venv/bin/activate  
>$ visdom  

For login credentials, please contact [Pierre-Luc Delisle](mailto:pierre-luc.delisle.1@ens.etsmtl.ca).


# Department servers 

The ETS LOG/TI department has several deployment server on which you can develop, test and run your GPU-accelerated code.

If your algorithm doesn't take more than 8 GB of VRAM, please use the GPU in your personal development machine instead of these servers. Students who requires higher VRAM capacity for their algorithm will be prioritized.

#### Available development and deployment servers with NVIDIA GPUs.
 
| Hostname	| IP address        | Hostname                          | GPUs                                          | CUDA Version   |
|-----------|-------------------|-----------------------------------|-----------------------------------------------|----------------|
| Koios     | 10.178.8.81	    | koios.logti.etsmtl.ca 	        | 2x NVIDIA Titan XP + 1x NVIDIA 1080 TI	    | 11.0            |
| Phoebe	| 10.178.8.145	    | phoebe.logti.etsmtl.ca 	        | 2x NVIDIA RTX 2080 Ti	                        | 11.0           |
| Minerva	| 10.178.8.84	    | minerva.logti.etsmtl.ca 	        | 2x NVIDIA RTX 2080 Ti	                        | 11.0           |

When using these servers for running full experiments, please keep an eye on them ! Failed experiments or processes not
successfully terminated still use RAM and VRAM on GPUs, preventing others of using the resources. Kill your process as
soon as you notice something is wrong or if your code thrown an uncaught exception which prevent the process to 
terminate cleanly.

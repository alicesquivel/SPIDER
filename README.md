SPIDER: Sustainable Policy-based Intelligence Driven Edge Routing
for energy-aware and low-latency Visual Data Applications  
=================
In this project, we develop a 
Proposed algorithm is evaluted with event-driven (ns-3) simulations, and we establish the practicality of our approach in a real incident-supporting hierarchical cloud deployment to demonstrate ... under severe node failures and high mobility challenges of disaster response scenarios.

Authors
=================
2017 VIMAN laboratory, Computer Science Department, University of Missouri-Columbia.

```
Updated December 7, 2017 by Huy Trinh
```

All feedback appreciated to hntzq4@mail.missouri.edu 

License
=================
This project is licensed under the GNU General Public License - see the [LICENSE.md](LICENSE.md) file for details


How does SPIDER work?
==================
SPIDER first obtains a geographical knowledge of the physical obstacles (e.g., extracts this information from the satellite imagery available at the edge cloud using deep learning) and then propagates it from the gateway as shown in the figure below:

![Figure](/img/general.png)

**Figure 1**: *Incident-Supporting Hierarchical Cloud setup: SPIDER first extracts geographical knowledge of physical obstacles from the pre-uploaded at the edge cloud satellite imagery and then propagates this information from the gateway during disaster-incident response activities within a lost infrastructure region to enhance geographic routing.*

Our proposed stateless greedy forwarding algorithm viz. "Attractive/Repulsive Greedy Forwarding" that emulates electrostatic repulsive forces and achieves the worst case a **3.291** path stretch approximation bound with respect to the shortest path, then uses this geo-knowledge in addition to geo-coordinates of the nodes in order to proactively avoid local minimum situtations as shown in the figure below:

![Figure](/img/SPIDER_example.jpg)

**Figure 2**: *Attractive/Repulsive Greedy Forwarding (ARGF) example: ARGF starts in Attraction mode until it reaches the repulsion zone; at node b (located outside the repulsion zone), ARGF returns back to its Attraction mode. ARGF can again switch to the Repulsion mode with guaranteed progress towards destination. At node d, ARGF returns to the Attraction mode and continue forwarding in this mode to destination.*

What is inside?
================
The source code for the Elsevier FGCS submission (SI on Information and Resource Management Systems for Internet of Things: Energy Management, Communication Protocols and Future Applications).

NS-3 simulation is used to evalute the application level throughput gained by those greedy forwarding protocols as well as by commonly used AODV and HWMP protocols under severe node failures and high mobility challenges of disaster response scenarios

Distribution
================
The distribution tree contains: 

* README

	- this file
    
* LICENSE

	- GNU license file

* img/ (folder with images used in README)
        
* ns3_sim/ (event-driven simulation of the realistic incident-supporting hierarchical cloud deployment)    
    
    - src/     (c++ source files for the SPIDER protocol implemented as part of the GPSR protocol in NS-3, see - A. Fonseca, A. Camoes, T. Vazao, “Geographical routing implementation in NS3”, Proc. of ACM ICST, 2012.)
    
    - scratch/ (c++ source files of the node high failures and mobility scenarios)
    
        ```
        SPIDER_failure_expr.cc  (main file for the high node failures simulation; the Joplin MO high school scene is used)
        ```
        
        ```
        SPIDER_mobility_expr.cc (main file for the high node mobility simulation; the Joplin MO hospital scene is used)
        ```

Compilation and run
============
Compiling and run of this software requires and NS-3 (v.3.25 or higher) installed. These can be downloaded respectively from:  
http://www.nsnam.org/
    
## NS-3 simulations
* navigate to *ns-3_sim* folder

* copy everything to your NS-3 directory
    
* refer to NS-3 manual (see https://www.nsnam.org/docs/release/3.26/tutorial/html/getting-started.html#running-a-script) to run any of the following two simulations:
        
    ```
    SPIDER_failure_expr.cc  (main file for the high node failures simulation; the Joplin MO high school scene is used)
    ```
        
    ```
    SPIDER_mobility_expr.cc (main file for the high node mobility simulation; the Joplin MO hospital scene is used)
    ```    

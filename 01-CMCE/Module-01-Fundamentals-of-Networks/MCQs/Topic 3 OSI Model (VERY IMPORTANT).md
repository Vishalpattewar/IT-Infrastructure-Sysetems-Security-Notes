Topic 3: OSI Model (VERY IMPORTANT) – 60 MCQs

🧠 Quick Memory Trick



👉 “Please Do Not Throw Sausage Pizza Away”

Physical → Data Link → Network → Transport → Session → Presentation → Application



**🔹 SECTION A: Basics \& Layer Identification**

1\. How many layers are in the OSI model?



A. 4

B. 5

C. 7

D. 8



✅ Answer: C

Explanation: OSI has 7 layers from Physical to Application.



2\. Which layer is closest to the user?



A. Physical

B. Transport

C. Application

D. Network



✅ Answer: C

Explanation: Application layer interacts directly with end users.



3\. Which layer is responsible for transmission of bits?



A. Physical

B. Data Link

C. Network

D. Transport



✅ Answer: A

Explanation: Physical layer handles raw bit transmission.



4\. Which layer provides logical addressing?



A. Data Link

B. Network

C. Transport

D. Session



✅ Answer: B

Explanation: Network layer uses IP addresses.



5\. Which layer ensures reliable delivery?



A. Network

B. Transport

C. Session

D. Physical



✅ Answer: B

Explanation: Transport layer ensures reliability (TCP).



6\. Which layer handles MAC addressing?



A. Physical

B. Data Link

C. Network

D. Session



✅ Answer: B

Explanation: Data Link uses MAC addresses.



7\. Which layer is responsible for routing?



A. Transport

B. Network

C. Data Link

D. Session



✅ Answer: B

Explanation: Routing decisions occur at Network layer.



8\. Which layer handles encryption?



A. Session

B. Presentation

C. Transport

D. Network



✅ Answer: B

Explanation: Presentation layer handles encryption/decryption.



9\. Which layer manages sessions?



A. Transport

B. Session

C. Application

D. Data Link



✅ Answer: B

Explanation: Session layer establishes and manages connections.



10\. Which layer is responsible for formatting data?



A. Application

B. Presentation

C. Session

D. Transport



✅ Answer: B

Explanation: Presentation handles format translation.



**🔹 SECTION B: Layer Functions (Common Exam Traps)**

11\. Which layer adds port numbers?



A. Network

B. Transport

C. Session

D. Data Link



✅ Answer: B

Explanation: Transport layer uses port numbers (TCP/UDP).



12\. Which layer deals with frames?



A. Physical

B. Data Link

C. Network

D. Transport



✅ Answer: B

Explanation: Data Link layer works with frames.



13\. Which layer deals with packets?



A. Network

B. Transport

C. Session

D. Physical



✅ Answer: A

Explanation: Network layer handles packets.



14\. Which layer uses bits?



A. Physical

B. Data Link

C. Network

D. Transport



✅ Answer: A

Explanation: Physical layer transmits bits.



15\. Which layer uses segments?



A. Network

B. Transport

C. Data Link

D. Session



✅ Answer: B

Explanation: Transport layer uses segments.



16\. Which layer performs error detection (CRC)?



A. Network

B. Data Link

C. Transport

D. Session



✅ Answer: B

Explanation: Data Link detects errors using CRC.



17\. Flow control occurs at:



A. Data Link \& Transport

B. Only Physical

C. Only Network

D. Session



✅ Answer: A

Explanation: Both layers handle flow control.



18\. Which layer ensures data order?



A. Network

B. Transport

C. Data Link

D. Physical



✅ Answer: B

Explanation: TCP ensures ordered delivery.



19\. Which layer provides multiplexing?



A. Transport

B. Network

C. Session

D. Physical



✅ Answer: A

Explanation: Uses port numbers for multiple sessions.



20\. Which layer is responsible for segmentation?



A. Network

B. Transport

C. Data Link

D. Application



✅ Answer: B

Explanation: Breaks data into segments.



**🔹 SECTION C: Devices \& OSI Mapping**

21\. Hub operates at:



A. Layer 1

B. Layer 2

C. Layer 3

D. Layer 4



✅ Answer: A

Explanation: Hub is a Physical layer device.



22\. Switch operates at:



A. Layer 1

B. Layer 2

C. Layer 3

D. Layer 4



✅ Answer: B

Explanation: Switch uses MAC addresses.



23\. Router operates at:



A. Layer 2

B. Layer 3

C. Layer 4

D. Layer 7



✅ Answer: B

Explanation: Router uses IP addresses.



24\. Firewall operates at:



A. Layer 3/4

B. Layer 1

C. Layer 2

D. Layer 7 only



✅ Answer: A

Explanation: Filters based on IP and ports.



25\. Which device uses frames?



A. Router

B. Switch

C. Hub

D. Repeater



✅ Answer: B

Explanation: Switch works with frames.



**🔹 SECTION D: Encapsulation (VERY IMPORTANT)**

26\. What is encapsulation?



A. Encryption

B. Wrapping data with headers

C. Routing

D. Switching



✅ Answer: B

Explanation: Each layer adds its header.



27\. Order of encapsulation (top → bottom)?



A. Segment → Packet → Frame → Bits

B. Packet → Segment → Frame → Bits

C. Frame → Packet → Segment → Bits

D. Bits → Frame → Packet → Segment



✅ Answer: A

Explanation: Transport → Network → Data Link → Physical.



28\. Decapsulation happens at:



A. Sender

B. Receiver

C. Router

D. Switch



✅ Answer: B

Explanation: Headers are removed at receiver.



29\. Frame contains:



A. IP only

B. MAC only

C. MAC + data

D. Port numbers



✅ Answer: C

Explanation: Frame includes MAC addresses.



30\. Packet contains:



A. MAC

B. IP

C. Port

D. Bits



✅ Answer: B

Explanation: Network layer uses IP addresses.



🔹 SECTION E: Protocols \& Layers

31\. HTTP belongs to:



A. Transport

B. Application

C. Network

D. Session



✅ Answer: B

Explanation: Application layer protocol.



32\. TCP belongs to:



A. Transport

B. Network

C. Data Link

D. Session



✅ Answer: A

Explanation: Transport protocol.



33\. IP belongs to:



A. Network

B. Transport

C. Session

D. Physical



✅ Answer: A

Explanation: Network layer protocol.



34\. ARP works between:



A. Layer 2 \& 3

B. Layer 1 \& 2

C. Layer 4 \& 5

D. Layer 6 \& 7



✅ Answer: A

Explanation: Maps IP to MAC.



35\. DNS operates at:



A. Layer 7

B. Layer 4

C. Layer 3

D. Layer 2



✅ Answer: A

Explanation: Application layer protocol.



**🔹 SECTION F: Scenario-Based Questions**

36\. Data corrupted during transmission → which layer detects?



A. Network

B. Data Link

C. Session

D. Application



✅ Answer: B

Explanation: CRC detects errors.



37\. Packet dropped due to wrong IP → which layer?



A. Data Link

B. Network

C. Transport

D. Session



✅ Answer: B

Explanation: Routing decisions based on IP.



38\. Application cannot understand data format → which layer issue?



A. Session

B. Presentation

C. Transport

D. Physical



✅ Answer: B

Explanation: Handles format translation.



39\. Multiple apps sending data simultaneously → which layer handles?



A. Network

B. Transport

C. Session

D. Data Link



✅ Answer: B

Explanation: Multiplexing via ports.



40\. Lost packets need retransmission → which layer?



A. Network

B. Transport

C. Data Link

D. Physical



✅ Answer: B

Explanation: TCP handles retransmission.



**🔹 SECTION G: Tricky/Confusing Concepts**

41\. Which layer does NOT add header?



A. Physical

B. Data Link

C. Network

D. Transport



✅ Answer: A

Explanation: Physical transmits bits only.



42\. Which layer is connection-oriented?



A. Network

B. Transport

C. Physical

D. Data Link



✅ Answer: B

Explanation: TCP is connection-oriented.



43\. Which layer uses MAC addresses only locally?



A. Network

B. Data Link

C. Transport

D. Session



✅ Answer: B

Explanation: MAC is local to LAN.



44\. Which layer is responsible for end-to-end communication?



A. Network

B. Transport

C. Data Link

D. Physical



✅ Answer: B

Explanation: Ensures host-to-host communication.



45\. Which layer is closest to hardware?



A. Physical

B. Data Link

C. Network

D. Transport



✅ Answer: A

Explanation: Directly interacts with hardware.



**🔹 SECTION H: Advanced/Exam-Level**

46\. Which layer performs fragmentation?



A. Network

B. Transport

C. Data Link

D. Session



✅ Answer: A

Explanation: IP fragmentation occurs at Network layer.



47\. Which layer handles session recovery?



A. Session

B. Transport

C. Network

D. Presentation



✅ Answer: A

Explanation: Maintains session checkpoints.



48\. Which layer converts ASCII to EBCDIC?



A. Session

B. Presentation

C. Transport

D. Network



✅ Answer: B

Explanation: Data format translation.



49\. Which layer ensures synchronization?



A. Session

B. Transport

C. Data Link

D. Network



✅ Answer: A

Explanation: Session maintains sync.



50\. Which layer provides services to end-user apps?



A. Transport

B. Session

C. Application

D. Presentation



✅ Answer: C

Explanation: Direct interface to user apps.



**🔹 BONUS (VERY TRICKY – HIGH CHANCE IN EXAM)**

51\. Which layer is responsible for BOTH compression \& encryption?



A. Session

B. Presentation

C. Transport

D. Network



✅ Answer: B

Explanation: Common exam trap.



52\. If MAC address is wrong, which layer fails?



A. Network

B. Data Link

C. Transport

D. Session



✅ Answer: B

Explanation: MAC belongs to Data Link.



53\. If port number is wrong, which layer fails?



A. Network

B. Transport

C. Session

D. Data Link



✅ Answer: B

Explanation: Ports belong to Transport.



54\. If IP address is wrong, which layer fails?



A. Data Link

B. Network

C. Transport

D. Session



✅ Answer: B

Explanation: IP is Network layer.



55\. Which layer provides best-effort delivery?



A. Network

B. Transport

C. Session

D. Application



✅ Answer: A

Explanation: IP does not guarantee delivery.



56\. Which layer adds sequence numbers?



A. Transport

B. Network

C. Data Link

D. Session



✅ Answer: A

Explanation: TCP uses sequence numbers.



57\. Which layer handles logical connections?



A. Session

B. Transport

C. Network

D. Data Link



✅ Answer: B

Explanation: Logical end-to-end connection.



58\. Which layer is used for flow control via windowing?



A. Transport

B. Network

C. Session

D. Physical



✅ Answer: A

Explanation: TCP windowing.



59\. Which layer deals with voltage levels?



A. Physical

B. Data Link

C. Network

D. Transport



✅ Answer: A

Explanation: Electrical signals.



60\. Which layer breaks data into frames?



A. Network

B. Data Link

C. Transport

D. Physical



✅ Answer: B

Explanation: Data Link creates frames.


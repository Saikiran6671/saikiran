              ASSIGNMENT-4 
                  COMP_SCI-5596A Computer Security I: Cryptology 

Sai Kiran Merugu
16321811


1.	Explain briefly why we need to involve a secure one-way hash function in generating digital signatures.

Ans: The use of a digital signature by creating a unique virtual fingerprint, it identifies an individual and secures information in a digital message or document. The message content is protected when an email is signed with a digital signature. Digital signatures are more secure than other types of electronic signatures. A digital signature encrypts a message or document with a one-of-a-kind hash derived from the sender's private key. Because each message or document generates a unique hash, if any part of it is changed, the hash will also change. After that, an electronic message or document is digitally signed and delivered to the intended recipient. The recipient creates a digital fingerprint of the message or document using the sender's public key. The recipient decrypts the message using the sender's encryption key (which was included in the original message). The sender validates their certification by comparing their decrypted hash to that of the recipient. If they are identical, the message or digital document is not altered, and the sender is verified.
A mathematical function that converts a variable-length input string into a fixed-length binary sequence is known as one-way hashing. Message digests, fingerprints, and compression algorithms are other names for these functions. One-way hash functions are designed to produce a different hash value for each input bit when computed. We use hashing to provide authentication, non-repudiation, and document integrity when we create a digital signature.
Hashing algorithms have the fundamental property that no two strings can ever have the same hash value. When two documents have the same hash value, this is referred to as a hash collision. It is critical to avoid creating two documents with the same hash value, as this could result in errors or security issues.
2.	What is the digital Envelop?

Ans: A secure electronic transaction that encrypts data sent between two parties is known as a digital envelope. Digital envelopes employ a two-layer encryption scheme that includes both private and public keys. A secret key encryption method is used to encrypt the communication, and a public key encryption method is used to deliver the secret key to the recipient. Using public key encryption has its own set of speed and security challenges, which this technique addresses. A digital envelope is a safe electronic data container that encrypts and authenticates data in order to protect a communication. Data is protected by digital envelopes, which encrypt it with secret and public keys. Rivest, Shamir, and Adleman (RSA) developed a standard for encrypting data in digital envelopes and digital signatures. A sort of digital envelope, often known as the digital wrapper.

In a digital envelope, secret (also known as symmetric key) and public encryption layers are used (also known as public key). Secret key encryption is used to encrypt and decrypt messages, whereas public key encryption is used to send a secret key across a network to a receiving party. This strategy does not require plain text communication to function.

The following are the two methods for making a digital envelope: 

• Messages are encrypted using secret key encryption methods.

• RSA is an encryption method that uses public keys to encrypt data. The public key of the receiver is used to encrypt hidden keys.



3.	In GSM 

(a)	We assume that each subscriber has been assigned an IMSI (i. e. International Mobile Subscriber Identity) and this information is publicly known. If we want to provide a service to hide this information even during the initial connection (i.e., including the registration), suggest one solution to satisfy this requirement. You need to point out how and why this solution can protect IMSI. (No more than 30 words)

Ans: A randomly generated temporary mobile subscriber ID will be sent on behalf of the IMSI, keeping the mobile subscriber ID private and removing the need to send it unencrypted over the airlink.

(b) Multiple SRESs and RANDs are stored at VLR for authentication purpose, where SRES=A3(Ki, RAND) and Ki is a pre-shared secret key between the mobile subscriber and HLR. SRES needs to be protected and used as evidence to collect service fee. Since SRES is known by both mobile subscriber and VLR, repudiation cannot be resolved. If we want to establish a partially non-repudiation services between the mobile subscriber and VLR, suggest one solution to meet this requirement. (No more than 30 words)
    
     Ans: Only a public-key device using virtual signatures can provide true non-repudiation service among HLR, VLR, and MS. A virtual signature can be used to replace HMAC in a public-key device.

4.	In most wireless communications, there are 3 entities involved in connecting a call: Mobile Subscriber (MS), VLR, and HLR.

(a)	 Suggest a method that MS can protect its identity when MS roams into a new VLR region. (i.e., MS does not need to expose its real identity to the attacker when makes the first connection through VLR)
Ans: Authentication Information Registration and Distribution (Initial Authentication) This method is used when a mobile person (MS) leaves his home area and roams to a previously visited location. The individual can also make a carrier request to the community operator of the visited area. In this case, the three events perform the preliminary authentication demonstrated in Figure 3. First, the MS sends a request message to the authentication VLR/SN within the visited area. Because the VLR/SN cannot authenticate the MS on its own, it sends it to the HLR within the MS's domestic area. The HLR is included in the cost of the verification method. 
The authentication vector is used to generate a reaction message, which is like the authentication result (AV). Based on the authentication result, the VLR/SN forwards the reaction message to the MS and decides whether to offer the carrier to the MS. The VLR/SN caches a small amount of authentication data on this location, which may be used in the next authentication. The response message informs the MS whether the authentication was successful. Following preliminary authentication, each of the VLR/SN and MS obtains the authentication result from the HLR/HN and proportion.


(b)	 If only VLR and HLR have digital certificates, can a secure channel be established between the MS and VLR? (If your answer is YES, you need to explain how.
Ans: Key Agreement and Authentication (Subsequent Authentication): After initial authentication, the VLR/SGSN can authenticate the MS in the following communication. If the MS remains within the same visited area and requests services, the individual must request additional authentication. Similarly, the MS generates an authentication request message, which must include the records shared between the MS and VLR/SN; the VLR/SN then uses these records to authenticate the MS. The VLR/SN, as previously stated, has cached the records required to authenticate MS. The VLR/SSN sends the MS a reaction message containing the authentication result after authenticating it. The MS receives the response message and determines whether or not the authentication was successful.


5.	 In SSL and TLS, why is there a separate Change Cipher Spec Protocol rather than including a Change Cipher Spec message in the Handshake Protocol?

Ans: SSL encrypts communications by using records. Encryption is done on a per-record basis. Despite this, several messages of the same type (for example, handshake messages) can be crammed into a single record. Because the Change Cipher Spec message updates encryption settings, a new record should be started immediately afterward to ensure that the new settings are implemented as soon as possible (in particular, the Finished message must utilize the new encryption and MAC for security reasons).
This property can be enforced by using a specific record type for Change Cipher Spec. Because the final message employs a different record type than the Change Cipher Spec message, an SSL/TLS implementation must create a new record for it. A specialized record type could be avoided if all SSL/TLS implementations were disciplined enough to start a new record whenever needed, and to double-check that the peer did the same. It is safer and more robust to make it inescapable through the record type.
The advantage of using IPsec is that it is transparent to end users and applications and provides a general-purpose solution. Further, IPsec includes filtering capability so that only selected traffic need incur the overhead of IPsec processing.

	SSL handshake protocol – SSL alert protocol.
	SSL change cipher spec protocol – SSL record protocol.

Connection: A connection is a mode of transportation that delivers a certain set of services. Peer-to-peer connections are what SSL calls them.

Session: An SSL session is a connection between a server and a client. The handshake protocol creates sessions. A session is a collection of cryptographic security settings that can be shared across numerous connections.

  Session Identifiers: The server chooses an arbitrary byte sequence to identify an active or    probable session state.

Compression Method: This algorithm used to compress data prior to encryption.

Master Secret: 48 bytes secret shared between client and server.

Server and Client Randoms: These are byte sequence that are chosen by the server and client for each connection.

Server Write MAC Secret: This secret key used in MAC operations on data sent by the server.

Client Write MAC Secret: This secret key used in MAC operations on data sent by the client.

Server Write Key: This secret key encryption key is used to encrypt and decrypt data that is encrypted by the server and decrypted by the client.

Client Write Key: This is symmetric key for data encrypted by client and decrypted by server.

Confidentially: The handshake protocol establishes a shared secret key that is utilized for the SSL protocol's conventional encryption.

Message Integrity: It establishes a shared secret key for forming a message authentication code (MAC).


6.	What steps are involved in the SSL Record Protocol transmission?

Ans:





 
Fragmentation: Each application message is broken down into at least 16384 bytes.

Compression: Optionally, lossless compression is used. The content length should not exceed 1024 bytes because of this compression. The compression algorithm might also be null, implying no compression.
 
Generation of Method Authentication Code: Over the compressed data from the previous phase, we compute the Message Authentication Code (MAC). This is accomplished using a shared secret key and the following calculation formula:

Hash(MAC_write_secret||pad_2|| Hash(MAC_write_secret||pad_1||seq_num||
SSLCompressed.type||SSLCompressed.length||SSLComponents.fragment)) The following terms means:
•	|| -- Concatenation
•	Hash – Cryptographic hash algorithm
•	Pad_! – The byte (00110110) repeated 48 times for MD5 and 40 times for SHA-1.
•	Pad_2 -- the byte (01011100) repeated 48 times for MD5 and 40 times for SHA-1.
•	Seq_num – The unique sequence number for this message.
•	MAC_WRITE_SECRET – Shared secret key between client and server.
•	SSLCompressed.type – The compression algorithm type used to compress this fragment.
•	SSLCompressed.length –	The length of compressed fragment.
•	SSLCompressed.fragment – The data in the compressed fragment.

Encryption:  The next step is to append generated MAC to compressed data and send the whole block for symmetric encryption. This encryption should not raise the length of this block to greater than 1024 bytes. Some of the allowed encryption algorithms are AES, RC2-40, DES, Frotezza, etc. These algorithms are used on the application where SSL used, like somewhere stream encryption is required while at other places Block cipher is required. 

Header Preparation: 
The final step is to prepare and append the header to the encrypted message. A header consists of the following.

Content Type (8 bits): The compression method used to compress the enclosed fragment data.

Major Version (8 bits): The major version of SSL used right now.
Minor Version (8 bits): The minor version of SSL used right now.
Compressed Length (16 bits): The length in bytes of the uncompressed data stored in the fragment.

The final step is to prepare and append the header to the encrypted message. A header consists of the following.

Content Type (8 bits): The compression method used to compress the enclosed fragment data.

Major Version (8 bits): The major version of SSL used right now.
Minor Version (8 bits): The minor version of SSL used right now.
Compressed Length (16 bits): The length in bytes of the uncompressed data stored in the fragment.



---
title: "Accelerating Privacy-Preserving Medical Record Linkage: A Three-Party MPC Approach"
collection: publications
category: manuscripts
permalink: /publication/PPRL
excerpt: 'A novel and efficient Privacy-Preserving Recor Linkage method based on a secure 3-party (MPC)computaion framework'
date: 2025-10-01
venue: ''
#slidesurl: 'http://academicpages.github.io/files/slides3.pdf'
paperurl: 'https://arxiv.org/abs/2410.21605'
repourl: 'https://github.com/mdppml/PPRL'
citation: 'Mağara, Ş. S., Dietrich, N., Ünal, A. B., & Akgün, M. (2024). Accelerating Privacy-Preserving Medical Record Linkage: A Three-Party MPC Approach. <i>arXiv preprint</i>, arXiv:2410.21605. https://doi.org/10.48550/arXiv.2410.21605'

---

 Record linkage is a crucial concept for integrating data from multiple sources, particularly when datasets lack exact identifiers, and it has diverse applications in real-world data analysis. Privacy-Preserving Record Linkage (PPRL) ensures this integration occurs securely, protecting sensitive information from unauthorized access. This is especially important in sectors such as healthcare, where datasets include private identity information (IDAT) governed by strict privacy laws. However, maintaining both privacy and efficiency in large-scale record linkage poses significant challenges. Consequently, researchers must develop advanced methods to protect data privacy while optimizing processing performance. This paper presents a novel and efficient PPRL method based on a secure 3-party computation (MPC) framework. Our approach allows multiple parties to compute linkage results without exposing their private inputs and significantly improves the speed of linkage process compared to existing privacy-preserving solutions. We demonstrated that our method preserves the linkage quality of the state-of-the-art PPRL method while achieving up to 14 times faster performance. For example, linking a record against a database of 10,000 records takes just 8.74 seconds in a realistic network with 700 Mbps bandwidth and 60 ms latency. Even on a slower internet connection with 100 Mbps bandwidth and 60 ms latency, the linkage completes in 28 seconds, highlighting the scalability and efficiency of our solution. 
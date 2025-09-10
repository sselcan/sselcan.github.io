---
title: "Secure and Efficient Logistic Regression With Secret-Sharing MPC and Differential Privacy"
collection: publications
category: manuscripts
permalink: /publication/DPLR
excerpt: 'Privacy-preserving approach for logistic regression that integrates secret sharing-based  multi-party computation (MPC) with differential privacy (DP).'
date: 2025-08-15
authors: "Şeyma Selcan Mağara, Ipek Motorcu, Emin Şahin Mektepli, Cem Baykara, Ali Burak Ünal, Mete Akgün"
venue: 'IEEE Access'
#slidesurl: 'http://academicpages.github.io/files/slides2.pdf'
paperurl: 'https://ieeexplore.ieee.org/abstract/document/11126887'
repourl: 'https://github.com/mdppml/DPLR'
#citation: 'Your Name, You. (2010). &quot;Paper Title Number 2.&quot; <i>Journal 1</i>. 1(2).'
---

Machine learning models are being increasingly deployed in sensitive applications where data privacy and model security are of paramount importance. This paper introduces a novel privacy-preserving approach for logistic regression that integrates secret sharing-based multi-party computation (MPC) with differential privacy (DP). Our approach ensures input data confidentiality during training via a three-party MPC protocol that supports mini-batch gradient descent, reducing computational and communication overhead compared to prior MPC methods. To protect the model against membership inference and inversion attacks, we implement DP through direct gradient perturbation that scales efficiently to high-dimensional data while preserving strong ϵ -differential privacy guarantees. Experimental results demonstrate that our approach achieves state-of-the-art efficiency without compromising privacy or model accuracy. By addressing both collaborative training privacy and model-level vulnerabilities, our work enables the secure adoption of logistic regression in scenarios requiring strict data confidentiality and robust post-deployment privacy.
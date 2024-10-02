---
layout: post
title: PV-Tuning for Extreme LLM Compression at NeurIPS 24
published: true
---


Paper [PV-Tuning: Beyond Straight-Through Estimation for Extreme LLM Compression](https://arxiv.org/abs/2405.14852) has been accepted at NeurIPS 2024.

---

<center>
<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="80px" src="https://burlachenkok.github.io/materials/neurips-logo.svg"/> </td>
</tr>
</table>
</center>


Our recent research work **PV-Tuning: Beyond Straight-Through Estimation for Extreme LLM Compression** has been accepted for presentation and proceedings at [Conference on Neural Information Processing Systems (NeurIPS) 2024](https://neurips.cc/Conferences/2024/). This year, the NeurIPS main track received 15,671 valid paper submissions, from which the program committee accepted only 25.8%.

The work will be presented at NeurIPS 2024 which will be held at the [Vancouver Convention Center, Vancouver, Canada](https://maps.app.goo.gl/XCrE3Q9ibkWK8LER9) in the form of an oral presentation.

The total number of oral presentations at NeurIPS 2024 is 61.

We demonstrated that [PV-Tuning](https://arxiv.org/abs/2405.14852) can improve quantized model accuracy compared to leading existing approaches, including:

* [QuIP](https://arxiv.org/abs/2307.13304)
* [BiLLM](https://arxiv.org/abs/2402.04291)
* [PB-LLM](https://arxiv.org/abs/2310.00034)
* [DB-LLM](https://arxiv.org/abs/2402.11960)
* [AQLM](https://arxiv.org/abs/2401.06118)
* [OneBit](https://arxiv.org/abs/2402.11295v3)
* [QuIP#](https://arxiv.org/abs/2402.04396)

The arXiv link for the paper: [https://arxiv.org/abs/2405.14852](https://arxiv.org/abs/2405.14852).

I was glad to work with my peers:
* [Prof.Peter Richtárik](https://richtarik.org/), [Ivan Ilin](https://ivan-ilin.netlify.app/), [Kai Yi](https://kaiyi.me/) from [KAUST AI Initiative](https://cemse.kaust.edu.sa/ai)
* [Prof.Dan Alistarh](https://ist.ac.at/en/research/alistarh-group/) from [IST Austria](https://ista.ac.at/en/home/), [NeuralMagic](https://neuralmagic.com/)
* [Vladimir Malinovskii](https://www.linkedin.com/in/vladimir-malinovskii-0871a51b4/), [Denis Kuznedelev](https://crei.skoltech.ru/ai/people/deniskuznedelev) from [Yandex](https://yandex.com/company/)
* [Denis Mazur](https://scholar.google.com/citations?user=rgDwAT0AAAAJ&hl=en) from [Moscow Institute of Physics and Technology](https://old.mipt.ru/english/)

----

# Abstract

There has been significant interest in "extreme" compression of large language models (LLMs), i.e., to 1-2 bits per parameter, which allows such models to be executed efficiently on resource-constrained devices. 

Existing work focused on improved one-shot quantization techniques and weight representations; yet, purely post-training approaches are reaching diminishing 
returns in terms of the accuracy-vs-bit-width trade-off. State-of-the-art quantization methods such as [QuIP#](https://arxiv.org/abs/2402.04396) and [AQLM](https://arxiv.org/abs/2401.06118) include fine-tuning (part of) 
the compressed parameters over a limited amount of calibration data; however, such fine-tuning techniques over compressed weights often make exclusive 
use of straight-through estimators (STE), whose performance is not well-understood in this setting. In this work, we question the use of STE for extreme LLM compression, showing that it can be sub-optimal, 
and perform a systematic study of quantization-aware fine-tuning strategies for LLMs.

We propose [PV-Tuning](https://arxiv.org/abs/2405.14852) - a representation-agnostic framework that generalizes and improves upon existing fine-tuning strategies 
and provides convergence guarantees in restricted cases. On the practical side, when used for 1-2 bit vector quantization, 
[PV-Tuning](https://arxiv.org/abs/2405.14852) outperforms prior techniques for highly performant models such as [Llama](https://arxiv.org/abs/2302.13971) and [Mistral](https://arxiv.org/abs/2310.06825). 
Using [PV-Tuning](https://arxiv.org/abs/2405.14852), we achieve the first Pareto-optimal quantization for Llama 2 family models at 2 bits per parameter.

# Other Links in the Media

* Prof.Dan Alistarh's Twitter post: [https://twitter.com/DAlistarh/status/1796530164215820766](https://twitter.com/DAlistarh/status/1796530164215820766)
* Prof.Peter Richtarik's post in the news: [https://richtarik.org/index.html](https://richtarik.org/index.html)
* The official implementation: [https://github.com/Vahe1994/AQLM/tree/pv-tuning](https://github.com/Vahe1994/AQLM/tree/pv-tuning)

---

<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="95px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="155px" src="https://burlachenkok.github.io/materials/mipt-logo.svg"/> </td>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="85px" src="https://burlachenkok.github.io/materials/yandex-logo.svg"/> </td>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="85px" src="https://burlachenkok.github.io/materials/ISTA-Logo-4c-rgb.svg"/> </td>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="85px" src="https://burlachenkok.github.io/materials/neural-magic.svg"/> </td>
</tr>
</table>

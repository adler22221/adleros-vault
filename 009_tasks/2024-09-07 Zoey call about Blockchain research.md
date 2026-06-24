---
title: Zoey call about Blockchain research
allDay: false
startTime: 12:00
endTime: 13:00
date: 2024-09-07
completed: 2024-09-11T00:31:19.621+08:00
type: single
---

## 豆泥參考資料

### [Digital Identity and Access Control (technometria.com)](https://www.technometria.com/p/digital-identity-and-access-control?fbclid=IwY2xjawFIEClleHRuA2FlbQIxMAABHc6RGLLQctGtHRqnDHmKrygJNYxvAlXSOVeedbcTfwoYhUE9aj4GZGvojg_aem_0FoMzp_XF4v5aBHhmjdR3g)

> Paul's comment points out the primary problem with how we build identity systems today: when access control is centralized, it inherently shifts power towards those who manage the system. This dynamic can lead to a situation where ==individuals must [[conform]] to the expectations or demands of those in [[control]], just to maintain their access to essential services or resources.==[^1] While we often accept this [[trade-off]] for [[convenience]]—like using Google to manage multiple logins—the broader implications are troubling.

> ==The more we rely on federated [[identity system]]s, with their tendency to [[centralization]], the more we risk ceding control over our digital lives, reducing our autonomy and increasing our [[dependence]] on entities whose goals may not align with our own.== This is why the principles of [[self-sovereign identity]] (SSI) are so compelling. SSI proposes a model where individuals maintain control over their own identity, reducing the risks associated with centralized access control and enhancing personal [[freedom]] in the digital realm.

> Critics of SSI will claim that giving people control over their identity means we have to accept their self assertions. Nothing could be further from the truth. When someone wants me to prove I'm over 18, I use a driver's license. The state is asserting my age, not me. But _I'm in control_ of who I show that to and where. ==[[Sovereignty]] is [about borders](https://www.windley.com/archives/2016/10/on_sovereignty.shtml) and imposes a system of relationships==.


### [NIST Releases Second Public Draft of Digital Identity Guidelines for Final Review | NIST](https://www.nist.gov/news-events/news/2024/08/nist-releases-second-public-draft-digital-identity-guidelines-final-review?fbclid=IwY2xjawFIFAhleHRuA2FlbQIxMAABHffElVxTwvg5WPCLJGOg9t_wUtS-Bn02Bs-BgWu0gS9riJZo3Go9U6ePbQ_aem_FAJm4WS0QbZNBJZznq3UcA)

> Proving one’s identity is often a necessary step in accessing services from federal agencies. Identity management is important to these agencies and other organizations, especially because fraudulent claims can be very costly to both organizations and individuals, but not everyone uses the same methods to demonstrate their identity either in person or online. Defending against fraud while maintaining accessibility for a multitude of potential users are two of the goals NIST is trying to balance with the update, Galluzzo said.

> “We want to open up the use of modern digital pathways while still allowing for physical and manual methods whenever they may be necessary.” —Ryan Galluzzo, NIST Digital Identity Program Lead

> Many of these comments focused on expanding the guidance on two technologies that are rapidly growing in use: syncable authenticators and digital credentials presented through user-controlled wallets. Syncable authenticators, often called [passkeys](https://www.nist.gov/blogs/cybersecurity-insights/giving-nist-digital-identity-guidelines-boost-supplement-incorporating "Giving NIST Digital Identity Guidelines a Boost: Supplement for Incorporating Syncable Authenticators"), offer greater security than passwords while allowing a user to save a single passkey on multiple devices. User-controlled wallets, which several major companies currently offer, can securely store payment information along with other items like plane tickets and digital versions of physical identification documents like driver’s licenses.

### [Identity & the Web (w3.org)](https://www.w3.org/reports/identity-web-impact/?fbclid=IwY2xjawFIFzFleHRuA2FlbQIxMAABHbJUg0v6WTSGdbFgkvUafA_Z2DBy--stYDOUBIIueSgBMoU-sePABbWnfw_aem_t51Te4y78gQa5NepdrI8gQ)

---
# [EBSI Basics for Adler’s ref (notion.site)](https://odditysaylabs.notion.site/EBSI-Basics-for-Adler-s-ref-e19ada2f187d4c27b22dc2a170bccebe)

## 研究方向
- EBSI發展現況追蹤分析
- ESSIF（歐盟自主身分框架）研析
	- [1._panel_-_daniel_du_seuil.pdf (europa.eu)](https://www.eesc.europa.eu/sites/default/files/files/1._panel_-_daniel_du_seuil.pdf)
	- [About ESSIF framework – ESSIF Playground](https://docs.essif.sk/en/about-essif-framework/)
	- [home - eSSIF-Lab](https://essif-lab.eu/)
- 身分驗證技術（VC）規格分析
- 協助我國與EBSI合作洽談情形

10/4初稿


## [EBSI-CAN event with EU and Canadian trust frameworks experts - YouTube](https://www.youtube.com/watch?v=HEKYobkaaiE)

![[Pasted image 20240907042739.png]]

![[Pasted image 20240907042808.png]]

![[Pasted image 20240907042838.png]]

![[Pasted image 20240907042859.png]]



- interoperability isn't just a technical issue, but also a governance issue
	- PCTF: [Trust Framework | Digital ID & Authentication Council of Canada (diacc.ca)](https://diacc.ca/trust-framework/)
	- eIDAS: [The European Digital Identity Regulation - eIDAS 2 (european-digital-identity-regulation.com)](https://www.european-digital-identity-regulation.com/)

## [EBSI W3C VCs and VPs | EBSI hub](https://hub.ebsi.eu/vc-framework/ebsi-w3c-vc-vp)

![[Pasted image 20240907042246.png]]
- Lifecycle
- APIs Relevant to the VC Lifecycle

## [IOTA Successfully Completes European Blockchain PCP](https://blog.iota.org/european-blockchain-pcp-final/)

> **TL;DR:**  
> The IOTA Foundation has successfully completed the final phase of the European Blockchain Pre-Commercial Procurement. Alongside our fellow finalists Chromaway and Billon, we've developed pre-commercial products for Intellectual Property Rights Management and Digital Product Passports, demonstrating scalability and sustainability. We are now in conversations with commercial partners to further support and drive this important European initiative in its new governance form as EUROPEUM-EDIC.

## [Revocation by EBSI](https://ec.europa.eu/digital-building-blocks/sites/download/attachments/693209363/(EBSI).(Revocation%20Whitepaper).(V1.0).pdf?api=v2)

> The revocation of VCs issued to legal entities, including Verifiable Authorisations, Verifiable Accreditations, and Verifiable Attestations, is ==not subject to the General Data Protection Regulation (GDPR)==. As such, the status of Legal Entity VCs can be managed either in the Trusted Issuers Registry on EBSI's ledger or externally. Two strategies are proposed for Verifiable Accreditation management: ==storing the status information in the EBSI Trusted Issuers Registry== or ==hosting the information by the Issuer and obtaining it via the registry==. Data structures for Verifiable Accreditation management include W3C Status List, Certificate Revocation List (CRL), and others.

> For VCs issued to natural persons, the status information for Verifiable Attestations ==must be managed per the GDPR==. Furthermore, Natural Person VC status information must be ==hosted and managed by the Issuer of the Verifiable Attestation==, and ==no personal information is stored on EBSI==. The modular design of the VC status framework enables use cases to meet their business, privacy, and security requirements by choosing from different strategies for either short-lived or long-lived VCs. Short-lived VCs involve the holder obtaining a fresh VC each time it is needed. In contrast, long-lived VCs may involve obtaining status information directly from the Trusted Issuer, through the EBSI network, or from the Issuer or a third party as a separate status VC.

The revocation and suspension framework must include the following parameters for VCs: 
- The validity of a VC is determined by three elements: the VC's inherent properties, such as a validity date (the date at and after which the VC becomes valid), the authenticity of the public keys used to sign or seal the VC along with their supporting attestations, and the status of the VC itself. 
- The status of a VC indicates its current state, which can be valid (active and acceptable for authentication), revoked (withdrawn or cancelled permanently), or suspended (temporarily disabled but may be reinstated later). 
- A VC can also be cancelled after its expiration if an expiry date has been assigned. This is often the case for VCs with a short lifetime

When a trusted issuing organisation issues a VC, information about the Issuer and data that connects the Issuer to the issued credential are stored on the immutable ledger. ==Since this data cannot be easily altered or deleted, the VC itself will remain valid until it expires. If mistake was found, access has been compromised, or issuer had to revoke the credential for other reasons, without a revocation mechanism in place, the holder could continue to use a VC for authentication purposes.== As a result, both Legal Entities and Natural Persons face several issues when verifying, changing and proving the validity of VCs issued, held, or presented to other entities.

- phone home problem
- tracking beacon problem
- tracking changes problem

## [Transatlantic SSI Interop | NGI Atlantic](https://ngiatlantic.eu/funded-experiments/transatlantic-ssi-interop)

The concept behind this experiment was to demonstrate interoperability in the area of the emerging Self-Sovereign Identity (SSI) concept, building on top of infrastructures that are being developed in the US and the EU. SSI is clearly emerging as a next-generation paradigm for digital identity that enables independence, privacy, security, and human dignity for individuals, as well as new opportunities for digital identity of organizations and things. This approach is based on inherently decentralized architectures that eliminate dependencies on centralized authorities.

At the moment, many SSI projects and initiatives are being built across the world, but each project in each country and each industry is essentially being designed and deployed in an isolated manner, not paying much attention to how to interact with other related efforts. This stands in strong contrast to both the ideology of SSI and its foundational technical building blocks such as Decentralized Identifiers (DIDs) and Verifiable Credentials (VCs), which have been designed for interoperability across both technical and political boundaries. Just like on the Internet itself, everyone should be able to communicate with everyone else independently of their location, service provider, and software, so should the various global SSI projects connect seamlessly into a single network fabric, instead of working on isolated structures that only fit limited use cases for a limited audience.

In this project, we conducted an experiment that connects SSI infrastructures in the US and the EU, and we demonstrated that decentralized digital identity based on open standards can be globally interoperable and connected. To achieve this, we built upon existing infrastructures and use case narratives that have been developed in the US and the EU.

---

# Questions

## subject matter questions:
- what's the relation between DID and VDR? How can DID be decentralized, while VDR still a government (centralized) database?
- If the DID is self-sovereigned, doesn't it mean that the key to make such self-sovereignity trust-worthy is blockchain? (then why it can be written by the old web or DNS or any other method?) 

## work related questions:
- 知能：
	- 概念、功能、流程ok
	- developer術語（e.g., JSON, API, etc.）not very ok
- 編譯？原創？
- 分工？
- 共同翻譯概念翻譯glossory

---

# ChatGPT's advice

### 1. **EBSI發展現況追蹤分析**

**EBSI（European Blockchain Services Infrastructure）**是歐盟為了促進數字身份和跨國互操作性而開發的區塊鏈平台。你需要分析其發展現況，具體可以從以下幾個方面入手：

- **現有技術框架**：EBSI的技術基礎是什麼？它如何實現跨國界的數字服務？
- **主要應用場景**：有哪些實際應用場景已經在EBSI平台上運行？
- **未來發展方向**：歐盟有哪些計劃進一步發展EBSI？

**參考資料建議**：

- [YouTube影片](https://www.youtube.com/watch?v=HEKYobkaaiE)提供了EBSI的簡介，建議先從這個視頻開始，了解基礎背景。
- [EBSI的VC規格分析](https://hub.ebsi.eu/vc-framework/ebsi-w3c-vc-vp)可以幫助你理解該平台如何處理身份驗證與數據共享問題。

### 2. **ESSIF（歐盟自主身分框架）研析**

**ESSIF**是EBSI的一個關鍵組成部分，目的是讓個人或實體完全控制自己的數字身份。你的任務是在了解ESSIF的核心概念後，分析它在技術與政策層面上對台灣的可能影響。

- **自主身份的優勢**：ESSIF是如何解決傳統身份驗證系統的缺點？
- **技術規格與應用場景**：ESSIF是如何使用區塊鏈技術實現自主身份的？
- **與我國的合作潛力**：台灣是否可以參考或採納類似框架？

**參考資料建議**：

- [IOTA文章](https://blog.iota.org/european-blockchain-pcp-final/)中有關歐盟區塊鏈自主身份的實例，可以幫助你了解ESSIF的實際應用。

### 3. **身分驗證技術（VC）規格分析**

**VC（Verifiable Credentials）**是一種可驗證的憑證技術，廣泛應用於數字身份驗證。這項任務要求你研究該技術的標準和在不同平台上的應用，特別是在EBSI中的應用。

- **VC的技術原理**：什麼是VC，它是如何工作的？
- **VC與EBSI的整合**：VC如何在EBSI中實現安全和隱私保護？
- **國際標準**：VC在全球範圍內的應用有哪些？是否與我國的身份驗證系統相兼容？

**參考資料建議**：

- [EBSI VC框架](https://hub.ebsi.eu/vc-framework/ebsi-w3c-vc-vp)文件詳細解釋了VC在EBSI中的應用，特別是W3C VC標準。

### 4. **協助我國與EBSI合作洽談情形**

這部分任務涉及具體的洽談和合作策略。你可以基於上述研究提出合作建議，包括：

- **技術合作**：我國可以在哪些技術領域與EBSI合作？
- **政策框架的兼容性**：我國是否需要調整現有的政策框架以符合EBSI的要求？
- **試點計劃**：台灣是否有可能參與EBSI的某些試點計劃？

**參考資料建議**：

- [EBSI撤銷白皮書](https://ec.europa.eu/digital-building-blocks/sites/download/attachments/693209363/(EBSI).(Revocation%20Whitepaper).(V1.0).pdf?api=v2)介紹了EBSI如何處理數字證書的撤銷機制，這對於洽談合作中的技術細節有幫助。
- [NGI Atlantic報告](https://ngi.eu/funded_solution/ngi-atlanticoc3-288/)中提到了NGI計劃，或許可以提供一些合作的方向。

---

### 工作計畫草案：

1. **任務總結**： 針對EBSI、ESSIF及VC技術進行分析，提出與EBSI的合作策略，並探索台灣在此框架下的應用潛力。
    
2. **研究步驟**：
    
    - 研究EBSI的現狀及技術框架，參考其在數字身份驗證領域的應用。
    - 分析ESSIF的自主身份技術，並探索我國可能與之對接的途徑。
    - 對VC技術進行深入研究，並評估其在EBSI及全球應用中的標準化進程。
    - 根據上述分析，提出我國與EBSI合作的策略建議。
3. **時間表**：
    
    - **1-2天內**：閱讀並分析參考資料，了解EBSI、ESSIF及VC技術的基本概念。
    - **3-4天內**：針對技術規格進行深度分析，並撰寫報告的初步草案。
    - **5天內**：整合數據與分析，制定我國與EBSI洽談的具體策略建議。
4. **會議準備**：
    
    - 整理上述分析，編寫簡報提綱。
    - 提前準備幾個與主管討論的問題，例如：EBSI的哪個技術領域最適合台灣合作？

---



[^1]: another form of [[Allocation Dependence 配分依存|allocation dependence]]
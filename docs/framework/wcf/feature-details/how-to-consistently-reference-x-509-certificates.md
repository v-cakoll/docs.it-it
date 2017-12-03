---
title: 'Procedura: riferimenti coerenti ai certificati X.509'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e92b3b4950e0a2edecc9a1f954a9f2959595c4e3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="03811-102">Procedura: riferimenti coerenti ai certificati X.509</span><span class="sxs-lookup"><span data-stu-id="03811-102">How to: Consistently Reference X.509 Certificates</span></span>
<span data-ttu-id="03811-103">È possibile identificare un certificato in diversi modi: in base all'hash del certificato, l'identificatore SKI e l'autorità emittente con il numero di serie.</span><span class="sxs-lookup"><span data-stu-id="03811-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="03811-104">L'identificatore SKI offre un sistema di identificazione univoca per la chiave pubblica del soggetto del certificato e viene spesso utilizzato con le firme digitali XML.</span><span class="sxs-lookup"><span data-stu-id="03811-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="03811-105">Il valore SKI generalmente fa parte del certificato x. 509 come un *estensione del certificato x. 509*.</span><span class="sxs-lookup"><span data-stu-id="03811-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="03811-106">è un valore predefinito *stile di riferimento* che utilizza l'autorità emittente e il numero di serie se l'estensione SKI manca il certificato.</span><span class="sxs-lookup"><span data-stu-id="03811-106"> has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="03811-107">Se il certificato contiene l'estensione SKI, lo stile di riferimento predefinito utilizza l'identificatore SKI per puntare al certificato.</span><span class="sxs-lookup"><span data-stu-id="03811-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="03811-108">A metà strada durante lo sviluppo di un'applicazione, si passa dall'utilizzo di certificati che non utilizzano l'estensione SKI a certificati che la utilizzano e anche lo stile di riferimento utilizzato nei messaggi generati da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cambia.</span><span class="sxs-lookup"><span data-stu-id="03811-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-generated messages also changes.</span></span>  
  
 <span data-ttu-id="03811-109">Se è necessario un stile di riferimento coerente indipendentemente dalla presenza dell'estensione SKI, è possibile configurare lo stile desiderato come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="03811-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03811-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="03811-110">Example</span></span>  
 <span data-ttu-id="03811-111">Nell'esempio seguente viene creato un elemento di associazione di sicurezza personalizzato che utilizza un unico stile di riferimento coerente, il nome dell'autorità emittente e il numero di serie.</span><span class="sxs-lookup"><span data-stu-id="03811-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03811-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="03811-112">Compiling the Code</span></span>  
 <span data-ttu-id="03811-113">Per compilare il codice sono necessari gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="03811-113">The following namespaces are required to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="03811-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03811-114">See Also</span></span>  
 [<span data-ttu-id="03811-115">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="03811-115">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

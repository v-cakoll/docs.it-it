---
title: 'Procedura: riferimenti coerenti ai certificati X.509'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: c13dd5ebb18df62ce64fc74da53f3f5a2e8cadb7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599087"
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="95f5c-102">Procedura: riferimenti coerenti ai certificati X.509</span><span class="sxs-lookup"><span data-stu-id="95f5c-102">How to: Consistently Reference X.509 Certificates</span></span>
<span data-ttu-id="95f5c-103">È possibile identificare un certificato in diversi modi: in base all'hash del certificato, l'identificatore SKI e l'autorità emittente con il numero di serie.</span><span class="sxs-lookup"><span data-stu-id="95f5c-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="95f5c-104">L'identificatore SKI offre un sistema di identificazione univoca per la chiave pubblica del soggetto del certificato e viene spesso utilizzato con le firme digitali XML.</span><span class="sxs-lookup"><span data-stu-id="95f5c-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="95f5c-105">Il valore SKI è in genere parte del certificato X. 509 come *estensione del certificato x. 509*.</span><span class="sxs-lookup"><span data-stu-id="95f5c-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="95f5c-106">Windows Communication Foundation (WCF) dispone di uno *stile di riferimento* predefinito che utilizza l'autorità emittente e il numero di serie se l'estensione Ski non è presente nel certificato.</span><span class="sxs-lookup"><span data-stu-id="95f5c-106">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="95f5c-107">Se il certificato contiene l'estensione SKI, lo stile di riferimento predefinito utilizza l'identificatore SKI per puntare al certificato.</span><span class="sxs-lookup"><span data-stu-id="95f5c-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="95f5c-108">Se a metà dello sviluppo di un'applicazione si passa dall'uso di certificati che non usano l'estensione SKI ai certificati che usano l'estensione SKI, viene modificato anche lo stile di riferimento usato nei messaggi generati da WCF.</span><span class="sxs-lookup"><span data-stu-id="95f5c-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="95f5c-109">Se è necessario un stile di riferimento coerente indipendentemente dalla presenza dell'estensione SKI, è possibile configurare lo stile desiderato come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="95f5c-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95f5c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="95f5c-110">Example</span></span>  
 <span data-ttu-id="95f5c-111">Nell'esempio seguente viene creato un elemento di associazione di sicurezza personalizzato che utilizza un unico stile di riferimento coerente, il nome dell'autorità emittente e il numero di serie.</span><span class="sxs-lookup"><span data-stu-id="95f5c-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="95f5c-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="95f5c-112">Compiling the Code</span></span>  
 <span data-ttu-id="95f5c-113">Per compilare il codice sono necessari gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="95f5c-113">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="95f5c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95f5c-114">See also</span></span>

- [<span data-ttu-id="95f5c-115">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="95f5c-115">Working with Certificates</span></span>](working-with-certificates.md)

---
title: Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12e30d9df9d6bb0a9f8776099951e4354d302ebf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="da572-102">Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF</span><span class="sxs-lookup"><span data-stu-id="da572-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="da572-103">A causa della differenza del modo in cui in Internet Explorer e in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene eseguita la convalida di certificati del servizio quando viene utilizzato HTTPS, è possibile che con Internet Explorer non sia possibile accedere alla pagina della Guida o a WSDL (Web Services Description Language) di un servizio, nonostante un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sia in grado di inviare messaggi correttamente agli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="da572-103">Because of difference between the way Internet Explorer and [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="da572-104">Ciò avviene perché in Internet Explorer viene verificato se il certificato del servizio dispone degli identificatori dell'oggetto (OID) `ServerAuthentication` nei flag di utilizzo migliorato, mentre in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tale vincolo non viene applicato.</span><span class="sxs-lookup"><span data-stu-id="da572-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not enforce such a constraint.</span></span> <span data-ttu-id="da572-105">Se Internet Explorer non riesce ad accedere alla pagina della Guida del servizio o il file WSDL per il servizio, utilizzare il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per accedere ai metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="da572-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da572-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da572-106">See Also</span></span>  
 [<span data-ttu-id="da572-107">Differenze di convalida dei certificati tra HTTPS, SSL su TCP e sicurezza SOAP</span><span class="sxs-lookup"><span data-stu-id="da572-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [<span data-ttu-id="da572-108">Procedura: Recuperare metadati e implementare un servizio conforme</span><span class="sxs-lookup"><span data-stu-id="da572-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)

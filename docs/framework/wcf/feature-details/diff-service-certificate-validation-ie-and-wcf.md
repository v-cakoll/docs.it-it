---
title: Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 151075f2894b895ab90418748df9face3aa70252
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599191"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="2f568-102">Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF</span><span class="sxs-lookup"><span data-stu-id="2f568-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="2f568-103">A causa della differenza tra il modo in cui Internet Explorer e Windows Communication Foundation (WCF) convalidano i certificati di servizio quando si utilizza HTTPS, è possibile che Internet Explorer non possa accedere alla pagina della guida o Web Services Description Language (WSDL) di un servizio anche se un client WCF è in grado di inviare messaggi agli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="2f568-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="2f568-104">Questo perché Internet Explorer controlla se il certificato di servizio ha gli `ServerAuthentication` identificatori di oggetto (OID) nei flag di utilizzo avanzati, mentre WCF non impone tale vincolo.</span><span class="sxs-lookup"><span data-stu-id="2f568-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="2f568-105">Se Internet Explorer non è in grado di accedere alla pagina della guida del servizio o al WSDL per il servizio, utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per accedere ai metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="2f568-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f568-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f568-106">See also</span></span>

- [<span data-ttu-id="2f568-107">Differenze di convalida del certificato tra HTTPS, SSL su TCP e protezione SOAP</span><span class="sxs-lookup"><span data-stu-id="2f568-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="2f568-108">Procedura: recuperare metadati e implementare un servizio conforme</span><span class="sxs-lookup"><span data-stu-id="2f568-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](how-to-retrieve-metadata-and-implement-a-compliant-service.md)

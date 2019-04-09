---
title: Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 0bced548cdc9423d1907de09e8b52ebe078d7c19
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225918"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="1f9c0-102">Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF</span><span class="sxs-lookup"><span data-stu-id="1f9c0-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="1f9c0-103">A causa di differenza tra la modalità Internet Explorer e Windows Communication Foundation (WCF) convalidare i certificati del servizio quando viene utilizzato HTTPS, è possibile che Internet Explorer non sarà in grado di accedere alla pagina della Guida o Web Services Description Language (Web WSDL) di un servizio anche se un client WCF è stata in grado di inviare messaggi agli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="1f9c0-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="1f9c0-104">Infatti, Internet Explorer viene verificato se il certificato del servizio dispone di `ServerAuthentication` degli identificatori (OID) dell'oggetto nel flag di utilizzo migliorato, mentre WCF non impone un vincolo di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="1f9c0-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="1f9c0-105">Se Internet Explorer è in grado di accedere alla pagina della Guida del servizio o il file WSDL per il servizio, usare il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per accedere ai metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="1f9c0-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f9c0-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f9c0-106">See also</span></span>

- [<span data-ttu-id="1f9c0-107">Differenze di convalida del certificato tra HTTPS, SSL su TCP e protezione SOAP</span><span class="sxs-lookup"><span data-stu-id="1f9c0-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="1f9c0-108">Procedura: Recuperare metadati e implementare un servizio conforme</span><span class="sxs-lookup"><span data-stu-id="1f9c0-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)

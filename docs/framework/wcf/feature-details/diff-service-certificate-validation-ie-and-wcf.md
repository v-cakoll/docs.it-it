---
title: Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 08a790dbbc8bc51a1e47bbcbcf90ec7c035bf3df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549785"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF
A causa di differenza tra la modalità Internet Explorer e Windows Communication Foundation (WCF) convalidare i certificati del servizio quando viene utilizzato HTTPS, è possibile che Internet Explorer non sarà in grado di accedere alla pagina della Guida o Web Services Description Language (Web WSDL) di un servizio anche se un client WCF è stata in grado di inviare messaggi agli endpoint del servizio. Infatti, Internet Explorer viene verificato se il certificato del servizio dispone di `ServerAuthentication` degli identificatori (OID) dell'oggetto nel flag di utilizzo migliorato, mentre WCF non impone un vincolo di questo tipo. Se Internet Explorer è in grado di accedere alla pagina della Guida del servizio o il file WSDL per il servizio, usare il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per accedere ai metadati del servizio.  
  
## <a name="see-also"></a>Vedere anche
- [Differenze di convalida dei certificati tra HTTPS, SSL su TCP e sicurezza SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Procedura: Recuperare i metadati e implementare un servizio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)

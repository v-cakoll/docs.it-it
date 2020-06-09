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
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF
A causa della differenza tra il modo in cui Internet Explorer e Windows Communication Foundation (WCF) convalidano i certificati di servizio quando si utilizza HTTPS, è possibile che Internet Explorer non possa accedere alla pagina della guida o Web Services Description Language (WSDL) di un servizio anche se un client WCF è in grado di inviare messaggi agli endpoint del servizio. Questo perché Internet Explorer controlla se il certificato di servizio ha gli `ServerAuthentication` identificatori di oggetto (OID) nei flag di utilizzo avanzati, mentre WCF non impone tale vincolo. Se Internet Explorer non è in grado di accedere alla pagina della guida del servizio o al WSDL per il servizio, utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per accedere ai metadati del servizio.  
  
## <a name="see-also"></a>Vedere anche

- [Differenze di convalida del certificato tra HTTPS, SSL su TCP e protezione SOAP](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Procedura: recuperare metadati e implementare un servizio conforme](how-to-retrieve-metadata-and-implement-a-compliant-service.md)

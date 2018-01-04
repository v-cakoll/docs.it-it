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
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Differenze tra la convalida del certificato di servizio eseguita in Internet Explorer e in WCF
A causa della differenza del modo in cui in Internet Explorer e in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene eseguita la convalida di certificati del servizio quando viene utilizzato HTTPS, è possibile che con Internet Explorer non sia possibile accedere alla pagina della Guida o a WSDL (Web Services Description Language) di un servizio, nonostante un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sia in grado di inviare messaggi correttamente agli endpoint del servizio. Ciò avviene perché in Internet Explorer viene verificato se il certificato del servizio dispone degli identificatori dell'oggetto (OID) `ServerAuthentication` nei flag di utilizzo migliorato, mentre in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tale vincolo non viene applicato. Se Internet Explorer non riesce ad accedere alla pagina della Guida del servizio o il file WSDL per il servizio, utilizzare il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per accedere ai metadati del servizio.  
  
## <a name="see-also"></a>Vedere anche  
 [Differenze di convalida dei certificati tra HTTPS, SSL su TCP e sicurezza SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [Procedura: Recuperare metadati e implementare un servizio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)

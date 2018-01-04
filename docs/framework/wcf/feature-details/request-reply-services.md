---
title: Servizi request/reply
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9e8c01fa3451cbeb335c4771e287566af1c104b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="request-reply-services"></a>Servizi request/reply
I servizi request/reply sono il tipo predefinito di contratto dell'operazione in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. I client effettuano chiamate alle operazioni del servizio e attendono una risposta dal servizio. È possibile effettuare chiamate a un'operazione del servizio in modo sincrono o asincrono. Nel primo caso, il client si blocca finché non riceve una risposta dal servizio o la chiamata scade, mentre nel secondo caso il client esegue una chiamata all'operazione del servizio, continua a funzionare e riceve la risposta dal servizio su un altro thread.  
  
 Per creare un contratto di servizio request/reply, definirlo e applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni operazione, come illustrato nel codice di esempio seguente.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 Non è necessario impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `false` perché questo è il comportamento predefinito.  
  
## <a name="see-also"></a>Vedere anche  
 [Servizi unidirezionali](../../../../docs/framework/wcf/feature-details/one-way-services.md)  
 [Servizi duplex](../../../../docs/framework/wcf/feature-details/duplex-services.md)

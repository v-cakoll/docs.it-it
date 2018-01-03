---
title: 'Procedura: personalizzare i feed con il provider di reflection (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0989436b3315f69727aeaca03d51d7fbd3cbb6fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>Procedura: personalizzare i feed con il provider di reflection (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] consente di personalizzare la serializzazione Atom in una risposta del servizio dati in modo che venga eseguito il mapping delle proprietà di un'entità agli elementi inutilizzati definiti nel protocollo AtomPub. In questo argomento viene illustrato come definire attributi di mapping per i tipi di entità in un modello di dati definito tramite il provider di reflection. Per ulteriori informazioni, vedere [personalizzazione Feed](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 Il modello di dati per questo esempio viene definito nell'argomento [procedura: creare un servizio dati tramite il Provider di Reflection](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguito il mapping di entrambe le proprietà del tipo di `Order` agli elementi Atom esistenti. Viene eseguito il mapping della proprietà `Product` del tipo di `Item` a un attributo di feed personalizzato in uno spazio dei nomi separato.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio precedente per l'URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` viene restituito il risultato seguente.  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>Vedere anche  
 [Provider di reflection](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)

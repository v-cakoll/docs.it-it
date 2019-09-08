---
title: 'Procedura: Ispezionare e modificare i messaggi sul servizio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 1356983361c483170d9d7365932b788f2421bf09
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795610"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a>Procedura: Ispezionare e modificare i messaggi sul servizio
È possibile ispezionare o modificare i messaggi in ingresso o in uscita attraverso un client Windows Communication Foundation (WCF) implementando <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> un e inserendolo nel runtime del servizio. Per ulteriori informazioni, vedere [estensione di Dispatcher](extending-dispatchers.md). La funzionalità equivalente nel servizio è <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.  
  
### <a name="to-inspect-or-modify-messages"></a>Per ispezionare o modificare i messaggi  
  
1. Implementare l'interfaccia <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.  
  
2. Implementare un'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>, a seconda dell'ambito in cui si desidera inserire facilmente il controllo dei messaggi del servizio.  
  
3. Inserire il comportamento prima di chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>. Per informazioni dettagliate, vedere [configurazione ed estensione del runtime con i comportamenti](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Esempio  
 Negli esempi di codice seguenti vengono illustrati, nell'ordine:  
  
- Un'implementazione del controllo del servizio.  
  
- Un comportamento del servizio che inserisce il controllo.  
  
- Un file di configurazione che carica ed esegue il comportamento in un'applicazione del servizio.  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [Configurazione ed estensione del runtime con i comportamenti](configuring-and-extending-the-runtime-with-behaviors.md)

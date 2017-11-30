---
title: 'Procedura: controllare o modificare i parametri'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 71e96dc3cf448b2e67b8a039f28a12df8360c76a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inspect-or-modify-parameters"></a>Procedura: controllare o modificare i parametri
È possibile controllare o modificare i messaggi in arrivo o in uscita per una singola operazione su un oggetto client [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] o un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementando l'interfaccia <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> e inserendola nel runtime del client o del servizio. In genere, viene utilizzato un comportamento dell'operazione per aggiungere controlli del parametro per una singola operazione; è tuttavia possibile utilizzare altri comportamenti per fornire facile accesso al runtime per un ambito più vasto. Per ulteriori informazioni, vedere [estensione client](../../../../docs/framework/wcf/extending/extending-clients.md) e [estensione dispatcher](../../../../docs/framework/wcf/extending/extending-dispatchers.md).  
  
### <a name="inspecting-or-modifying-parameters"></a>Controllo o modifica di parametri  
  
1.  Implementare l'interfaccia <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.  
  
2.  Implementare un'interfaccia <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (a seconda dell'ambito richiesto) per aggiungere il controllo del parametro alle proprietà <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType>.  
  
3.  Inserire il comportamento prima di chiamare il metodo <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Per informazioni dettagliate, vedere [la configurazione e l'estensione del Runtime con i comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Esempio  
 Negli esempi di codice seguenti vengono illustrati, nell'ordine:  
  
-   L'implementazione di un controllo del parametro.  
  
-   L'implementazione del comportamento che inserisce il controllo del parametro mediante <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> e <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.  
  
-   Un file di configurazione che carica ed esegue il comportamento dell'endpoint in un'applicazione client per inserire il controllo del parametro sul client.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [La configurazione e l'estensione del Runtime dei comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

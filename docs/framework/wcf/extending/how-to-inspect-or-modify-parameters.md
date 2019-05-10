---
title: 'Procedura: Controllare o modificare i parametri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
ms.openlocfilehash: 5a15de504a27180c19d3450f7e4ddd490999b916
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651111"
---
# <a name="how-to-inspect-or-modify-parameters"></a>Procedura: Controllare o modificare i parametri
È possibile ispezionare o modificare i messaggi in ingresso o in uscita per una singola operazione su un oggetto client di Windows Communication Foundation (WCF) o un servizio WCF mediante l'implementazione di <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interfaccia e inserendola nel runtime del servizio o client. In genere, viene utilizzato un comportamento dell'operazione per aggiungere controlli del parametro per una singola operazione; è tuttavia possibile utilizzare altri comportamenti per fornire facile accesso al runtime per un ambito più vasto. Per altre informazioni, vedere [client estendendo](../../../../docs/framework/wcf/extending/extending-clients.md) e [estensione dispatcher](../../../../docs/framework/wcf/extending/extending-dispatchers.md).  
  
### <a name="inspecting-or-modifying-parameters"></a>Controllo o modifica di parametri  
  
1. Implementare l'interfaccia <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.  
  
2. Implementare un'interfaccia <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (a seconda dell'ambito richiesto) per aggiungere il controllo del parametro alle proprietà <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType>.  
  
3. Inserire il comportamento prima di chiamare il metodo <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Per informazioni dettagliate, vedere [configurazione ed estensione del Runtime dei comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Esempio  
 Negli esempi di codice seguenti vengono illustrati, nell'ordine:  
  
- L'implementazione di un controllo del parametro.  
  
- L'implementazione del comportamento che inserisce il controllo del parametro mediante <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> e <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.  
  
- Un file di configurazione che carica ed esegue il comportamento dell'endpoint in un'applicazione client per inserire il controllo del parametro sul client.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione ed estensione del runtime con i comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

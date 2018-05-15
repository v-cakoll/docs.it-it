---
title: 'Procedura: controllare o modificare i parametri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
ms.openlocfilehash: 1b825ff795f4db9d570420b187b8fedd041ddd3d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-inspect-or-modify-parameters"></a><span data-ttu-id="c1487-102">Procedura: controllare o modificare i parametri</span><span class="sxs-lookup"><span data-stu-id="c1487-102">How to: Inspect or Modify Parameters</span></span>
<span data-ttu-id="c1487-103">È possibile ispezionare o modificare i messaggi in ingresso o in uscita per una singola operazione su un oggetto client di Windows Communication Foundation (WCF) o un servizio WCF mediante l'implementazione di <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interfaccia e inserendola nel runtime del client o del servizio.</span><span class="sxs-lookup"><span data-stu-id="c1487-103">You can inspect or modify the incoming or outgoing messages for a single operation on a Windows Communication Foundation (WCF) client object or a WCF service by implementing the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface and inserting it into the client or service runtime.</span></span> <span data-ttu-id="c1487-104">In genere, viene utilizzato un comportamento dell'operazione per aggiungere controlli del parametro per una singola operazione; è tuttavia possibile utilizzare altri comportamenti per fornire facile accesso al runtime per un ambito più vasto.</span><span class="sxs-lookup"><span data-stu-id="c1487-104">Typically an operation behavior is used to add parameter inspectors for a single operation; other behaviors can be used to provide easy access to the runtime at a greater scope.</span></span> <span data-ttu-id="c1487-105">Per ulteriori informazioni, vedere [estensione client](../../../../docs/framework/wcf/extending/extending-clients.md) e [estensione dispatcher](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="c1487-105">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md) and [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span>  
  
### <a name="inspecting-or-modifying-parameters"></a><span data-ttu-id="c1487-106">Controllo o modifica di parametri</span><span class="sxs-lookup"><span data-stu-id="c1487-106">Inspecting or Modifying Parameters</span></span>  
  
1.  <span data-ttu-id="c1487-107">Implementare l'interfaccia <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c1487-107">Implement the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="c1487-108">Implementare un'interfaccia <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (a seconda dell'ambito richiesto) per aggiungere il controllo del parametro alle proprietà <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c1487-108">Implement a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (depending upon the required scope) to add your parameter inspector to either the <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> or <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> properties.</span></span>  
  
3.  <span data-ttu-id="c1487-109">Inserire il comportamento prima di chiamare il metodo <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c1487-109">Insert your behavior prior to calling <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c1487-110">Per informazioni dettagliate, vedere [la configurazione e l'estensione del Runtime con i comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="c1487-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1487-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1487-111">Example</span></span>  
 <span data-ttu-id="c1487-112">Negli esempi di codice seguenti vengono illustrati, nell'ordine:</span><span class="sxs-lookup"><span data-stu-id="c1487-112">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="c1487-113">L'implementazione di un controllo del parametro.</span><span class="sxs-lookup"><span data-stu-id="c1487-113">A parameter inspector implementation.</span></span>  
  
-   <span data-ttu-id="c1487-114">L'implementazione del comportamento che inserisce il controllo del parametro mediante <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> e <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c1487-114">The behavior implementation that inserts the parameter inspector using a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, and an <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="c1487-115">Un file di configurazione che carica ed esegue il comportamento dell'endpoint in un'applicazione client per inserire il controllo del parametro sul client.</span><span class="sxs-lookup"><span data-stu-id="c1487-115">A configuration file that loads and runs the endpoint behavior in a client application to insert the parameter inspector on the client.</span></span>  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c1487-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1487-116">See Also</span></span>  
 [<span data-ttu-id="c1487-117">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="c1487-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

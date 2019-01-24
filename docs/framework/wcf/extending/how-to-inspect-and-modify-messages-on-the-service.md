---
title: 'Procedura: Esaminare e modificare i messaggi nel servizio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 19487d3f401260a7a32e9aab63b8c2a75feccbd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599634"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a><span data-ttu-id="943ce-102">Procedura: Esaminare e modificare i messaggi nel servizio</span><span class="sxs-lookup"><span data-stu-id="943ce-102">How to: Inspect and Modify Messages on the Service</span></span>
<span data-ttu-id="943ce-103">È possibile ispezionare o modificare i messaggi in ingresso o in uscita tra un client Windows Communication Foundation (WCF) implementando un <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> e inserendola nel runtime del servizio.</span><span class="sxs-lookup"><span data-stu-id="943ce-103">You can inspect or modify the incoming or outgoing messages across a Windows Communication Foundation (WCF) client by implementing a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> and inserting it into the service runtime.</span></span> <span data-ttu-id="943ce-104">Per altre informazioni, vedere [estensione di dispatcher](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="943ce-104">For more information, see [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span> <span data-ttu-id="943ce-105">La funzionalità equivalente nel servizio è <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="943ce-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="943ce-106">Per ispezionare o modificare i messaggi</span><span class="sxs-lookup"><span data-stu-id="943ce-106">To inspect or modify messages</span></span>  
  
1.  <span data-ttu-id="943ce-107">Implementare l'interfaccia <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="943ce-107">Implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="943ce-108">Implementare un'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>, a seconda dell'ambito in cui si desidera inserire facilmente il controllo dei messaggi del servizio.</span><span class="sxs-lookup"><span data-stu-id="943ce-108">Implement a <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> interface depending upon the scope at which you want to easily insert your service message inspector.</span></span>  
  
3.  <span data-ttu-id="943ce-109">Inserire il comportamento prima di chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="943ce-109">Insert your behavior prior to calling the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span></span> <span data-ttu-id="943ce-110">Per informazioni dettagliate, vedere [configurazione ed estensione del Runtime dei comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="943ce-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="943ce-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="943ce-111">Example</span></span>  
 <span data-ttu-id="943ce-112">Negli esempi di codice seguenti vengono illustrati, nell'ordine:</span><span class="sxs-lookup"><span data-stu-id="943ce-112">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="943ce-113">Un'implementazione del controllo del servizio.</span><span class="sxs-lookup"><span data-stu-id="943ce-113">A service inspector implementation.</span></span>  
  
-   <span data-ttu-id="943ce-114">Un comportamento del servizio che inserisce il controllo.</span><span class="sxs-lookup"><span data-stu-id="943ce-114">A service behavior that inserts the inspector.</span></span>  
  
-   <span data-ttu-id="943ce-115">Un file di configurazione che carica ed esegue il comportamento in un'applicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="943ce-115">A configuration file that loads and runs the behavior in a service application.</span></span>  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a><span data-ttu-id="943ce-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="943ce-116">See also</span></span>
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="943ce-117">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="943ce-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

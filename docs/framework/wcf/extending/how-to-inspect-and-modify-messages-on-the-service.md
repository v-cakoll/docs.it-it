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
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a><span data-ttu-id="7b3c3-102">Procedura: Ispezionare e modificare i messaggi sul servizio</span><span class="sxs-lookup"><span data-stu-id="7b3c3-102">How to: Inspect and Modify Messages on the Service</span></span>
<span data-ttu-id="7b3c3-103">È possibile ispezionare o modificare i messaggi in ingresso o in uscita attraverso un client Windows Communication Foundation (WCF) implementando <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> un e inserendolo nel runtime del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-103">You can inspect or modify the incoming or outgoing messages across a Windows Communication Foundation (WCF) client by implementing a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> and inserting it into the service runtime.</span></span> <span data-ttu-id="7b3c3-104">Per ulteriori informazioni, vedere [estensione di Dispatcher](extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="7b3c3-104">For more information, see [Extending Dispatchers](extending-dispatchers.md).</span></span> <span data-ttu-id="7b3c3-105">La funzionalità equivalente nel servizio è <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="7b3c3-106">Per ispezionare o modificare i messaggi</span><span class="sxs-lookup"><span data-stu-id="7b3c3-106">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="7b3c3-107">Implementare l'interfaccia <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-107">Implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="7b3c3-108">Implementare un'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>, a seconda dell'ambito in cui si desidera inserire facilmente il controllo dei messaggi del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-108">Implement a <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> interface depending upon the scope at which you want to easily insert your service message inspector.</span></span>  
  
3. <span data-ttu-id="7b3c3-109">Inserire il comportamento prima di chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-109">Insert your behavior prior to calling the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7b3c3-110">Per informazioni dettagliate, vedere [configurazione ed estensione del runtime con i comportamenti](configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="7b3c3-110">For details, see [Configuring and Extending the Runtime with Behaviors](configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b3c3-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b3c3-111">Example</span></span>  
 <span data-ttu-id="7b3c3-112">Negli esempi di codice seguenti vengono illustrati, nell'ordine:</span><span class="sxs-lookup"><span data-stu-id="7b3c3-112">The following code examples show, in order:</span></span>  
  
- <span data-ttu-id="7b3c3-113">Un'implementazione del controllo del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-113">A service inspector implementation.</span></span>  
  
- <span data-ttu-id="7b3c3-114">Un comportamento del servizio che inserisce il controllo.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-114">A service behavior that inserts the inspector.</span></span>  
  
- <span data-ttu-id="7b3c3-115">Un file di configurazione che carica ed esegue il comportamento in un'applicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-115">A configuration file that loads and runs the behavior in a service application.</span></span>  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a><span data-ttu-id="7b3c3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b3c3-116">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="7b3c3-117">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="7b3c3-117">Configuring and Extending the Runtime with Behaviors</span></span>](configuring-and-extending-the-runtime-with-behaviors.md)

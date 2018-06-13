---
title: 'Procedura: usare ChannelFactory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: b407c76c86c7b4c988da5280d76c91969c155841
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491358"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="3e6cc-102">Procedura: usare ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="3e6cc-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="3e6cc-103">La classe generica <xref:System.ServiceModel.ChannelFactory%601> viene usata in scenari avanzati che richiedono la creazione di una channel factory utilizzabile per creare più di un canale.</span><span class="sxs-lookup"><span data-stu-id="3e6cc-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="3e6cc-104">Per creare e usare la classe ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="3e6cc-104">To create and use the ChannelFactory class</span></span>  
  
1.  <span data-ttu-id="3e6cc-105">Compilare ed eseguire un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3e6cc-105">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="3e6cc-106">Per altre informazioni, vedere [progettazione e implementazione di servizi](../../../../docs/framework/wcf/designing-and-implementing-services.md), [configurazione di servizi](../../../../docs/framework/wcf/configuring-services.md), e [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e6cc-106">For more information, see [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuring Services](../../../../docs/framework/wcf/configuring-services.md), and [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
2.  <span data-ttu-id="3e6cc-107">Utilizzare il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il contratto (interfaccia) per il client.</span><span class="sxs-lookup"><span data-stu-id="3e6cc-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3.  <span data-ttu-id="3e6cc-108">Nel codice client, usare la classe <xref:System.ServiceModel.ChannelFactory%601> per creare più listener endpoint.</span><span class="sxs-lookup"><span data-stu-id="3e6cc-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e6cc-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e6cc-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]

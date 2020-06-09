---
title: 'Procedura: usare ChannelFactory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 4bb2053fb50931756e79d5346a3f14d2acbe04f6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595310"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="f2b7c-102">Procedura: usare ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="f2b7c-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="f2b7c-103">La classe generica <xref:System.ServiceModel.ChannelFactory%601> viene usata in scenari avanzati che richiedono la creazione di una channel factory utilizzabile per creare più di un canale.</span><span class="sxs-lookup"><span data-stu-id="f2b7c-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="f2b7c-104">Per creare e usare la classe ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="f2b7c-104">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="f2b7c-105">Compilazione ed esecuzione di un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f2b7c-105">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="f2b7c-106">Per ulteriori informazioni, vedere [progettazione e implementazione di servizi](../designing-and-implementing-services.md), [configurazione di servizi](../configuring-services.md)e [hosting di servizi](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f2b7c-106">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md), [Configuring Services](../configuring-services.md), and [Hosting Services](../hosting-services.md).</span></span>  
  
2. <span data-ttu-id="f2b7c-107">Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il contratto (interfaccia) per il client.</span><span class="sxs-lookup"><span data-stu-id="f2b7c-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="f2b7c-108">Nel codice client, usare la classe <xref:System.ServiceModel.ChannelFactory%601> per creare più listener endpoint.</span><span class="sxs-lookup"><span data-stu-id="f2b7c-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2b7c-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2b7c-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]

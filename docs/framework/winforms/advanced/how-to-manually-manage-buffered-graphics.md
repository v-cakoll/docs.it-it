---
title: 'Procedura: gestire manualmente le immagini memorizzate nel buffer'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 678b9ad5e8f9b40f927a35e98973cabc831c5cf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="e5bf7-102">Procedura: gestire manualmente le immagini memorizzate nel buffer</span><span class="sxs-lookup"><span data-stu-id="e5bf7-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="e5bf7-103">Per scenari di buffering doppio più avanzati, è possibile utilizzare il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classi per implementare la logica del doppio buffer.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-103">For more advanced double buffering scenarios, you can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="e5bf7-104">La classe responsabile per l'allocazione e gestione dei singoli buffer grafici è la <xref:System.Drawing.BufferedGraphicsContext> classe.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="e5bf7-105">Ogni applicazione dispone di un proprio oggetto predefinito <xref:System.Drawing.BufferedGraphicsContext> che gestisce tutto il buffering doppio predefinito per tale applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="e5bf7-106">È possibile recuperare un riferimento a questa istanza chiamando il <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="e5bf7-107">Per ottenere un riferimento a BufferedGraphicsContext predefinito</span><span class="sxs-lookup"><span data-stu-id="e5bf7-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="e5bf7-108">Impostare il <xref:System.Drawing.BufferedGraphicsManager.Current%2A> proprietà, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <span data-ttu-id="e5bf7-109">Non è necessario chiamare il `Dispose` metodo il <xref:System.Drawing.BufferedGraphicsContext> riferimento che si riceve dalla <xref:System.Drawing.BufferedGraphicsManager> classe.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="e5bf7-110">Il <xref:System.Drawing.BufferedGraphicsManager> gestisce tutta l'allocazione di memoria e la distribuzione per impostazione predefinita <xref:System.Drawing.BufferedGraphicsContext> istanze.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="e5bf7-111">Per applicazioni grafiche quali animazione, in alcuni casi è possibile migliorare le prestazioni utilizzando un oggetto <xref:System.Drawing.BufferedGraphicsContext> anziché il <xref:System.Drawing.BufferedGraphicsContext> fornito dal <xref:System.Drawing.BufferedGraphicsManager>.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="e5bf7-112">In questo modo è possibile creare e gestire i buffer grafici singolarmente, senza l'overhead delle prestazioni della gestione di tutti gli altri buffer grafici associati all'applicazione, anche se la memoria utilizzata dall'applicazione sarà maggiore.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="e5bf7-113">Per creare un BufferedGraphicsContext dedicato</span><span class="sxs-lookup"><span data-stu-id="e5bf7-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="e5bf7-114">Dichiarare e creare una nuova istanza di <xref:System.Drawing.BufferedGraphicsContext> classe, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="e5bf7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5bf7-115">See Also</span></span>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [<span data-ttu-id="e5bf7-116">Grafica a doppio buffer</span><span class="sxs-lookup"><span data-stu-id="e5bf7-116">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [<span data-ttu-id="e5bf7-117">Procedura: Eseguire il rendering manuale di grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="e5bf7-117">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)

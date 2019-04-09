---
title: 'Procedura: Gestire manualmente la grafica memorizzata nel buffer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 965e3225f8cf1af6d61b81434089ebacac8ad13a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138671"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="37a54-102">Procedura: Gestire manualmente la grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="37a54-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="37a54-103">Per scenari più avanzati memorizzazione nel buffer, è possibile usare il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classi per implementare la propria logica di doppio buffer.</span><span class="sxs-lookup"><span data-stu-id="37a54-103">For more advanced double buffering scenarios, you can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="37a54-104">La classe responsabile dell'allocazione e la gestione di singoli buffer di grafica è la <xref:System.Drawing.BufferedGraphicsContext> classe.</span><span class="sxs-lookup"><span data-stu-id="37a54-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="37a54-105">Ogni applicazione dispone di un proprio predefinito <xref:System.Drawing.BufferedGraphicsContext> che gestisce tutto il doppio buffer predefinito per tale applicazione.</span><span class="sxs-lookup"><span data-stu-id="37a54-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="37a54-106">È possibile recuperare un riferimento a questa istanza chiamando il <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="37a54-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="37a54-107">Per ottenere un riferimento a BufferedGraphicsContext predefinito</span><span class="sxs-lookup"><span data-stu-id="37a54-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="37a54-108">Impostare il <xref:System.Drawing.BufferedGraphicsManager.Current%2A> proprietà, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="37a54-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <span data-ttu-id="37a54-109">Non è necessario chiamare il `Dispose` metodo sul <xref:System.Drawing.BufferedGraphicsContext> riferimento ricevuto dal <xref:System.Drawing.BufferedGraphicsManager> classe.</span><span class="sxs-lookup"><span data-stu-id="37a54-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="37a54-110">Il <xref:System.Drawing.BufferedGraphicsManager> provvede a tutto l'allocazione di memoria e la distribuzione per impostazione predefinita <xref:System.Drawing.BufferedGraphicsContext> istanze.</span><span class="sxs-lookup"><span data-stu-id="37a54-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="37a54-111">Per le applicazioni a grafica intensiva, ad esempio di animazione, è talvolta possibile migliorare le prestazioni usando un oggetto dedicato <xref:System.Drawing.BufferedGraphicsContext> anziché il <xref:System.Drawing.BufferedGraphicsContext> forniti dal <xref:System.Drawing.BufferedGraphicsManager>.</span><span class="sxs-lookup"><span data-stu-id="37a54-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="37a54-112">In questo modo è possibile creare e gestire singolarmente, buffer di grafica senza l'overhead delle prestazioni di gestione di tutti gli altri buffer grafici associati all'applicazione, anche se la memoria utilizzata dall'applicazione sarà maggiore.</span><span class="sxs-lookup"><span data-stu-id="37a54-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="37a54-113">Per creare un BufferedGraphicsContext dedicato</span><span class="sxs-lookup"><span data-stu-id="37a54-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="37a54-114">Dichiarare e creare una nuova istanza di <xref:System.Drawing.BufferedGraphicsContext> classe, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="37a54-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="37a54-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37a54-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="37a54-116">Grafica a doppio buffer</span><span class="sxs-lookup"><span data-stu-id="37a54-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="37a54-117">Procedura: Eseguire il rendering manuale della grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="37a54-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)

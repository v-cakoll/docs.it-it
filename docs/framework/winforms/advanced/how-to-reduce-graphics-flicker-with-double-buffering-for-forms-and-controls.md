---
title: 'Procedura: ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli'
description: Informazioni su come ridurre lo sfarfallio nella grafica con il doppio buffer per Windows Forms e usare i controlli per risolvere i problemi di sfarfallio associati alle operazioni di disegno.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: f7c0425729f8a1a780124621788a1c49e06e0c4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618129"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="62220-103">Procedura: ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli</span><span class="sxs-lookup"><span data-stu-id="62220-103">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="62220-104">Il doppio buffer usa un buffer di memoria per risolvere i problemi di sfarfallio associati a più operazioni di disegno.</span><span class="sxs-lookup"><span data-stu-id="62220-104">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="62220-105">Quando il doppio buffer è abilitato, tutte le operazioni di disegno vengono prima sottoposte a rendering in un buffer di memoria invece che nella superficie di disegno visualizzata.</span><span class="sxs-lookup"><span data-stu-id="62220-105">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="62220-106">Dopo che tutte le operazioni di disegno sono state completate, il buffer di memoria viene copiato direttamente nella superficie di disegno associata.</span><span class="sxs-lookup"><span data-stu-id="62220-106">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="62220-107">Poiché sullo schermo viene eseguita una sola operazione grafica, lo sfarfallio dell'immagine associato a operazioni di disegno complesse viene eliminato. Per la maggior parte delle applicazioni, il doppio buffer predefinito fornito dal .NET Framework fornirà i risultati migliori.</span><span class="sxs-lookup"><span data-stu-id="62220-107">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the .NET Framework will provide the best results.</span></span> <span data-ttu-id="62220-108">Per impostazione predefinita, i controlli Windows Forms standard vengono memorizzati nel buffer doppio.</span><span class="sxs-lookup"><span data-stu-id="62220-108">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="62220-109">È possibile abilitare il doppio buffer predefinito nei form e nei controlli creati in due modi.</span><span class="sxs-lookup"><span data-stu-id="62220-109">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="62220-110">È possibile impostare la <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà su `true` oppure è possibile chiamare il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo per impostare il <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag su `true` .</span><span class="sxs-lookup"><span data-stu-id="62220-110">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="62220-111">Entrambi i metodi consentiranno il doppio buffer predefinito per il form o il controllo e forniranno il rendering della grafica senza sfarfallio.</span><span class="sxs-lookup"><span data-stu-id="62220-111">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="62220-112">La chiamata al <xref:System.Windows.Forms.Control.SetStyle%2A> metodo è consigliata solo per i controlli personalizzati per i quali è stato scritto tutto il codice di rendering.</span><span class="sxs-lookup"><span data-stu-id="62220-112">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="62220-113">Per gli scenari di doppio buffer più avanzati, ad esempio l'animazione o la gestione avanzata della memoria, è possibile implementare la logica di doppio buffer.</span><span class="sxs-lookup"><span data-stu-id="62220-113">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="62220-114">Per altre informazioni, vedere [procedura: gestire manualmente le immagini memorizzate nel buffer](how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="62220-114">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="62220-115">Per ridurre lo sfarfallio</span><span class="sxs-lookup"><span data-stu-id="62220-115">To reduce flicker</span></span>  
  
- <span data-ttu-id="62220-116">Impostare la proprietà <xref:System.Windows.Forms.Control.DoubleBuffered%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="62220-116">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="62220-117">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="62220-117">\- or -</span></span>  
  
- <span data-ttu-id="62220-118">Chiamare il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo per impostare il <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag su `true` .</span><span class="sxs-lookup"><span data-stu-id="62220-118">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="62220-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62220-119">See also</span></span>

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [<span data-ttu-id="62220-120">Grafica a doppio buffer</span><span class="sxs-lookup"><span data-stu-id="62220-120">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="62220-121">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="62220-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)

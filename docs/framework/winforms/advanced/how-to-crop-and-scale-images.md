---
title: 'Procedura: ritagliare e adattare immagini'
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
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8fb5d527cd1047197f370c4a9a9b1f8f33461653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="850d8-102">Procedura: ritagliare e adattare immagini</span><span class="sxs-lookup"><span data-stu-id="850d8-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="850d8-103">Il <xref:System.Drawing.Graphics> classe sono disponibili numerosi <xref:System.Drawing.Graphics.DrawImage%2A> metodi, alcuni dei quali dispongono di parametri dei rettangoli di origine e di destinazione che è possibile usare per ritagliare e adattare le immagini.</span><span class="sxs-lookup"><span data-stu-id="850d8-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="850d8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="850d8-104">Example</span></span>  
 <span data-ttu-id="850d8-105">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file di disco Apple.</span><span class="sxs-lookup"><span data-stu-id="850d8-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="850d8-106">Il codice disegna l'immagine intera apple nelle dimensioni originali.</span><span class="sxs-lookup"><span data-stu-id="850d8-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="850d8-107">Il codice chiama quindi il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto su cui disegnare una parte dell'immagine di apple in un rettangolo di destinazione che è maggiore dell'immagine originale.</span><span class="sxs-lookup"><span data-stu-id="850d8-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="850d8-108">Il <xref:System.Drawing.Graphics.DrawImage%2A> metodo determina la porzione di apple per disegnare esaminando il rettangolo di origine, specificato dal terzo, quarto, quinto e sesto argomento.</span><span class="sxs-lookup"><span data-stu-id="850d8-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="850d8-109">In questo caso, la mela verrà ridotta al 75% della larghezza e il 75% dell'altezza.</span><span class="sxs-lookup"><span data-stu-id="850d8-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="850d8-110">Il <xref:System.Drawing.Graphics.DrawImage%2A> metodo consente di determinare la posizione in cui disegnare la mela e quali dimensioni ritagliata esaminando il rettangolo di destinazione, specificato dal secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="850d8-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="850d8-111">In questo caso, il rettangolo di destinazione è maggiore del 30% e il 30% più alto rispetto all'originale.</span><span class="sxs-lookup"><span data-stu-id="850d8-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="850d8-112">Nella figura seguente viene illustrato l'originale e l'immagine adattata, ritagliata.</span><span class="sxs-lookup"><span data-stu-id="850d8-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 <span data-ttu-id="850d8-113">![Ritaglio e adattamento](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span><span class="sxs-lookup"><span data-stu-id="850d8-113">![Crop & Scale](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="850d8-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="850d8-114">Compiling the Code</span></span>  
 <span data-ttu-id="850d8-115">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="850d8-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="850d8-116">Assicurarsi di sostituire `Apple.gif` con un nome di file di immagine e un percorso valido per il sistema.</span><span class="sxs-lookup"><span data-stu-id="850d8-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="850d8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="850d8-117">See Also</span></span>  
 [<span data-ttu-id="850d8-118">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="850d8-118">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="850d8-119">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="850d8-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

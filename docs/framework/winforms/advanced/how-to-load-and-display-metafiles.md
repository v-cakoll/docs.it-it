---
title: 'Procedura: caricare e visualizzare metafile'
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
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 722b6d36801c69e500535a32e952ef8f45634d03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="e131f-102">Procedura: caricare e visualizzare metafile</span><span class="sxs-lookup"><span data-stu-id="e131f-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="e131f-103">Il <xref:System.Drawing.Imaging.Metafile> classe che eredita la <xref:System.Drawing.Image> classe, fornisce metodi per la registrazione, la visualizzazione e l'esame di immagini vettoriali.</span><span class="sxs-lookup"><span data-stu-id="e131f-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e131f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e131f-104">Example</span></span>  
 <span data-ttu-id="e131f-105">Per visualizzare un'immagine di vettoriali (metafile) sullo schermo, è necessario un <xref:System.Drawing.Imaging.Metafile> oggetto e un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e131f-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e131f-106">Passare il nome di un file (o un flusso) a un <xref:System.Drawing.Imaging.Metafile> costruttore.</span><span class="sxs-lookup"><span data-stu-id="e131f-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="e131f-107">Dopo aver creato un <xref:System.Drawing.Imaging.Metafile> dell'oggetto, quindi passare tale <xref:System.Drawing.Imaging.Metafile> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e131f-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="e131f-108">Nell'esempio viene creato un <xref:System.Drawing.Imaging.Metafile> oggetto da un file EMF (enhanced metafile, metafile) e quindi disegna l'immagine con il relativo angolo superiore sinistro a (60, 10).</span><span class="sxs-lookup"><span data-stu-id="e131f-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="e131f-109">Nella figura seguente viene illustrato il metafile disegnato nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="e131f-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="e131f-110">![Immagine di posizione](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="e131f-110">![Image Position](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e131f-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e131f-111">Compiling the Code</span></span>  
 <span data-ttu-id="e131f-112">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="e131f-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e131f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e131f-113">See Also</span></span>  
 [<span data-ttu-id="e131f-114">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="e131f-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

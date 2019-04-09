---
title: 'Procedura: Caricare e visualizzare metafile'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 39b7251b2789c7410e1d59b4aa7990a2f73055fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229355"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="fe933-102">Procedura: Caricare e visualizzare metafile</span><span class="sxs-lookup"><span data-stu-id="fe933-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="fe933-103">Il <xref:System.Drawing.Imaging.Metafile> classe che eredita dal <xref:System.Drawing.Image> classe, fornisce i metodi per la registrazione, la visualizzazione e analisi di immagini vettoriali.</span><span class="sxs-lookup"><span data-stu-id="fe933-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe933-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe933-104">Example</span></span>  
 <span data-ttu-id="fe933-105">Per visualizzare un'immagine di vettoriali (metafile) sullo schermo, è necessario un <xref:System.Drawing.Imaging.Metafile> oggetto e un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="fe933-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="fe933-106">Passare il nome di un file (o un flusso) per un <xref:System.Drawing.Imaging.Metafile> costruttore.</span><span class="sxs-lookup"><span data-stu-id="fe933-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="fe933-107">Dopo aver creato un <xref:System.Drawing.Imaging.Metafile> dell'oggetto, quindi passare tale <xref:System.Drawing.Imaging.Metafile> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="fe933-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="fe933-108">Nell'esempio viene creato un <xref:System.Drawing.Imaging.Metafile> oggetto da un file EMF (metafile avanzato), quindi viene disegnata l'immagine con relativo angolo superiore sinistro a (60, 10).</span><span class="sxs-lookup"><span data-stu-id="fe933-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="fe933-109">La figura seguente mostra il metafile disegnato in corrispondenza della posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="fe933-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="fe933-110">![Posizione di immagine](./media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="fe933-110">![Image Position](./media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fe933-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fe933-111">Compiling the Code</span></span>  
 <span data-ttu-id="fe933-112">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="fe933-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe933-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe933-113">See also</span></span>

- [<span data-ttu-id="fe933-114">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="fe933-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)

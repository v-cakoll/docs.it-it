---
title: 'Procedura: Disegnare una Bitmap esistente sullo schermo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: d8c118d9561c0fe993228cb6bd8cebcd156d411d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586722"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="d19df-102">Procedura: Disegnare una Bitmap esistente sullo schermo</span><span class="sxs-lookup"><span data-stu-id="d19df-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="d19df-103">È possibile creare facilmente un'immagine esistente sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="d19df-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="d19df-104">Prima di tutto è necessario creare un <xref:System.Drawing.Bitmap> utilizzando il costruttore di mappa di bit che accetta un nome file, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="d19df-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="d19df-105">Questo costruttore accetta le immagini con diversi formati di file diversi, tra cui BMP, GIF, JPEG, PNG e TIFF.</span><span class="sxs-lookup"><span data-stu-id="d19df-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="d19df-106">Dopo aver creato il <xref:System.Drawing.Bitmap> dell'oggetto, quindi passare tale <xref:System.Drawing.Bitmap> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d19df-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d19df-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="d19df-107">Example</span></span>  
 <span data-ttu-id="d19df-108">Questo esempio viene creato un <xref:System.Drawing.Bitmap> oggetto da un file JPEG e quindi consente di disegnare la bitmap con relativo angolo superiore sinistro a (60, 10).</span><span class="sxs-lookup"><span data-stu-id="d19df-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="d19df-109">La figura seguente mostra la bitmap disegnata in corrispondenza della posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="d19df-109">The following illustration shows the bitmap drawn at the specified location.</span></span>  
  
 <span data-ttu-id="d19df-110">![Posizione di immagine](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span><span class="sxs-lookup"><span data-stu-id="d19df-110">![Image Position](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d19df-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d19df-111">Compiling the Code</span></span>  
 <span data-ttu-id="d19df-112">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="d19df-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d19df-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d19df-113">See also</span></span>
- [<span data-ttu-id="d19df-114">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="d19df-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="d19df-115">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="d19df-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

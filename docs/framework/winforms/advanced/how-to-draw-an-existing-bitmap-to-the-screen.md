---
title: 'Procedura: Disegnare una bitmap esistente sullo schermo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: 90511adf9caffe7952e270d6fe32dd85162a29d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004187"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="d20d9-102">Procedura: Disegnare una bitmap esistente sullo schermo</span><span class="sxs-lookup"><span data-stu-id="d20d9-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="d20d9-103">È possibile creare facilmente un'immagine esistente sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="d20d9-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="d20d9-104">Prima di tutto è necessario creare un <xref:System.Drawing.Bitmap> utilizzando il costruttore di mappa di bit che accetta un nome file, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="d20d9-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="d20d9-105">Questo costruttore accetta le immagini con diversi formati di file diversi, tra cui BMP, GIF, JPEG, PNG e TIFF.</span><span class="sxs-lookup"><span data-stu-id="d20d9-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="d20d9-106">Dopo aver creato il <xref:System.Drawing.Bitmap> dell'oggetto, quindi passare tale <xref:System.Drawing.Bitmap> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d20d9-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d20d9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="d20d9-107">Example</span></span>  
 <span data-ttu-id="d20d9-108">Questo esempio viene creato un <xref:System.Drawing.Bitmap> oggetto da un file JPEG e quindi consente di disegnare la bitmap con relativo angolo superiore sinistro a (60, 10).</span><span class="sxs-lookup"><span data-stu-id="d20d9-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="d20d9-109">La figura seguente mostra la bitmap disegnata in corrispondenza della posizione specificata:</span><span class="sxs-lookup"><span data-stu-id="d20d9-109">The following illustration shows the bitmap drawn at the specified location:</span></span>  
  
 ![Screenshot che mostra un'immagine in una posizione specificata.](./media/how-to-draw-an-existing-bitmap-to-the-screen/bitmap-specified-position.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d20d9-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d20d9-111">Compiling the Code</span></span>  
 <span data-ttu-id="d20d9-112">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d20d9-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d20d9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d20d9-113">See also</span></span>

- [<span data-ttu-id="d20d9-114">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="d20d9-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="d20d9-115">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="d20d9-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)

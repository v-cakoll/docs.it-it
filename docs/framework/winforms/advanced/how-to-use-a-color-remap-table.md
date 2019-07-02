---
title: 'Procedura: Usare una tabella per modificare il mapping dei colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505770"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="d43f5-102">Procedura: Usare una tabella per modificare il mapping dei colori</span><span class="sxs-lookup"><span data-stu-id="d43f5-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="d43f5-103">Modifica del mapping è il processo di conversione dei colori in un'immagine in base a una tabella di rimappatura dei colori.</span><span class="sxs-lookup"><span data-stu-id="d43f5-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="d43f5-104">La tabella di riassociazione cromatica è una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti.</span><span class="sxs-lookup"><span data-stu-id="d43f5-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="d43f5-105">Ciascuna <xref:System.Drawing.Imaging.ColorMap> oggetto nella matrice ha un <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà e un <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="d43f5-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="d43f5-106">Quando GDI+ disegna un'immagine, ogni pixel dell'immagine viene confrontato con la matrice di colori precedente.</span><span class="sxs-lookup"><span data-stu-id="d43f5-106">When GDI+ draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="d43f5-107">Se il colore del pixel corrisponde a un colore precedente, il relativo colore viene modificato il nuovo colore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d43f5-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="d43f5-108">I colori vengono modificati solo per il rendering, ovvero i valori di colore dell'immagine di se stesso (archiviati in un' <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> oggetto) non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="d43f5-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="d43f5-109">Per disegnare un'immagine riassociata, inizializzare una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti.</span><span class="sxs-lookup"><span data-stu-id="d43f5-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="d43f5-110">Passare la matrice per il <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> metodo di un <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto e quindi passare il <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d43f5-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d43f5-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d43f5-111">Example</span></span>  
 <span data-ttu-id="d43f5-112">L'esempio seguente crea un <xref:System.Drawing.Image> oggetto RemapInput nel file.</span><span class="sxs-lookup"><span data-stu-id="d43f5-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="d43f5-113">Il codice crea una tabella di riassociazione cromatica costituito da un singolo <xref:System.Drawing.Imaging.ColorMap> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d43f5-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="d43f5-114">Il <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà del `ColorRemap` oggetto è in rosso e il <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà è blu.</span><span class="sxs-lookup"><span data-stu-id="d43f5-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="d43f5-115">L'immagine viene disegnata una volta senza modifica del mapping e una con modifica del mapping.</span><span class="sxs-lookup"><span data-stu-id="d43f5-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="d43f5-116">Il processo di modifica del mapping modifica tutti i pixel rosso a blu.</span><span class="sxs-lookup"><span data-stu-id="d43f5-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="d43f5-117">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine rimappato a destra.</span><span class="sxs-lookup"><span data-stu-id="d43f5-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 ![Screenshot che mostra l'immagine originale e l'immagine riassociata.](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d43f5-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d43f5-119">Compiling the Code</span></span>  
 <span data-ttu-id="d43f5-120">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d43f5-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d43f5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d43f5-121">See also</span></span>

- [<span data-ttu-id="d43f5-122">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="d43f5-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="d43f5-123">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="d43f5-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)

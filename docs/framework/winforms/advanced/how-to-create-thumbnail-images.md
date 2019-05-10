---
title: 'Procedura: Creare miniature'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 275041372bd5e7da5dd0b32dc0a3d70a38bd0dcd
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063759"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="0be9c-102">Procedura: Creare miniature</span><span class="sxs-lookup"><span data-stu-id="0be9c-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="0be9c-103">Un'immagine di anteprima è una versione ridotta dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0be9c-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="0be9c-104">È possibile creare un'immagine di anteprima chiamando il <xref:System.Drawing.Image.GetThumbnailImage%2A> metodo di un <xref:System.Drawing.Image> oggetto.</span><span class="sxs-lookup"><span data-stu-id="0be9c-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0be9c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="0be9c-105">Example</span></span>  
 <span data-ttu-id="0be9c-106">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto da un file JPG.</span><span class="sxs-lookup"><span data-stu-id="0be9c-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="0be9c-107">L'immagine originale ha una larghezza pari a 640 pixel e un'altezza pari a 479 pixel.</span><span class="sxs-lookup"><span data-stu-id="0be9c-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="0be9c-108">Il codice crea un'immagine di anteprima con una larghezza pari a 100 pixel e un'altezza pari a 100 pixel.</span><span class="sxs-lookup"><span data-stu-id="0be9c-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="0be9c-109">La figura seguente mostra l'immagine di anteprima:</span><span class="sxs-lookup"><span data-stu-id="0be9c-109">The following illustration shows the thumbnail image:</span></span>  
  
 ![Screenshot che mostra l'anteprima di output.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
>  <span data-ttu-id="0be9c-111">In questo esempio, un metodo di callback viene dichiarato, ma mai usato.</span><span class="sxs-lookup"><span data-stu-id="0be9c-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="0be9c-112">Supporta tutte le versioni di GDI+.</span><span class="sxs-lookup"><span data-stu-id="0be9c-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0be9c-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0be9c-113">Compiling the Code</span></span>  
 <span data-ttu-id="0be9c-114">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0be9c-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0be9c-115">Per eseguire l'esempio, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="0be9c-115">To run the example, follow these steps:</span></span>  
  
1. <span data-ttu-id="0be9c-116">Creare una nuova applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0be9c-116">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="0be9c-117">Aggiungere il codice di esempio al form.</span><span class="sxs-lookup"><span data-stu-id="0be9c-117">Add the example code to the form.</span></span>  
  
3. <span data-ttu-id="0be9c-118">Creare un gestore per il form <xref:System.Windows.Forms.Control.Paint> evento</span><span class="sxs-lookup"><span data-stu-id="0be9c-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4. <span data-ttu-id="0be9c-119">Nel <xref:System.Windows.Forms.Control.Paint> gestore, chiamare il `GetThumbnail` metodo e passare `e` per <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="0be9c-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5. <span data-ttu-id="0be9c-120">Trovare un file di immagine che si desidera creare un'anteprima.</span><span class="sxs-lookup"><span data-stu-id="0be9c-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6. <span data-ttu-id="0be9c-121">Nel `GetThumbnail` (metodo), specificare il percorso e nome dell'immagine del file.</span><span class="sxs-lookup"><span data-stu-id="0be9c-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7. <span data-ttu-id="0be9c-122">Premere F5 per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="0be9c-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="0be9c-123">Un'immagine di anteprima di 100 per 100 viene visualizzato nel form.</span><span class="sxs-lookup"><span data-stu-id="0be9c-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be9c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0be9c-124">See also</span></span>

- [<span data-ttu-id="0be9c-125">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="0be9c-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="0be9c-126">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="0be9c-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)

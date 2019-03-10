---
title: 'Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 9e102f51d00953d05ed1d217a345e32178676ffe
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716335"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="7fae1-102">Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini</span><span class="sxs-lookup"><span data-stu-id="7fae1-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="7fae1-103">Il <xref:System.Drawing.Bitmap> classe (che eredita dal <xref:System.Drawing.Image> classe) e il <xref:System.Drawing.Imaging.ImageAttributes> classe fornisce la funzionalità per ottenere e impostare valori di pixel.</span><span class="sxs-lookup"><span data-stu-id="7fae1-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="7fae1-104">È possibile usare la <xref:System.Drawing.Imaging.ImageAttributes> valori di classe per modificare il valore alfa per un'immagine intera, oppure è possibile chiamare il <xref:System.Drawing.Bitmap.SetPixel%2A> metodo il <xref:System.Drawing.Bitmap> classe per modificare i valori dei singoli pixel.</span><span class="sxs-lookup"><span data-stu-id="7fae1-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fae1-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fae1-105">Example</span></span>  
 <span data-ttu-id="7fae1-106">Il <xref:System.Drawing.Imaging.ImageAttributes> classe ha numerose proprietà che è possibile usare per modificare le immagini durante il rendering.</span><span class="sxs-lookup"><span data-stu-id="7fae1-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="7fae1-107">Nell'esempio seguente, un <xref:System.Drawing.Imaging.ImageAttributes> oggetto viene usato per impostare tutti i valori alfa all'80% di quelle in uso.</span><span class="sxs-lookup"><span data-stu-id="7fae1-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="7fae1-108">Questa operazione viene eseguita l'inizializzazione di una matrice di colori e impostando alfa ridimensionamento valore nella matrice a 0,8.</span><span class="sxs-lookup"><span data-stu-id="7fae1-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="7fae1-109">L'indirizzo della matrice di colori viene passato per il <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo del <xref:System.Drawing.Imaging.ImageAttributes> oggetto e il <xref:System.Drawing.Imaging.ImageAttributes> oggetto viene passato al <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="7fae1-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="7fae1-110">Durante il rendering, i valori alfa nella mappa di bit vengono convertiti in l'80% del valore precedente.</span><span class="sxs-lookup"><span data-stu-id="7fae1-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="7fae1-111">Di conseguenza un'immagine che viene fusa con lo sfondo.</span><span class="sxs-lookup"><span data-stu-id="7fae1-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="7fae1-112">Come illustrato nella figura seguente, l'immagine bitmap è trasparente; è possibile visualizzare la linea nera continua attraverso di esso.</span><span class="sxs-lookup"><span data-stu-id="7fae1-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="7fae1-113">![Utilizzo di una matrice con fusione alfa](./media/image2.png "immagine2")</span><span class="sxs-lookup"><span data-stu-id="7fae1-113">![Alpha Blending Using a Matrix](./media/image2.png "image2")</span></span>  
  
 <span data-ttu-id="7fae1-114">In cui l'immagine sulla parte dello sfondo bianca, l'immagine è stato combinato con il colore bianco.</span><span class="sxs-lookup"><span data-stu-id="7fae1-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="7fae1-115">In cui l'immagine incrocia la linea nera, l'immagine viene sfumato con il colore nero.</span><span class="sxs-lookup"><span data-stu-id="7fae1-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7fae1-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7fae1-116">Compiling the Code</span></span>  
 <span data-ttu-id="7fae1-117">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="7fae1-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fae1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fae1-118">See also</span></span>
- [<span data-ttu-id="7fae1-119">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="7fae1-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="7fae1-120">Linee e riempimenti con fusione alfa</span><span class="sxs-lookup"><span data-stu-id="7fae1-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)

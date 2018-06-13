---
title: "Procedura: convertire un'immagine BMP in un'immagine PNG"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: fd890c4f17b9759d37d7625526366034c664a71a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520786"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a><span data-ttu-id="906ce-102">Procedura: convertire un'immagine BMP in un'immagine PNG</span><span class="sxs-lookup"><span data-stu-id="906ce-102">How to: Convert a BMP image to a PNG image</span></span>
<span data-ttu-id="906ce-103">Spesso può essere opportuno convertire un formato di file immagine in un altro.</span><span class="sxs-lookup"><span data-stu-id="906ce-103">Oftentimes, you will want to convert from one image file format to another.</span></span> <span data-ttu-id="906ce-104">È possibile eseguire questa conversione chiamando il metodo <xref:System.Drawing.Image.Save%2A> della classe <xref:System.Drawing.Image> e specificando l'oggetto <xref:System.Drawing.Imaging.ImageFormat> per il formato di file immagine desiderato.</span><span class="sxs-lookup"><span data-stu-id="906ce-104">You can do this conversion easily by calling the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class and specifying the <xref:System.Drawing.Imaging.ImageFormat> for the desired image file format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="906ce-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="906ce-105">Example</span></span>  
 <span data-ttu-id="906ce-106">Nell'esempio seguente viene caricata un'immagine BMP da un tipo e quindi salvata nel formato PNG.</span><span class="sxs-lookup"><span data-stu-id="906ce-106">The following example loads a BMP image from a type, and saves the image in the PNG format.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="906ce-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="906ce-107">Compiling the Code</span></span>  
 <span data-ttu-id="906ce-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="906ce-108">This example requires:</span></span>  
  
-   <span data-ttu-id="906ce-109">Applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="906ce-109">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="906ce-110">Un riferimento allo spazio dei nomi `System.Drawing.Imaging`.</span><span class="sxs-lookup"><span data-stu-id="906ce-110">A reference to the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="906ce-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="906ce-111">See Also</span></span>  
 [<span data-ttu-id="906ce-112">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="906ce-112">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="906ce-113">Uso di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="906ce-113">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)  
 [<span data-ttu-id="906ce-114">Tipi di bitmap</span><span class="sxs-lookup"><span data-stu-id="906ce-114">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)

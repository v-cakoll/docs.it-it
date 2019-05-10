---
title: 'Procedura: Elencare i codificatori installati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 2634dd96b3aa5edcecde092919eb328b7f3dadc3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626836"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="2712a-102">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="2712a-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="2712a-103">È possibile elencare i codificatori disponibili in un computer, per determinare se l'applicazione è possibile salvare in un formato di file di immagine specifico.</span><span class="sxs-lookup"><span data-stu-id="2712a-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="2712a-104">Il <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce il <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> metodi statici in modo da poter determinare quale immagine di codificatori sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="2712a-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="2712a-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.</span><span class="sxs-lookup"><span data-stu-id="2712a-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2712a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2712a-106">Example</span></span>  
 <span data-ttu-id="2712a-107">Esempio di codice seguente genera l'elenco di codificatori installati e i relativi valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="2712a-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2712a-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2712a-108">Compiling the Code</span></span>  
 <span data-ttu-id="2712a-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2712a-109">This example requires:</span></span>  
  
- <span data-ttu-id="2712a-110">Applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2712a-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="2712a-111">Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="2712a-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2712a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2712a-112">See also</span></span>

- [<span data-ttu-id="2712a-113">Procedura: Elencare i decodificatori installati</span><span class="sxs-lookup"><span data-stu-id="2712a-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="2712a-114">Uso di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="2712a-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)

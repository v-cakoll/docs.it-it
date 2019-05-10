---
title: 'Procedura: Elencare i decodificatori installati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 961862d6212b7e76812fc222d3a99f08528d9a16
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626899"
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="25a3b-102">Procedura: Elencare i decodificatori installati</span><span class="sxs-lookup"><span data-stu-id="25a3b-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="25a3b-103">È possibile elencare i decodificatori di immagini disponibili in un computer, per determinare se l'applicazione può leggere un formato di file di immagine specifico.</span><span class="sxs-lookup"><span data-stu-id="25a3b-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="25a3b-104">Il <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce il <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> metodi statici in modo da poter determinare quale immagine di decodificatori di immagini sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="25a3b-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="25a3b-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.</span><span class="sxs-lookup"><span data-stu-id="25a3b-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25a3b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="25a3b-106">Example</span></span>  
 <span data-ttu-id="25a3b-107">Esempio di codice seguente genera l'elenco dei decodificatori installati e i relativi valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="25a3b-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="25a3b-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="25a3b-108">Compiling the Code</span></span>  
 <span data-ttu-id="25a3b-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="25a3b-109">This example requires:</span></span>  
  
- <span data-ttu-id="25a3b-110">Applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="25a3b-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="25a3b-111">Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="25a3b-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a3b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25a3b-112">See also</span></span>

- [<span data-ttu-id="25a3b-113">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="25a3b-113">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="25a3b-114">Uso di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="25a3b-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)

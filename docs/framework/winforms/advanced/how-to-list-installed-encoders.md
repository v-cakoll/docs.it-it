---
title: 'Procedura: elencare i codificatori installati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 1882ce9a140fb325c29411173ba7bde717bd3f98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524755"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="7ec1c-102">Procedura: elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="7ec1c-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="7ec1c-103">È consigliabile elencare i codificatori disponibili in un computer, per determinare se l'applicazione è possibile salvare in un formato di file di immagine specifico.</span><span class="sxs-lookup"><span data-stu-id="7ec1c-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="7ec1c-104">Il <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce il <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> metodi statici in modo che è possibile determinare quali codificatori sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="7ec1c-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="7ec1c-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.</span><span class="sxs-lookup"><span data-stu-id="7ec1c-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ec1c-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ec1c-106">Example</span></span>  
 <span data-ttu-id="7ec1c-107">Esempio di codice seguente genera l'elenco di codificatori installati e i relativi valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="7ec1c-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7ec1c-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7ec1c-108">Compiling the Code</span></span>  
 <span data-ttu-id="7ec1c-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ec1c-109">This example requires:</span></span>  
  
-   <span data-ttu-id="7ec1c-110">Applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7ec1c-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="7ec1c-111">Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="7ec1c-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec1c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ec1c-112">See Also</span></span>  
 [<span data-ttu-id="7ec1c-113">Procedura: Elencare i decodificatori installati</span><span class="sxs-lookup"><span data-stu-id="7ec1c-113">How to: List Installed Decoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [<span data-ttu-id="7ec1c-114">Uso di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="7ec1c-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)

---
title: 'Procedura: elencare i codificatori installati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70f913acb2620b5c01e1aec1f1eb98b041b82a59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="d85b4-102">Procedura: elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="d85b4-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="d85b4-103">È consigliabile elencare i codificatori disponibili in un computer, per determinare se l'applicazione è possibile salvare in un formato di file di immagine specifico.</span><span class="sxs-lookup"><span data-stu-id="d85b4-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="d85b4-104">Il <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce il <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> metodi statici in modo che è possibile determinare quali codificatori sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="d85b4-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="d85b4-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.</span><span class="sxs-lookup"><span data-stu-id="d85b4-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d85b4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d85b4-106">Example</span></span>  
 <span data-ttu-id="d85b4-107">Esempio di codice seguente genera l'elenco di codificatori installati e i relativi valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d85b4-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d85b4-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d85b4-108">Compiling the Code</span></span>  
 <span data-ttu-id="d85b4-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d85b4-109">This example requires:</span></span>  
  
-   <span data-ttu-id="d85b4-110">Applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d85b4-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="d85b4-111">Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="d85b4-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d85b4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d85b4-112">See Also</span></span>  
 [<span data-ttu-id="d85b4-113">Procedura: Elencare i decodificatori installati</span><span class="sxs-lookup"><span data-stu-id="d85b4-113">How to: List Installed Decoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [<span data-ttu-id="d85b4-114">Uso di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="d85b4-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)

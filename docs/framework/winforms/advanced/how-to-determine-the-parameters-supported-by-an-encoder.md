---
title: 'Procedura: determinare i parametri supportati da un codificatore'
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
helpviewer_keywords: encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3304adc9ab22d12905bd2a6c3739d909387d82cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="fbefe-102">Procedura: determinare i parametri supportati da un codificatore</span><span class="sxs-lookup"><span data-stu-id="fbefe-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="fbefe-103">È possibile modificare i parametri di immagine, ad esempio livello di qualità e la compressione, ma è necessario conoscere quali parametri sono supportati da un codificatore di immagini specificato.</span><span class="sxs-lookup"><span data-stu-id="fbefe-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="fbefe-104">Il <xref:System.Drawing.Image> classe fornisce il <xref:System.Drawing.Image.GetEncoderParameterList%2A> metodo in modo che è possibile determinare quali parametri di immagini sono supportate per un codificatore particolare.</span><span class="sxs-lookup"><span data-stu-id="fbefe-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="fbefe-105">Specificare il codificatore con un GUID.</span><span class="sxs-lookup"><span data-stu-id="fbefe-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="fbefe-106">Il <xref:System.Drawing.Image.GetEncoderParameterList%2A> il metodo restituisce una matrice di <xref:System.Drawing.Imaging.EncoderParameter> oggetti.</span><span class="sxs-lookup"><span data-stu-id="fbefe-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbefe-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbefe-107">Example</span></span>  
 <span data-ttu-id="fbefe-108">Esempio di codice seguente restituisce i parametri supportati per il codificatore JPEG.</span><span class="sxs-lookup"><span data-stu-id="fbefe-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="fbefe-109">Utilizzare l'elenco delle categorie di parametro e i GUID associati il <xref:System.Drawing.Imaging.Encoder> Cenni preliminari sulla classe per determinare la categoria per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="fbefe-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fbefe-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fbefe-110">Compiling the Code</span></span>  
 <span data-ttu-id="fbefe-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbefe-111">This example requires:</span></span>  
  
-   <span data-ttu-id="fbefe-112">Applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fbefe-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="fbefe-113">Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="fbefe-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbefe-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbefe-114">See Also</span></span>  
 [<span data-ttu-id="fbefe-115">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="fbefe-115">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="fbefe-116">Tipi di bitmap</span><span class="sxs-lookup"><span data-stu-id="fbefe-116">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [<span data-ttu-id="fbefe-117">Uso di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="fbefe-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)

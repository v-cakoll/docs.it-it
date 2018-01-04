---
title: 'Procedura: utilizzare l''antialiasing nel testo'
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
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edd31ec5b9d94ac1791fb0f2a73522fdf4178627
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="b525e-102">Procedura: utilizzare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="b525e-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="b525e-103">*Anti-aliasing* fa riferimento un arrotondamento dei margini irregolari di grafica e testo per migliorare l'aspetto o leggibilità disegnati.</span><span class="sxs-lookup"><span data-stu-id="b525e-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="b525e-104">All'oggetto gestito [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classi, è possibile eseguire il rendering di testo con antialias di alta qualità, come testo di qualità inferiore.</span><span class="sxs-lookup"><span data-stu-id="b525e-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="b525e-105">In genere, rendering a qualità elevata richiede più tempo di elaborazione di rendering di qualità inferiore.</span><span class="sxs-lookup"><span data-stu-id="b525e-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="b525e-106">Per impostare il livello di qualità del testo, impostare il <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà di un <xref:System.Drawing.Graphics> a uno degli elementi del <xref:System.Drawing.Text.TextRenderingHint> enumerazione</span><span class="sxs-lookup"><span data-stu-id="b525e-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="b525e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b525e-107">Example</span></span>  
 <span data-ttu-id="b525e-108">Nell'esempio seguente disegna un testo con due diverse impostazioni di qualità.</span><span class="sxs-lookup"><span data-stu-id="b525e-108">The following code example draws text with two different quality settings.</span></span>  
  
 <span data-ttu-id="b525e-109">Nella figura seguente mostra l'output del codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="b525e-109">The following illustration shows the output of the cod example code.</span></span>  
  
 <span data-ttu-id="b525e-110">![Tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="b525e-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b525e-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b525e-111">Compiling the Code</span></span>  
 <span data-ttu-id="b525e-112">L'esempio di codice precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="b525e-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b525e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b525e-113">See Also</span></span>  
 [<span data-ttu-id="b525e-114">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="b525e-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)

---
title: "Procedura: Usare l'antialiasing nel testo"
ms.date: 03/30/2017
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
ms.openlocfilehash: 64b1c27b9e8b7d405dde5add105ff2e682f8ad87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534104"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="b9cf9-102">Procedura: Usare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="b9cf9-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="b9cf9-103">*Anti-aliasing* si intende l'anti-aliasing dei bordi irregolari della grafica e testo per migliorarne la leggibilità o aspetto disegnati.</span><span class="sxs-lookup"><span data-stu-id="b9cf9-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="b9cf9-104">Con managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classi, è possibile eseguire il rendering di testo con anti-aliasing di elevata qualità, nonché il testo di qualità inferiore.</span><span class="sxs-lookup"><span data-stu-id="b9cf9-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="b9cf9-105">In genere, il rendering di qualità superiore impiega più tempo di elaborazione rispetto il rendering di qualità inferiore.</span><span class="sxs-lookup"><span data-stu-id="b9cf9-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="b9cf9-106">Per impostare il livello di qualità del testo, impostare il <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà di un <xref:System.Drawing.Graphics> a uno degli elementi del <xref:System.Drawing.Text.TextRenderingHint> enumerazione</span><span class="sxs-lookup"><span data-stu-id="b9cf9-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9cf9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9cf9-107">Example</span></span>  
 <span data-ttu-id="b9cf9-108">Esempio di codice seguente crea testo con due diverse impostazioni di qualità.</span><span class="sxs-lookup"><span data-stu-id="b9cf9-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 <span data-ttu-id="b9cf9-109">Nella figura seguente mostra l'output del codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="b9cf9-109">The following illustration shows the output of the example code:</span></span>  
  
 <span data-ttu-id="b9cf9-110">![I tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="b9cf9-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b9cf9-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b9cf9-111">Compiling the Code</span></span>  
 <span data-ttu-id="b9cf9-112">Esempio di codice precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="b9cf9-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9cf9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9cf9-113">See also</span></span>
- [<span data-ttu-id="b9cf9-114">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="b9cf9-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)

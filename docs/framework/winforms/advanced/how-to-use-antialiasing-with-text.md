---
title: "Procedura: utilizzare l'antialiasing nel testo"
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
ms.openlocfilehash: 2adb33e3d05e38ee71be8a12cdc2e20dc8c55c72
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338130"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="2c032-102">Procedura: utilizzare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="2c032-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="2c032-103">*Anti-aliasing* si intende l'anti-aliasing dei margini irregolari di grafica e testo per migliorare l'aspetto o leggibilità disegnati.</span><span class="sxs-lookup"><span data-stu-id="2c032-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="2c032-104">All'oggetto gestito [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classi, è possibile eseguire il rendering di testo con antialias di alta qualità, come testo di qualità inferiore.</span><span class="sxs-lookup"><span data-stu-id="2c032-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="2c032-105">In genere, rendering a qualità elevata richiede più tempo di elaborazione più rendering qualità inferiore.</span><span class="sxs-lookup"><span data-stu-id="2c032-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="2c032-106">Per impostare il livello di qualità del testo, impostare il <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà di un <xref:System.Drawing.Graphics> a uno degli elementi del <xref:System.Drawing.Text.TextRenderingHint> enumerazione</span><span class="sxs-lookup"><span data-stu-id="2c032-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c032-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c032-107">Example</span></span>  
 <span data-ttu-id="2c032-108">Esempio di codice seguente disegna un testo con due diverse impostazioni di qualità.</span><span class="sxs-lookup"><span data-stu-id="2c032-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 <span data-ttu-id="2c032-109">Nella figura seguente mostra l'output del codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="2c032-109">The following illustration shows the output of the example code:</span></span>  
  
 <span data-ttu-id="2c032-110">![Testo caratteri](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="2c032-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2c032-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2c032-111">Compiling the Code</span></span>  
 <span data-ttu-id="2c032-112">L'esempio di codice precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="2c032-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c032-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c032-113">See Also</span></span>  
 [<span data-ttu-id="2c032-114">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="2c032-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)

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
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182478"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="b9e26-102">Procedura: utilizzare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="b9e26-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="b9e26-103">*L'antialiasing* si riferisce all'arrotondamento dei bordi frastagliati di grafica e testo disegnati per migliorarne l'aspetto o la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="b9e26-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="b9e26-104">Con le classi GDI, è possibile eseguire il rendering di testo con antialiasing di alta qualità, nonché di testo di qualità inferiore.</span><span class="sxs-lookup"><span data-stu-id="b9e26-104">With the managed GDI+ classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="b9e26-105">In genere, il rendering di qualità superiore richiede più tempo di elaborazione rispetto al rendering di qualità inferiore.</span><span class="sxs-lookup"><span data-stu-id="b9e26-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="b9e26-106">Per impostare il livello <xref:System.Drawing.Graphics.TextRenderingHint%2A> di qualità <xref:System.Drawing.Graphics> del testo, impostare la proprietà di a su uno degli elementi dell'enumerazione <xref:System.Drawing.Text.TextRenderingHint></span><span class="sxs-lookup"><span data-stu-id="b9e26-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9e26-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9e26-107">Example</span></span>  
 <span data-ttu-id="b9e26-108">Esempio di codice seguente disegna testo con due diverse impostazioni di qualità.</span><span class="sxs-lookup"><span data-stu-id="b9e26-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 <span data-ttu-id="b9e26-109">La figura seguente mostra l'output del codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="b9e26-109">The following illustration shows the output of the example code:</span></span>  
  
 ![Screenshot che mostra il testo con due diverse impostazioni di qualità.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b9e26-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b9e26-111">Compiling the Code</span></span>  
 <span data-ttu-id="b9e26-112">L'esempio di codice precedente è progettato per <xref:System.Windows.Forms.PaintEventArgs> `e`l'utilizzo con <xref:System.Windows.Forms.PaintEventHandler>Windows Form e richiede , che è un parametro di .</span><span class="sxs-lookup"><span data-stu-id="b9e26-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9e26-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9e26-113">See also</span></span>

- [<span data-ttu-id="b9e26-114">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="b9e26-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)

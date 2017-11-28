---
title: 'Procedura: creare testo con GDI'
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
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48644ce8449c8d8eea7306eff1e43539659370c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="3604b-102">Procedura: creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="3604b-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="3604b-103">Con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo il <xref:System.Windows.Forms.TextRenderer> (classe), è possibile accedere [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] funzionalità per il disegno di testo in un form o controllo.</span><span class="sxs-lookup"><span data-stu-id="3604b-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] functionality for drawing text on a form or control.</span></span> [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]<span data-ttu-id="3604b-104">il rendering del testo offre in genere prestazioni migliori e misurazione del testo più accurata [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3604b-104"> text rendering typically offers better performance and more accurate text measuring than [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3604b-105">Il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi di <xref:System.Windows.Forms.TextRenderer> classe non sono supportati per la stampa.</span><span class="sxs-lookup"><span data-stu-id="3604b-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="3604b-106">Quando si stampa, utilizzare sempre il <xref:System.Drawing.Graphics.DrawString%2A> metodi il <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="3604b-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3604b-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="3604b-107">Example</span></span>  
 <span data-ttu-id="3604b-108">Esempio di codice riportato di seguito viene illustrato come disegnare testo su più righe all'interno di un rettangolo con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="3604b-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="3604b-109">Per eseguire il rendering di testo con il <xref:System.Windows.Forms.TextRenderer> (classe), è necessario un <xref:System.Drawing.IDeviceContext>, ad esempio un <xref:System.Drawing.Graphics> e un <xref:System.Drawing.Font>, un percorso in cui disegnare il testo e il colore in cui deve essere disegnato.</span><span class="sxs-lookup"><span data-stu-id="3604b-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="3604b-110">Facoltativamente, è possibile specificare il formattazione del testo utilizzando il <xref:System.Windows.Forms.TextFormatFlags> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3604b-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="3604b-111">Per ulteriori informazioni su come ottenere un <xref:System.Drawing.Graphics>, vedere [procedura: creazione di oggetti di grafica per il disegno](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="3604b-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="3604b-112">Per ulteriori informazioni sulla creazione di un <xref:System.Drawing.Font>, vedere [procedura: creare famiglie di caratteri e i tipi di carattere](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).</span><span class="sxs-lookup"><span data-stu-id="3604b-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3604b-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3604b-113">Compiling the Code</span></span>  
 <span data-ttu-id="3604b-114">L'esempio di codice precedente è progettato per l'uso con Windows Form e richiede la <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="3604b-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3604b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3604b-115">See Also</span></span>  
 <xref:System.Windows.Forms.TextRenderer>  
 <xref:System.Drawing.Font>  
 <xref:System.Drawing.Color>  
 <xref:System.Drawing.Color>  
 [<span data-ttu-id="3604b-116">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="3604b-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)

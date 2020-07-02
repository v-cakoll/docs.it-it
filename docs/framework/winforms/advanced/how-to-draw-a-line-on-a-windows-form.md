---
title: 'Procedura: disegnare una linea in un Windows Form'
description: Informazioni su come disegnare una linea in un Form gestendo l'evento Paint, quindi eseguire il disegno usando la proprietà graphics di PaintEventArgs.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: c8e92dc265c63413275561d0e2e3aa820eaec724
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621626"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="97375-103">Procedura: disegnare una linea in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="97375-103">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="97375-104">In questo esempio viene disegnata una riga in un form.</span><span class="sxs-lookup"><span data-stu-id="97375-104">This example draws a line on a form.</span></span> <span data-ttu-id="97375-105">In genere, quando si disegna in un form, si gestisce l'evento del form <xref:System.Windows.Forms.Control.Paint> e si esegue il disegno usando la <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> , come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="97375-105">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="97375-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="97375-106">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="97375-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="97375-107">Compiling the Code</span></span>  
 <span data-ttu-id="97375-108">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="97375-108">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="97375-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="97375-109">Robust Programming</span></span>  
 <span data-ttu-id="97375-110">È sempre necessario chiamare <xref:System.IDisposable.Dispose%2A> sugli oggetti che utilizzano risorse di sistema, ad esempio <xref:System.Drawing.Pen> gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="97375-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97375-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97375-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="97375-112">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="97375-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="97375-113">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="97375-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="97375-114">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="97375-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)

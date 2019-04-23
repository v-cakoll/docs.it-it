---
title: 'Procedura: Disegnare una linea in un Windows Form'
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
ms.openlocfilehash: aab04b9236175cedd154b817db5a6f6450503105
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074449"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="89727-102">Procedura: Disegnare una linea in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="89727-102">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="89727-103">In questo esempio disegna una linea in un form.</span><span class="sxs-lookup"><span data-stu-id="89727-103">This example draws a line on a form.</span></span> <span data-ttu-id="89727-104">In genere, quando si disegna in un form, la gestione del modulo <xref:System.Windows.Forms.Control.Paint> eventi ed eseguire il disegno utilizzando i <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> proprietà del <xref:System.Windows.Forms.PaintEventArgs>, come illustrato in questo esempio</span><span class="sxs-lookup"><span data-stu-id="89727-104">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="89727-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="89727-105">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="89727-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="89727-106">Compiling the Code</span></span>  
 <span data-ttu-id="89727-107">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="89727-107">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="89727-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="89727-108">Robust Programming</span></span>  
 <span data-ttu-id="89727-109">È sempre necessario chiamare <xref:System.IDisposable.Dispose%2A> tutti gli oggetti che utilizzano le risorse di sistema, ad esempio <xref:System.Drawing.Pen> oggetti.</span><span class="sxs-lookup"><span data-stu-id="89727-109">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89727-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89727-110">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="89727-111">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="89727-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="89727-112">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="89727-112">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="89727-113">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="89727-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)

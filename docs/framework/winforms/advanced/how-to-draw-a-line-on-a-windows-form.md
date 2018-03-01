---
title: 'Procedura: disegnare una linea in un Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 78ad7d455f1de4b7077288d9575ea4907c3f218d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="11b1c-102">Procedura: disegnare una linea in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="11b1c-102">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="11b1c-103">In questo esempio disegna una linea in un form.</span><span class="sxs-lookup"><span data-stu-id="11b1c-103">This example draws a line on a form.</span></span> <span data-ttu-id="11b1c-104">In genere, quando si disegna in un form, gestire il modulo <xref:System.Windows.Forms.Control.Paint> eventi ed eseguire il disegno utilizzando il <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> proprietà del <xref:System.Windows.Forms.PaintEventArgs>, come illustrato in questo esempio</span><span class="sxs-lookup"><span data-stu-id="11b1c-104">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="11b1c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="11b1c-105">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="11b1c-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="11b1c-106">Compiling the Code</span></span>  
 <span data-ttu-id="11b1c-107">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="11b1c-107">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="11b1c-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="11b1c-108">Robust Programming</span></span>  
 <span data-ttu-id="11b1c-109">È necessario chiamare sempre <xref:System.IDisposable.Dispose%2A> in tutti gli oggetti che utilizzano le risorse di sistema, ad esempio <xref:System.Drawing.Pen> oggetti.</span><span class="sxs-lookup"><span data-stu-id="11b1c-109">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11b1c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11b1c-110">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawLine%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="11b1c-111">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="11b1c-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="11b1c-112">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="11b1c-112">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="11b1c-113">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="11b1c-113">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)

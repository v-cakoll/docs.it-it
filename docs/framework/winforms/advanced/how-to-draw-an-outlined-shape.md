---
title: 'Procedura: creare una forma con contorno'
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
- cpp
f1_keywords: Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eace68b646b3cdf75546527204bc41584ba64f85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-an-outlined-shape"></a>Procedura: creare una forma con contorno
In questo esempio disegna ellissi e rettangoli in un form.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Non è possibile chiamare questo metodo <xref:System.Windows.Forms.Form.Load> gestore dell'evento. Se il form viene ridimensionato o nascosto da un altro formato, il contenuto disegnato non verrà ridisegnato. Per ridisegnare automaticamente il contenuto è necessario eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 È necessario chiamare sempre <xref:System.IDisposable.Dispose%2A> in tutti gli oggetti che utilizzano le risorse di sistema, ad esempio <xref:System.Drawing.Pen> e <xref:System.Drawing.Graphics> oggetti.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Graphics.DrawRectangle%2A>  
 [Introduzione alla programmazione grafica](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)

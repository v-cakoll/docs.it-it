---
title: 'Procedura: creare un Windows Form con una forma'
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
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b0641adfcd7fa8e1d3367ea55d00830dd5a60706
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-shaped-windows-form"></a>Procedura: creare un Windows Form con una forma
In questo esempio viene creato un form con una forma ellittica che viene ridimensionato con il modulo.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli spazi dei nomi <xref:System.Windows.Forms> e <xref:System.Drawing>.  
  
 Questo esempio sostituisce il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo per modificare la forma del form. Per utilizzare questo codice, copiare la dichiarazione del metodo, nonché il codice di disegno all'interno del metodo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Region>  
 <xref:System.Drawing>  
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>  
 <xref:System.Windows.Forms.Control.Region%2A>  
 [Introduzione alla programmazione grafica](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)

---
title: 'Procedura: creare un oggetto Solid Brush'
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
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 594d18d9607928b9a54a3b2639988775572f205c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-solid-brush"></a>Procedura: creare un oggetto Solid Brush
Questo esempio viene creato un <xref:System.Drawing.SolidBrush> oggetto che può essere utilizzato da un <xref:System.Drawing.Graphics> oggetto per il riempimento di forme.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Dopo avere la possibilità di utilizzarli, è necessario chiamare <xref:System.IDisposable.Dispose%2A> su oggetti che utilizzano le risorse di sistema, ad esempio gli oggetti di pennello.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.SolidBrush>  
 <xref:System.Drawing.Brush>  
 [Introduzione alla programmazione grafica](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Pennelli e forme con riempimento in GDI+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)  
 [Uso di un oggetto Brush per il riempimento di forme](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)

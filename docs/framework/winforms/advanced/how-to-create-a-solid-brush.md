---
title: 'Procedura: Creare un oggetto Solid Brush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: d7fb7c11a69cae69210dd2eece3336bc40c505c7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711980"
---
# <a name="how-to-create-a-solid-brush"></a>Procedura: Creare un oggetto Solid Brush
Questo esempio viene creato un <xref:System.Drawing.SolidBrush> oggetto che può essere usato da un <xref:System.Drawing.Graphics> oggetto per il riempimento di forme.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Dopo aver usarle, è necessario chiamare <xref:System.IDisposable.Dispose%2A> su oggetti che utilizzano le risorse di sistema, ad esempio gli oggetti pennello.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [Introduzione alla programmazione grafica](getting-started-with-graphics-programming.md)
- [Pennelli e forme con riempimento in GDI+](brushes-and-filled-shapes-in-gdi.md)
- [Uso di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)

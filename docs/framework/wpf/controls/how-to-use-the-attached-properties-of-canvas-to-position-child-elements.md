---
title: "Procedura: Usare le proprietà associate di un'area di disegno per posizionare gli elementi figlio"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 347c8502bd4c5fafcde7a142327f85bfb75b9954
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699071"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>Procedura: Usare le proprietà associate di un'area di disegno per posizionare gli elementi figlio
In questo esempio viene illustrato come utilizzare le proprietà associate di <xref:System.Windows.Controls.Canvas> per posizionare elementi figlio.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente aggiunge quattro <xref:System.Windows.Controls.Button> elementi come elementi figlio di un elemento padre <xref:System.Windows.Controls.Canvas>. Ogni elemento è rappresentato da un <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, e <xref:System.Windows.Controls.Canvas.Top%2A>.
Ciascuna <xref:System.Windows.Controls.Button> viene posizionata in relazione padre <xref:System.Windows.Controls.Canvas> e in base al valore di proprietà assegnato.  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Procedure relative alle proprietà](canvas-how-to-topics.md)
- [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md)

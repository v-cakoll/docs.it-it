---
title: "Procedura: Eseguire l'associazione dati a un InkCanvas"
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 5d3fc0ed7b6176d7bc68bf20af42c311b5563908
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776467"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a>Procedura: Eseguire l'associazione dati a un InkCanvas
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare le <xref:System.Windows.Controls.InkCanvas.Strokes%2A> proprietà di un <xref:System.Windows.Controls.InkCanvas> a un altro <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xaml[InkCanvasBindingSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 Nell'esempio seguente viene illustrato come associare il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà a un'origine dati.  
  
 [!code-xaml[InkCanvasBindingSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 L'esempio seguente dichiara due <xref:System.Windows.Controls.InkCanvas> degli oggetti in XAML e stabilisce l'associazione dati tra queste e altre origini dati.  Il primo <xref:System.Windows.Controls.InkCanvas>, denominato `ic`, è associato a due origini dati.  Il <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> e <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> delle proprietà nel `ic` sono associati a <xref:System.Windows.Controls.ListBox> oggetti, che a sua volta sono associati a matrici definite nel XAML.  Il <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, e <xref:System.Windows.Controls.InkCanvas.Strokes%2A> delle proprietà del secondo <xref:System.Windows.Controls.InkCanvas> sono associati al primo <xref:System.Windows.Controls.InkCanvas>, `ic`.  
  
 [!code-xaml[InkCanvasBindingSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]

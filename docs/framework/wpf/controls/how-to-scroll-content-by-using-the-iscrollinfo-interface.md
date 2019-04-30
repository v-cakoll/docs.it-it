---
title: "Procedura: Scorrere il contenuto usando l'interfaccia IScrollInfo"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 6ebd8268e1358b45709885c07e6b096d5f806ebb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051247"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a>Procedura: Scorrere il contenuto usando l'interfaccia IScrollInfo
Questo esempio viene illustrato come scorrere il contenuto usando la <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaccia.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrate le funzionalità del <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaccia. Nell'esempio viene creata una <xref:System.Windows.Controls.StackPanel> nell'elemento [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] annidato all'interno di un elemento padre <xref:System.Windows.Controls.ScrollViewer>. Gli elementi figlio del <xref:System.Windows.Controls.StackPanel> è possibile scorrere in modo logico usando i metodi definiti dal <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaccia ed eseguire il cast all'istanza di <xref:System.Windows.Controls.StackPanel> (`sp1`) nel codice.  
  
 [!code-xaml[IScrollInfoMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Ciascuna <xref:System.Windows.Controls.Button> nella [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file attiva un metodo personalizzato associato che controlla il comportamento dello scorrimento in <xref:System.Windows.Controls.StackPanel>. Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> e <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> metodi; inoltre genericamente viene illustrato come utilizzare tutti i metodi di posizionamento che il <xref:System.Windows.Controls.Primitives.IScrollInfo> classe definisce.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [Panoramica sull'elemento ScrollViewer](scrollviewer-overview.md)
- [Procedure relative alle proprietà](scrollviewer-how-to-topics.md)
- [Cenni preliminari sugli elementi Panel](panels-overview.md)

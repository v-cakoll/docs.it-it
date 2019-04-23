---
title: 'Procedura: Creare e usare un oggetto GridLengthConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 498d2b9c531f391f4cbeb1478469a99d381deec7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770770"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>Procedura: Creare e usare un oggetto GridLengthConverter
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare e usare un'istanza di <xref:System.Windows.GridLengthConverter>. L'esempio definisce un metodo personalizzato denominato `changeCol`, che passa il <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.GridLengthConverter> che converte il <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Windows.GridLength>. Il valore convertito viene quindi passato nuovamente come valore dei <xref:System.Windows.Controls.ColumnDefinition.Width%2A> proprietà del <xref:System.Windows.Controls.ColumnDefinition> elemento.  
  
 L'esempio definisce anche un secondo metodo personalizzato, denominato `changeColVal`. Converte questo metodo personalizzato le <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> di un <xref:System.Windows.Controls.Slider> a un <xref:System.String> e quindi passa tale valore al <xref:System.Windows.Controls.ColumnDefinition> come il <xref:System.Windows.Controls.ColumnDefinition.Width%2A> dell'elemento.  
  
 Si noti che un oggetto separato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file definisce il contenuto di un <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>

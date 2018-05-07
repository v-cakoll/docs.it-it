---
title: 'Procedura: creare una griglia complessa'
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: 49bf9781d56b93fd4529f3c9b62deb171e69155f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-complex-grid"></a>Procedura: creare una griglia complessa
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Controls.Grid> per creare layout simile a un calendario mensile.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente definisce otto righe e otto colonne utilizzando la <xref:System.Windows.Controls.RowDefinition> e <xref:System.Windows.Controls.ColumnDefinition> classi. Usa il <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> associate, insieme a <xref:System.Windows.Shapes.Rectangle> elementi che riempiono gli sfondi delle varie colonne e righe. Questa progettazione è possibile perché può esistere più di un elemento in ogni cella in un <xref:System.Windows.Controls.Grid>, una differenza principio <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Documents.Table>.  
  
 L'esempio Usa sfumature verticali per <xref:System.Windows.Shapes.Shape.Fill%2A> le colonne e righe per migliorare la presentazione visiva e migliorare la leggibilità del calendario. Stile <xref:System.Windows.Controls.TextBlock> elementi rappresentano le date e i giorni della settimana. <xref:System.Windows.Controls.TextBlock> gli elementi vengono posizionati all'interno delle celle utilizzando il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà e le proprietà di allineamento che sono definite nello stile per l'applicazione.  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [Cenni sul disegno con colori a tinta unita e sfumature](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Cenni preliminari sull'elemento Table](../../../../docs/framework/wpf/advanced/table-overview.md)

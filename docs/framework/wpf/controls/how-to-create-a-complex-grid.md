---
title: Come creare una griglia complessa
description: Un esempio su come usare un controllo griglia per creare un layout simile a un calendario mensile.
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: e2356113457e8c9a6737132e9779e49c05a23d77
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149783"
---
# <a name="how-to-create-a-complex-grid"></a>Come creare una griglia complessa

In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Controls.Grid> controllo per creare un layout simile a un calendario mensile.

## <a name="example"></a>Esempio

L'esempio seguente definisce le otto righe e otto colonne usando il <xref:System.Windows.Controls.RowDefinition> e <xref:System.Windows.Controls.ColumnDefinition> classi. Usa il <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> associate, insieme a <xref:System.Windows.Shapes.Rectangle> elementi, che è riempiono gli sfondi delle varie colonne e righe. Questa progettazione è possibile perché può esistere più di un elemento in ogni cella in una <xref:System.Windows.Controls.Grid>, una differenza essenziale tra <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Documents.Table>.

L'esempio Usa le sfumature verticale a <xref:System.Windows.Shapes.Shape.Fill%2A> le colonne e righe per migliorare la presentazione visiva e migliorare la leggibilità del calendario. Nello stile <xref:System.Windows.Controls.TextBlock> elementi rappresentano le date e giorni della settimana. <xref:System.Windows.Controls.TextBlock> gli elementi vengono posizionati all'interno delle celle mediante i <xref:System.Windows.FrameworkElement.Margin%2A> proprietà e le proprietà di allineamento definiti al suo interno lo stile per l'applicazione.

[!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

L'immagine seguente mostra il controllo risultante, un calendario personalizzabile:

![Screenshot del controllo risulta](./media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [Cenni sul disegno con colori a tinta unita e sfumature](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Cenni preliminari sull'elemento Table](../advanced/table-overview.md)
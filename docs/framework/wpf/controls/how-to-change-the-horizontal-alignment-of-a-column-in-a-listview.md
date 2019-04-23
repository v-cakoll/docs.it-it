---
title: "Procedura: Modificare l'allineamento orizzontale di una colonna in ListView"
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 528a711c1cf7992bb32c0aa4d6e81d71744c9f80
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102661"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Procedura: Modificare l'allineamento orizzontale di una colonna in ListView
Per impostazione predefinita, il contenuto di ogni colonna in un <xref:System.Windows.Controls.ListViewItem> è allineato a sinistra. È possibile modificare l'allineamento di ogni colonna, fornendo una <xref:System.Windows.DataTemplate> e impostando il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà dell'elemento all'interno di <xref:System.Windows.DataTemplate>. Questo argomento viene illustrato come un <xref:System.Windows.Controls.ListView> Allinea il contenuto per impostazione predefinita e come modificare l'allineamento di una colonna in un <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, i dati di `Title` e `ISBN` colonne è allineato a sinistra.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Per modificare l'allineamento del `ISBN` colonna, è necessario specificare che il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> proprietà di ciascuno <xref:System.Windows.Controls.ListViewItem> viene <xref:System.Windows.HorizontalAlignment.Stretch>, in modo che gli elementi in ogni <xref:System.Windows.Controls.ListViewItem> può estendersi su o essere posizionata lungo l'intera larghezza di ogni colonna. Poiché il <xref:System.Windows.Controls.ListView> è associato a un'origine dati, è necessario creare uno stile che imposta il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. Successivamente, è necessario usare una <xref:System.Windows.DataTemplate> per visualizzare il contenuto invece di usare il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà. Per visualizzare il `ISBN` di ogni modello, il <xref:System.Windows.DataTemplate> può contenere solo un <xref:System.Windows.Controls.TextBlock> con relativo <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> impostata su <xref:System.Windows.HorizontalAlignment.Right>.  
  
 L'esempio seguente definisce lo stile e <xref:System.Windows.DataTemplate> necessario per rendere il `ISBN` colonna allineata a destra e le modifiche le <xref:System.Windows.Controls.GridViewColumn> per fare riferimento al <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Panoramica sui modelli di dati](../data/data-templating-overview.md)
- [Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul controllo ListView](listview-overview.md)

---
title: "Procedura: modificare l'allineamento orizzontale di una colonna in ListView"
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 5447f1a73b008b2ed4f345eba00f4d631e11e257
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458599"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Procedura: modificare l'allineamento orizzontale di una colonna in ListView
Per impostazione predefinita, il contenuto di ogni colonna in un <xref:System.Windows.Controls.ListViewItem> è allineato a sinistra. È possibile modificare l'allineamento di ogni colonna fornendo un <xref:System.Windows.DataTemplate> e impostando la proprietà <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> sull'elemento all'interno della <xref:System.Windows.DataTemplate>. In questo argomento viene illustrato il modo in cui un <xref:System.Windows.Controls.ListView> allinea il contenuto per impostazione predefinita e come modificare l'allineamento di una colonna in una <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente i dati delle colonne `Title` e `ISBN` sono allineati a sinistra.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Per modificare l'allineamento della colonna `ISBN`, è necessario specificare che la proprietà <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> di ogni <xref:System.Windows.Controls.ListViewItem> venga <xref:System.Windows.HorizontalAlignment.Stretch>, in modo che gli elementi di ogni <xref:System.Windows.Controls.ListViewItem> possano estendersi o essere posizionati lungo l'intera larghezza di ogni colonna. Poiché il <xref:System.Windows.Controls.ListView> è associato a un'origine dati, è necessario creare uno stile che imposta l'<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. Successivamente, è necessario usare un <xref:System.Windows.DataTemplate> per visualizzare il contenuto invece di usare la proprietà <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>. Per visualizzare la `ISBN` di ogni modello, l'<xref:System.Windows.DataTemplate> può contenere solo un <xref:System.Windows.Controls.TextBlock> la cui proprietà <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> è impostata su <xref:System.Windows.HorizontalAlignment.Right>.  
  
 Nell'esempio seguente vengono definiti lo stile e la <xref:System.Windows.DataTemplate> necessari per rendere allineata a destra la colonna `ISBN` e viene modificato il <xref:System.Windows.Controls.GridViewColumn> in modo da fare riferimento al <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica sui modelli di dati](../data/data-templating-overview.md)
- [Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul controllo ListView](listview-overview.md)

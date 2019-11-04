---
title: 'Procedura: applicare uno stile a una riga in un ListView che implementa una GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 150988aab368e3ffef0107d29bea5ebc53163946
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459316"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Procedura: applicare uno stile a una riga in un ListView che implementa una GridView
Questo esempio illustra come applicare uno stile a una riga in un controllo <xref:System.Windows.Controls.ListView> che implementa una modalità di <xref:System.Windows.Controls.ListView.View%2A> <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Esempio  
 È possibile applicare uno stile a una riga in un controllo <xref:System.Windows.Controls.ListView> impostando una <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> sul controllo <xref:System.Windows.Controls.ListView>. Impostare lo stile per gli elementi rappresentati come oggetti <xref:System.Windows.Controls.ListViewItem>. Il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> fa riferimento agli oggetti <xref:System.Windows.Controls.ControlTemplate> utilizzati per visualizzare il contenuto della riga.  
  
 L'esempio completo, da cui sono estratti gli esempi seguenti, visualizza una raccolta di informazioni relative a brani archiviati in un database [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Ogni brano nel database include un campo di classificazione e il valore di questo campo specifica la modalità di visualizzazione di una riga di informazioni relative al brano.  
  
 Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per gli oggetti <xref:System.Windows.Controls.ListViewItem> che rappresentano i brani della raccolta Song. Il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> fa riferimento a <xref:System.Windows.Controls.ControlTemplate> oggetti che specificano come visualizzare una riga di informazioni sul brano.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 Nell'esempio seguente viene illustrato un <xref:System.Windows.Controls.ControlTemplate> che aggiunge la stringa di testo `"Strongly Recommended"` alla riga. Si fa riferimento a questo modello nel <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> e viene visualizzato quando la classificazione del brano ha un valore pari a 5 (cinque). Il <xref:System.Windows.Controls.ControlTemplate> include un oggetto <xref:System.Windows.Controls.GridViewRowPresenter> che imposta il contenuto della riga nelle colonne, come definito dalla modalità di visualizzazione <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 Nell'esempio seguente viene definito <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure relative alle proprietà](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)

---
title: 'Procedura: Applicare uno stile a una riga in un ListView che implementa un oggetto GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 9af8d10c7db2d3bbe8b9443402cbb1cfeaa7edb3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091460"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Procedura: Applicare uno stile a una riga in un ListView che implementa un oggetto GridView
Questo esempio viene illustrato come applicare uno stile a una riga in una <xref:System.Windows.Controls.ListView> controllo che implementa un <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> modalità.  
  
## <a name="example"></a>Esempio  
 È possibile applicare uno stile a una riga in una <xref:System.Windows.Controls.ListView> controllo impostando un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> nel <xref:System.Windows.Controls.ListView> controllo. Impostare lo stile per i relativi elementi rappresentati come <xref:System.Windows.Controls.ListViewItem> oggetti. Il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> riferimenti di <xref:System.Windows.Controls.ControlTemplate> gli oggetti che consentono di visualizzare il contenuto della riga.  
  
 L'esempio completo, da cui sono estratti gli esempi seguenti, visualizza una raccolta di informazioni relative a brani archiviati in un database [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Ogni brano nel database include un campo di classificazione e il valore di questo campo specifica la modalità di visualizzazione di una riga di informazioni relative al brano.  
  
 Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per il <xref:System.Windows.Controls.ListViewItem> gli oggetti che rappresentano i brani nella raccolta. Il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> riferimenti <xref:System.Windows.Controls.ControlTemplate> gli oggetti che specificano come visualizzare una riga di informazioni relative al brano.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 L'esempio seguente mostra una <xref:System.Windows.Controls.ControlTemplate> che aggiunge la stringa di testo `"Strongly Recommended"` alla riga. Questo modello fa riferimento il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> e viene visualizzato quando la valutazione del brano ha un valore pari a 5 (cinque). Il <xref:System.Windows.Controls.ControlTemplate> include un <xref:System.Windows.Controls.GridViewRowPresenter> che applica il contenuto della riga di colonne come definito dall'oggetto di <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 L'esempio seguente definisce <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure relative](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Applicazione di stili e modelli](styling-and-templating.md)

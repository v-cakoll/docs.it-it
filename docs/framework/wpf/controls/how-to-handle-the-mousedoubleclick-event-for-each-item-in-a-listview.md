---
title: "Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646103"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView
Per gestire un evento per <xref:System.Windows.Controls.ListView>un elemento in un oggetto <xref:System.Windows.Controls.ListViewItem>, è necessario aggiungere un gestore eventi a ciascuno di essi . Quando <xref:System.Windows.Controls.ListView> un oggetto è associato a un'origine <xref:System.Windows.Controls.ListViewItem>dati, non si crea in modo <xref:System.Windows.EventSetter> esplicito un <xref:System.Windows.Controls.ListViewItem>oggetto , ma è possibile gestire l'evento per ogni elemento aggiungendo un a uno stile di un oggetto .  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di <xref:System.Windows.Controls.ListView> seguito <xref:System.Windows.Style> viene creata una associazione a dati e viene creato un oggetto per aggiungere un gestore eventi a each <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Nell'esempio seguente <xref:System.Windows.Controls.Control.MouseDoubleClick> viene gestita l'evento.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Sebbene sia più comune <xref:System.Windows.Controls.ListView> associare un oggetto a un'origine dati, <xref:System.Windows.Controls.ListViewItem> è possibile utilizzare uno <xref:System.Windows.Controls.ListView> stile per aggiungere un <xref:System.Windows.Controls.ListViewItem>gestore eventi a ciascuno in un'origine dati non associata, indipendentemente dal fatto che venga creato in modo esplicito un oggetto .  Per ulteriori informazioni sui controlli <xref:System.Windows.Controls.ListViewItem> creati <xref:System.Windows.Controls.ItemsControl>in modo esplicito e implicito, vedere .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.XmlElement>
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Eseguire l'associazione a dati XML utilizzando un XMLDataProvider e query XPathBind to XML Data Using an XMLDataProvider and XPath Queries](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul controllo ListView](listview-overview.md)

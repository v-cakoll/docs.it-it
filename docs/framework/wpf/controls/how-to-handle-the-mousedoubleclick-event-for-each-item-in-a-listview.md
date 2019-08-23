---
title: "Procedura: Gestire l'evento MouseDoubleClick per ciascun elemento di ListView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7e51c810a2e1e4bf4157aa1311255c5547021b60
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962069"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Procedura: Gestire l'evento MouseDoubleClick per ciascun elemento di ListView
Per gestire un evento per un elemento in un <xref:System.Windows.Controls.ListView>oggetto, è necessario aggiungere un gestore eventi a ognuno <xref:System.Windows.Controls.ListViewItem>di essi. Quando un <xref:System.Windows.Controls.ListView> oggetto è associato a un'origine dati, non si crea in modo <xref:System.Windows.Controls.ListViewItem>esplicito un oggetto, ma è possibile gestire l'evento per ogni <xref:System.Windows.EventSetter> elemento aggiungendo un oggetto a <xref:System.Windows.Controls.ListViewItem>uno stile di un oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un oggetto con <xref:System.Windows.Controls.ListView> associazione a dati <xref:System.Windows.Style> e viene creato un oggetto per aggiungere <xref:System.Windows.Controls.ListViewItem>un gestore eventi a ognuno di essi.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Nell'esempio seguente viene gestito <xref:System.Windows.Controls.Control.MouseDoubleClick> l'evento.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Sebbene sia più comune <xref:System.Windows.Controls.ListView> associare un oggetto a un'origine dati, è possibile utilizzare uno stile per aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem> oggetto in un non associato <xref:System.Windows.Controls.ListView> a dati indipendentemente dal fatto che si crei in modo esplicito un oggetto <xref:System.Windows.Controls.ListViewItem>.  Per ulteriori informazioni sui controlli creati <xref:System.Windows.Controls.ListViewItem> in modo esplicito e implicito, vedere. <xref:System.Windows.Controls.ItemsControl>  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.XmlElement>
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Applicazione di stili e modelli](styling-and-templating.md)
- [Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul controllo ListView](listview-overview.md)

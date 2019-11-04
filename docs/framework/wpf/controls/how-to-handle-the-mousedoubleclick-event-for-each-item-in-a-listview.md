---
title: "Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 25308ee87fb387787e20c8a8887ae8e4e60742b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460225"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView
Per gestire un evento per un elemento in una <xref:System.Windows.Controls.ListView>, è necessario aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem>. Quando un <xref:System.Windows.Controls.ListView> viene associato a un'origine dati, non si crea in modo esplicito una <xref:System.Windows.Controls.ListViewItem>, ma è possibile gestire l'evento per ogni elemento aggiungendo un <xref:System.Windows.EventSetter> a uno stile di una <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una <xref:System.Windows.Controls.ListView> associata a dati e viene creato un <xref:System.Windows.Style> per aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Nell'esempio seguente viene gestito l'evento <xref:System.Windows.Controls.Control.MouseDoubleClick>.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Sebbene sia più comune associare un <xref:System.Windows.Controls.ListView> a un'origine dati, è possibile utilizzare uno stile per aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem> in un <xref:System.Windows.Controls.ListView> non associato ai dati indipendentemente dal fatto che si crei in modo esplicito un <xref:System.Windows.Controls.ListViewItem>.  Per ulteriori informazioni sui controlli <xref:System.Windows.Controls.ListViewItem> creati in modo esplicito e implicito, vedere <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.XmlElement>
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul controllo ListView](listview-overview.md)

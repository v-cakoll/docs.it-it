---
title: 'Procedura: utilizzare il modello Master-Details con dati gerarchici'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e4183ddc3868a1568662853b46e05348df129092
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733476"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Procedura: utilizzare il modello Master-Details con dati gerarchici
Questo esempio illustra come implementare lo scenario Master-Details.  
  
## <a name="example"></a>Esempio  
 In questo esempio `LeagueList` è una raccolta di `Leagues`. Ogni `League` dispone di un `Name` e una raccolta di `Divisions`e ogni `Division` ha un nome e una raccolta di `Teams`. Ogni `Team` ha un nome del team.  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Lo screenshot seguente mostra l'esempio. Il `Divisions` <xref:System.Windows.Controls.ListBox> rileva automaticamente le selezioni nel `Leagues` <xref:System.Windows.Controls.ListBox> e Visualizza i dati corrispondenti. Il `Teams` <xref:System.Windows.Controls.ListBox> tiene traccia delle selezioni negli altri due controlli di <xref:System.Windows.Controls.ListBox>.  
  
 ![Screenshot che mostra un esempio&#45;di scenario di dettaglio master.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 I due aspetti da notare in questo esempio sono i seguenti:  
  
1. I tre controlli <xref:System.Windows.Controls.ListBox> si associano alla stessa origine. È possibile impostare la proprietà <xref:System.Windows.Data.Binding.Path%2A> dell'associazione per specificare il livello di dati che si desidera visualizzare nel <xref:System.Windows.Controls.ListBox>.  
  
2. È necessario impostare la proprietà <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> su `true` sui controlli <xref:System.Windows.Controls.ListBox> di cui si sta verificando la selezione. L'impostazione di questa proprietà garantisce che l'elemento selezionato sia sempre impostato come <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. In alternativa, se il <xref:System.Windows.Controls.ListBox> ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource>, sincronizza automaticamente la selezione e la valuta.  
  
 La tecnica è leggermente diversa quando si utilizzano dati XML. Per un esempio, vedere [usare il modello Master-Details con dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.HierarchicalDataTemplate>
- [Eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica sui modelli di dati](data-templating-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)

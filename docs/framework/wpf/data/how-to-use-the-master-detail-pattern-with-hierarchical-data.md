---
title: 'Procedura: utilizzare il modello Master-Details con dati gerarchici'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 46733b462861bdac3381cdacb8f2fbe0536d12eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556796"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Procedura: utilizzare il modello Master-Details con dati gerarchici
In questo esempio viene illustrato come implementare uno scenario master-details.  
  
## <a name="example"></a>Esempio  
 In questo esempio, `LeagueList` è una raccolta di `Leagues`. Ogni `League` ha un `Name` e una raccolta di `Divisions`e ogni `Division` ha un nome e una raccolta di `Teams`. Ogni `Team` ha un nome.  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Lo screenshot seguente mostra l'esempio. Il `Divisions` <xref:System.Windows.Controls.ListBox> automaticamente tiene traccia delle selezioni nel `Leagues` <xref:System.Windows.Controls.ListBox> e visualizzare i dati corrispondenti. Il `Teams` <xref:System.Windows.Controls.ListBox> tiene traccia delle selezioni negli altri due <xref:System.Windows.Controls.ListBox> controlli.  
  
 ![Master&#45;esempio di dettaglio](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 I due elementi per rilevare in questo esempio sono:  
  
1.  I tre <xref:System.Windows.Controls.ListBox> associare i controlli alla stessa origine. Impostare il <xref:System.Windows.Data.Binding.Path%2A> proprietà dell'associazione per specificare il livello di dati di cui si desidera il <xref:System.Windows.Controls.ListBox> da visualizzare.  
  
2.  È necessario impostare il <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà `true` sul <xref:System.Windows.Controls.ListBox> controlli dei quali la selezione si tiene traccia. L'impostazione di questa proprietà garantisce che l'elemento selezionato è sempre impostato come il <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. In alternativa, se il <xref:System.Windows.Controls.ListBox> Ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource>, la selezione e valuta sincronizzate automaticamente.  
  
 La tecnica è leggermente diversa quando si utilizza [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati. Per un esempio, vedere [utilizzare il modello Master-Details con dati XML gerarchici](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [Eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Panoramica sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

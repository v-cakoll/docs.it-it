---
title: 'Procedura: Usare il modello Master-Details con dati XML gerarchici'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: ba6c932f519ffa5c3c70ecb21eb9b5d08c40fb28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931755"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>Procedura: Usare il modello Master-Details con dati XML gerarchici
In questo esempio viene illustrato come implementare lo scenario master-Details con [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dei dati.  
  
## <a name="example"></a>Esempio  
 Questo esempio è il [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] versione di dati di esempio illustrato in [usare il modello Master-Details con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md). In questo esempio, i dati sono nel file `League.xml`. Si noti come la terza <xref:System.Windows.Controls.ListBox> controllo tiene traccia delle modifiche di selezione nella seconda <xref:System.Windows.Controls.ListBox> tramite l'associazione alla relativo <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> proprietà.  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.HierarchicalDataTemplate>
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)

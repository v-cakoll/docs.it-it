---
title: 'Procedura: utilizzare i modelli per applicare uno stile a un ListView che utilizza una GridView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9abc19ca14cf512deff898f5f20d23870b8b7847
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a>Procedura: utilizzare i modelli per applicare uno stile a un ListView che utilizza una GridView
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.DataTemplate> e <xref:System.Windows.Style> gli oggetti per specificare l'aspetto di un <xref:System.Windows.Controls.ListView> controllo che utilizza un <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti <xref:System.Windows.Style> e <xref:System.Windows.DataTemplate> gli oggetti che consentono di personalizzare l'aspetto di un'intestazione di colonna per un <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 Nell'esempio seguente viene illustrato come utilizzare questi <xref:System.Windows.Style> e <xref:System.Windows.DataTemplate> oggetti su cui impostare il <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> e <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> le proprietà di un <xref:System.Windows.Controls.GridViewColumn>. Il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà definisce il contenuto delle celle della colonna.  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 Il <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> e <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> sono solo due delle numerose proprietà che è possibile utilizzare per personalizzare l'aspetto dell'intestazione di colonna per un <xref:System.Windows.Controls.GridView> controllo. Per altre informazioni, vedere [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.DataTemplate> che consente di personalizzare l'aspetto delle celle in un <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 Nell'esempio seguente viene illustrato come utilizzare questo <xref:System.Windows.DataTemplate> per definire il contenuto di un <xref:System.Windows.Controls.GridViewColumn> cella. Questo modello viene utilizzato anziché il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà visualizzate nella precedente <xref:System.Windows.Controls.GridViewColumn> esempio.  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)

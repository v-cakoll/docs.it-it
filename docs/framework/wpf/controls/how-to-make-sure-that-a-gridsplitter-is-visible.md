---
title: 'Procedura: assicurarsi che GridSplitter sia visibile'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 926df118bfd8e7ab3d1f0c953d0b6debafd59073
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554820"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>Procedura: assicurarsi che GridSplitter sia visibile
In questo esempio viene illustrato come assicurarsi che un <xref:System.Windows.Controls.GridSplitter> controllo non è nascosto da altri controlli in un <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.Panel.Children%2A> di un <xref:System.Windows.Controls.Grid> controllo vengono visualizzati in ordine di definizione nel markup o codice. <xref:System.Windows.Controls.GridSplitter> controlli possono essere nascosti da altri controlli se non vengono definiti come ultimi elementi nel <xref:System.Windows.Controls.Panel.Children%2A> insieme o se si assegna ad altri controlli di un livello più elevato <xref:System.Windows.Controls.Panel.ZIndexProperty>.  
  
 Per evitare nascosto <xref:System.Windows.Controls.GridSplitter> controlli, eseguire una delle operazioni seguenti.  
  
-   Assicurarsi che <xref:System.Windows.Controls.GridSplitter> i controlli sono l'ultima <xref:System.Windows.Controls.Panel.Children%2A> aggiunti il <xref:System.Windows.Controls.Grid>. Nell'esempio seguente il <xref:System.Windows.Controls.GridSplitter> come l'ultimo elemento il <xref:System.Windows.Controls.Panel.Children%2A> insieme del <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   Impostare il <xref:System.Windows.Controls.Panel.ZIndexProperty> sul <xref:System.Windows.Controls.GridSplitter> è superiore a un controllo che sarebbe altrimenti nasconderlo. Nell'esempio seguente consente di <xref:System.Windows.Controls.GridSplitter> controllano un livello più elevato <xref:System.Windows.Controls.Panel.ZIndexProperty> rispetto di <xref:System.Windows.Controls.Button> controllo.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   Impostare i margini del controllo che in caso contrario nasconderà la <xref:System.Windows.Controls.GridSplitter> in modo che il <xref:System.Windows.Controls.GridSplitter> viene esposta. Nell'esempio seguente imposta i margini su un controllo che in caso contrario, verrebbe sovrapposto e nascondere il <xref:System.Windows.Controls.GridSplitter>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.GridSplitter>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)

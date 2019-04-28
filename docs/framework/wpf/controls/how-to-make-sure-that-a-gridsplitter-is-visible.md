---
title: 'Procedura: Assicurarsi che GridSplitter sia visibile'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: b7543d14ba39d854b5a2c3f4d0d19b9a457ea89b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770851"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>Procedura: Assicurarsi che GridSplitter sia visibile
In questo esempio viene illustrato come assicurarsi che un <xref:System.Windows.Controls.GridSplitter> controllo non è nascosto da altri controlli in un <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.Panel.Children%2A> di un <xref:System.Windows.Controls.Grid> controllo vengono visualizzati in ordine che sono definiti nel codice o markup. <xref:System.Windows.Controls.GridSplitter> i controlli possono essere nascosti da altri controlli se si non vengono definiti come gli ultimi elementi nel <xref:System.Windows.Controls.Panel.Children%2A> raccolta o se si assegna ad altri controlli di un livello più elevato <xref:System.Windows.Controls.Panel.ZIndexProperty>.  
  
 Per evitare nascosto <xref:System.Windows.Controls.GridSplitter> controlli, effettuare una delle operazioni seguenti.  
  
- Verificare che l'opzione <xref:System.Windows.Controls.GridSplitter> controlli sono l'ultima <xref:System.Windows.Controls.Panel.Children%2A> aggiunto al <xref:System.Windows.Controls.Grid>. L'esempio seguente illustra il <xref:System.Windows.Controls.GridSplitter> come l'ultimo elemento nel <xref:System.Windows.Controls.Panel.Children%2A> insieme del <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
- Impostare il <xref:System.Windows.Controls.Panel.ZIndexProperty> nella <xref:System.Windows.Controls.GridSplitter> superiori rispetto a un controllo che sarebbe altrimenti nasconderlo. L'esempio seguente restituisce il <xref:System.Windows.Controls.GridSplitter> controllano un livello più elevato <xref:System.Windows.Controls.Panel.ZIndexProperty> rispetto al <xref:System.Windows.Controls.Button> controllo.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
- Impostare i margini del controllo che in caso contrario nasconderà la <xref:System.Windows.Controls.GridSplitter> in modo che il <xref:System.Windows.Controls.GridSplitter> viene esposto. L'esempio seguente imposta i margini su un controllo che sarebbe altrimenti si sovrappongono e nascondono la <xref:System.Windows.Controls.GridSplitter>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridSplitter>
- [Procedure relative alle proprietà](gridsplitter-how-to-topics.md)

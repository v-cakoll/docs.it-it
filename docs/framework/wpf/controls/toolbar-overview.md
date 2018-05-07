---
title: Cenni preliminari sui controlli ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 0c66867ce4d86a11424d7a7a859817d603b4227e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="toolbar-overview"></a>Cenni preliminari sui controlli ToolBar
<xref:System.Windows.Controls.ToolBar> i controlli sono contenitori per un gruppo di comandi o controlli che sono in genere correlati alla funzione. Oggetto <xref:System.Windows.Controls.ToolBar> contiene in genere i pulsanti per richiamare i comandi.  
  
  
<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>Controllo ToolBar  
 Il <xref:System.Windows.Controls.ToolBar> controllo lo stesso nome di disposizione dei pulsanti o altri controlli della barra, come in una singola riga o colonna. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> i controlli forniscono un meccanismo di overflow che inserisce tutti gli elementi che non rientrano naturalmente all'interno dei limiti <xref:System.Windows.Controls.ToolBar> in un'area di riversamento speciali. Inoltre, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> i controlli vengono in genere utilizzati con correlata <xref:System.Windows.Controls.ToolBarTray> controllo, che fornisce un comportamento speciale del layout e il supporto per avviata dall'utente, il ridimensionamento e la disposizione delle barre degli strumenti.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Specifica della posizione dei controlli ToolBar in un oggetto ToolBarTray  
 Utilizzare il <xref:System.Windows.Controls.ToolBar.Band%2A> e <xref:System.Windows.Controls.ToolBar.BandIndex%2A> proprietà per posizionare il <xref:System.Windows.Controls.ToolBar> nel <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.Band%2A> indica la posizione in cui il <xref:System.Windows.Controls.ToolBar> viene posizionato all'interno del relativo padre <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> indica l'ordine in cui il <xref:System.Windows.Controls.ToolBar> viene inserito all'interno della banda. L'esempio seguente viene illustrato come utilizzarla questa proprietà per posizionare <xref:System.Windows.Controls.ToolBar> controlli all'interno di un <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xaml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>Oggetti ToolBar con elementi di overflow  
 Spesso <xref:System.Windows.Controls.ToolBar> controlli contengono più elementi adattabili nelle dimensioni della barra degli strumenti. In questo caso, il <xref:System.Windows.Controls.ToolBar> viene visualizzato un pulsante di overflow. Per visualizzare gli elementi di overflow, un utente fa clic sul pulsante di overflow e gli elementi vengono visualizzati in una finestra popup sotto il <xref:System.Windows.Controls.ToolBar>. Nell'immagine seguente viene illustrata una <xref:System.Windows.Controls.ToolBar> con elementi di overflow.  
  
 ![Barra degli strumenti con overflow](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
Oggetto Toolbar con elementi di overflow  
  
 È possibile specificare quando un elemento in una barra degli strumenti viene effettuato nel Pannello di overflow tramite l'impostazione di <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> proprietà associata <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>, o <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. L'esempio seguente specifica che gli ultimi quattro pulsanti della barra degli strumenti devono essere sempre posizionati nel pannello di overflow.  
  
 [!code-xaml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 Il <xref:System.Windows.Controls.ToolBar> utilizza un <xref:System.Windows.Controls.Primitives.ToolBarPanel> e un <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> nel relativo <xref:System.Windows.Controls.ControlTemplate>.  Il <xref:System.Windows.Controls.Primitives.ToolBarPanel> è responsabile per il layout degli elementi sulla barra degli strumenti.  Il <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> è responsabile per il layout degli elementi che non si adattano al <xref:System.Windows.Controls.ToolBar>. Per un esempio di un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.ToolBar>, vedere  
  
 [Stili e modelli di ToolBar](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
 [Applicare uno stile ai controlli di un oggetto ToolBar](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)  
 [Esempio di raccolta di controlli WPF](http://go.microsoft.com/fwlink/?LinkID=160053)

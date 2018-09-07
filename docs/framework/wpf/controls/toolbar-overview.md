---
title: Cenni preliminari sui controlli ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 816ac0d81ddcaa461a842c0f69fe5ed5b21a32d1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087998"
---
# <a name="toolbar-overview"></a>Cenni preliminari sui controlli ToolBar
<xref:System.Windows.Controls.ToolBar> i controlli sono contenitori per un gruppo di comandi o controlli che sono in genere correlati alla funzione. Oggetto <xref:System.Windows.Controls.ToolBar> contiene in genere pulsanti che richiamano comandi.  
  
  
<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>Controllo ToolBar  
 Il <xref:System.Windows.Controls.ToolBar> controllo prende il nome dalla disposizione simile a barra dei pulsanti o altri controlli in una singola riga o colonna. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> i controlli forniscono un meccanismo di overflow che inserisce tutti gli elementi che non rientrano in una dimensione limitata <xref:System.Windows.Controls.ToolBar> in un'area di overflow speciale. È inoltre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> controlli vengono in genere usati con i relativi <xref:System.Windows.Controls.ToolBarTray> controllo, che fornisce un comportamento speciale del layout, nonché il supporto per avviata dall'utente ridimensionamento e la disposizione delle barre degli strumenti.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Specifica della posizione dei controlli ToolBar in un oggetto ToolBarTray  
 Usare la <xref:System.Windows.Controls.ToolBar.Band%2A> e <xref:System.Windows.Controls.ToolBar.BandIndex%2A> delle proprietà per posizionare il <xref:System.Windows.Controls.ToolBar> nel <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.Band%2A> indica la posizione in cui il <xref:System.Windows.Controls.ToolBar> viene posizionato all'interno di padre <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> indica l'ordine in cui il <xref:System.Windows.Controls.ToolBar> viene posizionato all'interno della banda. L'esempio seguente viene illustrato come utilizzarla questa proprietà per posizionare <xref:System.Windows.Controls.ToolBar> controlli all'interno di un <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xaml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>Oggetti ToolBar con elementi di overflow  
 Spesso <xref:System.Windows.Controls.ToolBar> controlli contengono più elementi quelli può adattarsi alla dimensione della barra degli strumenti. In questo caso, il <xref:System.Windows.Controls.ToolBar> consente di visualizzare un pulsante di overflow. Per visualizzare gli elementi di overflow, un utente fa clic sul pulsante di overflow e gli elementi vengono visualizzati in una finestra popup seguente il <xref:System.Windows.Controls.ToolBar>. Il grafico seguente mostra un <xref:System.Windows.Controls.ToolBar> con elementi di overflow.  
  
 ![Barra degli strumenti con overflow](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
Oggetto Toolbar con elementi di overflow  
  
 È possibile specificare quando un elemento in una barra degli strumenti viene posizionato nel Pannello di overflow impostando il <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> proprietà associata <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>, o <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. L'esempio seguente specifica che gli ultimi quattro pulsanti della barra degli strumenti devono essere sempre posizionati nel pannello di overflow.  
  
 [!code-xaml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 Il <xref:System.Windows.Controls.ToolBar> utilizza un <xref:System.Windows.Controls.Primitives.ToolBarPanel> e una <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> nel relativo <xref:System.Windows.Controls.ControlTemplate>.  Il <xref:System.Windows.Controls.Primitives.ToolBarPanel> è responsabile per il layout degli elementi nella barra degli strumenti.  Il <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> è responsabile per il layout degli elementi che non si adattano il <xref:System.Windows.Controls.ToolBar>. Per un esempio di un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.ToolBar>, vedere  
  
 [Stili e modelli di ToolBar](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
 [Applicare uno stile ai controlli di un oggetto ToolBar](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)  
 [Esempio di raccolta di controlli WPF](https://go.microsoft.com/fwlink/?LinkID=160053)

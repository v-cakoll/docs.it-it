---
title: Cenni preliminari sui controlli ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: b5498b8b88c7403ffe51256a57544261de3ace08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186620"
---
# <a name="toolbar-overview"></a>Cenni preliminari sui controlli ToolBar
<xref:System.Windows.Controls.ToolBar>i controlli sono contenitori per un gruppo di comandi o controlli che sono in genere correlati nella loro funzione. Un <xref:System.Windows.Controls.ToolBar> di solito contiene pulsanti che richiamano i comandi.  

<a name="ToolBarControl"></a>
## <a name="toolbar-control"></a>Controllo ToolBar  
 Il <xref:System.Windows.Controls.ToolBar> controllo prende il nome dalla disposizione a barre di pulsanti o altri controlli in una singola riga o colonna. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.ToolBar> i controlli forniscono un meccanismo di overflow che posiziona <xref:System.Windows.Controls.ToolBar> tutti gli elementi che non rientrano naturalmente all'interno di un'area di overflow speciale. Inoltre, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> i controlli vengono <xref:System.Windows.Controls.ToolBarTray> in genere utilizzati con il controllo correlato, che fornisce un comportamento di layout speciale, nonché il supporto per il ridimensionamento avviato dall'utente e la disposizione delle barre degli strumenti.  
  
<a name="Creating_ToolBars"></a>
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Specifica della posizione dei controlli ToolBar in un oggetto ToolBarTray  
 Utilizzare <xref:System.Windows.Controls.ToolBar.Band%2A> le <xref:System.Windows.Controls.ToolBar.BandIndex%2A> proprietà e <xref:System.Windows.Controls.ToolBar> per <xref:System.Windows.Controls.ToolBarTray>posizionare l'oggetto nel file . <xref:System.Windows.Controls.ToolBar.Band%2A>indica la posizione in <xref:System.Windows.Controls.ToolBar> cui l'oggetto viene posizionato all'interno del relativo elemento padre. <xref:System.Windows.Controls.ToolBarTray> <xref:System.Windows.Controls.ToolBar.BandIndex%2A>indica l'ordine in <xref:System.Windows.Controls.ToolBar> cui l'oggetto viene posizionato all'interno della banda. Nell'esempio riportato di seguito <xref:System.Windows.Controls.ToolBar> viene <xref:System.Windows.Controls.ToolBarTray>illustrato come utilizzare questa proprietà per inserire i controlli all'interno di un oggetto .  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>
## <a name="toolbars-with-overflow-items"></a>Oggetti ToolBar con elementi di overflow  
 Spesso <xref:System.Windows.Controls.ToolBar> i controlli contengono più elementi di quelli che possono rientrare nelle dimensioni della barra degli strumenti. In questo caso, viene <xref:System.Windows.Controls.ToolBar> visualizzato un pulsante di overflow. Per visualizzare gli elementi di overflow, un utente fa clic sul pulsante <xref:System.Windows.Controls.ToolBar>di overflow e gli elementi vengono visualizzati in una finestra popup sotto il file . Il grafico seguente <xref:System.Windows.Controls.ToolBar> mostra un oggetto con overflow:  
  
 ![Screenshot che mostra una barra degli strumenti con elementi di overflow.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 È possibile specificare quando un elemento di una barra <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> degli strumenti <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType> <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>viene <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>posizionato nel pannello di overflow impostando la proprietà associata su , , o . L'esempio seguente specifica che gli ultimi quattro pulsanti della barra degli strumenti devono essere sempre posizionati nel pannello di overflow.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar> L'utilizza <xref:System.Windows.Controls.Primitives.ToolBarPanel> a <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> e <xref:System.Windows.Controls.ControlTemplate>un nel suo .  L'oggetto <xref:System.Windows.Controls.Primitives.ToolBarPanel> è responsabile del layout degli elementi della barra degli strumenti.  Il <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> campo è responsabile del layout degli <xref:System.Windows.Controls.ToolBar>elementi che non rientrano nel file . Per un esempio <xref:System.Windows.Controls.ControlTemplate> di <xref:System.Windows.Controls.ToolBar>a per un oggetto , vedere  
  
 [Stili e modelli ToolBar](toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [Applicare uno stile ai controlli di un oggetto ToolBar](how-to-style-controls-on-a-toolbar.md)
- [Esempio di raccolta di controlli WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)

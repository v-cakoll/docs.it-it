---
title: Cenni preliminari sui controlli ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 460d4420d5faf849a8d05a94e0170aea384f69b4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452695"
---
# <a name="toolbar-overview"></a>Cenni preliminari sui controlli ToolBar
<xref:System.Windows.Controls.ToolBar> controlli sono contenitori per un gruppo di comandi o controlli che in genere sono correlati alla relativa funzione. Un <xref:System.Windows.Controls.ToolBar> contiene in genere pulsanti che richiamano i comandi.  

<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>Controllo ToolBar  
 Il controllo <xref:System.Windows.Controls.ToolBar> prende il nome dalla disposizione dei pulsanti o di altri controlli a barre in una singola riga o colonna. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli <xref:System.Windows.Controls.ToolBar> forniscono un meccanismo di overflow che inserisce tutti gli elementi che non rientrano naturalmente in un <xref:System.Windows.Controls.ToolBar> vincolato alle dimensioni in un'area di overflow speciale. Inoltre, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli <xref:System.Windows.Controls.ToolBar> vengono in genere utilizzati con il controllo <xref:System.Windows.Controls.ToolBarTray> correlato, che fornisce un comportamento di layout speciale, nonché il supporto per il ridimensionamento e la disposizione delle barre degli strumenti avviate dall'utente.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Specifica della posizione dei controlli ToolBar in un oggetto ToolBarTray  
 Usare le proprietà <xref:System.Windows.Controls.ToolBar.Band%2A> e <xref:System.Windows.Controls.ToolBar.BandIndex%2A> per posizionare il <xref:System.Windows.Controls.ToolBar> nel <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.Band%2A> indica la posizione in cui viene inserita la <xref:System.Windows.Controls.ToolBar> all'interno del <xref:System.Windows.Controls.ToolBarTray>padre. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> indica l'ordine in cui la <xref:System.Windows.Controls.ToolBar> viene posizionata all'interno della banda. Nell'esempio seguente viene illustrato come utilizzare questa proprietà per inserire controlli <xref:System.Windows.Controls.ToolBar> all'interno di un <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>Oggetti ToolBar con elementi di overflow  
 Spesso <xref:System.Windows.Controls.ToolBar> controlli contengono più elementi di quelli che possono essere inseriti nella dimensione della barra degli strumenti. Quando si verifica questo problema, nel <xref:System.Windows.Controls.ToolBar> viene visualizzato un pulsante di overflow. Per visualizzare gli elementi di overflow, un utente fa clic sul pulsante di overflow e gli elementi vengono visualizzati in una finestra popup sotto la <xref:System.Windows.Controls.ToolBar>. Il grafico seguente mostra un <xref:System.Windows.Controls.ToolBar> con elementi di overflow:  
  
 ![Screenshot che mostra una barra degli strumenti con elementi di overflow.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 È possibile specificare quando un elemento di una barra degli strumenti viene posizionato nel pannello di overflow impostando la proprietà associata <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> su <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>o <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. L'esempio seguente specifica che gli ultimi quattro pulsanti della barra degli strumenti devono essere sempre posizionati nel pannello di overflow.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 Il <xref:System.Windows.Controls.ToolBar> utilizza una <xref:System.Windows.Controls.Primitives.ToolBarPanel> e un <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> nel <xref:System.Windows.Controls.ControlTemplate>.  Il <xref:System.Windows.Controls.Primitives.ToolBarPanel> è responsabile del layout degli elementi sulla barra degli strumenti.  Il <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> è responsabile del layout degli elementi che non rientrano nel <xref:System.Windows.Controls.ToolBar>. Per un esempio di <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.ToolBar>, vedere  
  
 [Stili e modelli di ToolBar](toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [Applicare uno stile ai controlli di un oggetto ToolBar](how-to-style-controls-on-a-toolbar.md)
- [Esempio di raccolta di controlli WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)

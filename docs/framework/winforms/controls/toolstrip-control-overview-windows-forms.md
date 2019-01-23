---
title: Cenni preliminari sul controllo ToolStrip (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 49f544727ee82b1e36357fc4312bcd449ffc3c0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558748"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Cenni preliminari sul controllo ToolStrip (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.ToolStrip> controllo e le classi associate forniscono un framework comune per combinare gli elementi dell'interfaccia utente nelle barre degli strumenti, barre di stato e menu. <xref:System.Windows.Forms.ToolStrip> controlli offrono una ricca esperienza della fase di progettazione che include l'attivazione sul posto e modifica, il layout personalizzato e raggruppamento verticale/orizzontale, ovvero la capacità delle barre degli strumenti di condividere lo spazio orizzontale o verticale.  
  
 Sebbene <xref:System.Windows.Forms.ToolStrip> sostituisce e aggiunge funzionalità al controllo nelle versioni precedenti, <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se si desidera.  
  
## <a name="features-of-the-toolstrip-controls"></a>Funzionalità dei controlli ToolStrip  
 Usare il <xref:System.Windows.Forms.ToolStrip> controllo:  
  
-   Presentare un'interfaccia utente comune tra contenitori.  
  
-   Creare con facilità personalizzato, impiego frequente barre degli strumenti che supportano avanzate funzionalità di layout e interfaccia utente, ad esempio di ancoraggio, raggruppamento verticale/orizzontale, i pulsanti con testo e immagini, caselle di riepilogo e i controlli, pulsanti di overflow e riordinamento dei runtime di <xref:System.Windows.Forms.ToolStrip> elementi.  
  
-   Supporto di overflow e il riordinamento degli elementi in fase di esecuzione. La funzionalità di overflow sposta gli elementi in un menu di scelta rapida quando non vi è spazio sufficiente per visualizzarli in un <xref:System.Windows.Forms.ToolStrip>.  
  
-   Supporta l'aspetto tipico e il comportamento del sistema operativo tramite un modello comune per il rendering.  
  
-   Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo è possibile gestire gli eventi per altri controlli.  
  
-   Trascinare gli elementi da una <xref:System.Windows.Forms.ToolStrip> a un altro o in un <xref:System.Windows.Forms.ToolStrip>.  
  
-   Creare editor di tipi di interfaccia di utente e i controlli elenco a discesa con layout avanzati in un <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Usare la <xref:System.Windows.Forms.ToolStripControlHost> classe da utilizzare altri controlli in un <xref:System.Windows.Forms.ToolStrip> e ottenere <xref:System.Windows.Forms.ToolStrip> funzionalità relativa.  
  
 È possibile estendere le funzionalità e modificare l'aspetto e comportamento usando il <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, e <xref:System.Windows.Forms.ToolStripManager> insieme al <xref:System.Windows.Forms.ToolStripRenderMode> e <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumerazioni.  
  
 Il <xref:System.Windows.Forms.ToolStrip> controllo è altamente configurabili ed estensibile e offre molte proprietà, metodi ed eventi per personalizzare l'aspetto e comportamento. Ecco alcuni membri degno di nota:  
  
### <a name="important-toolstrip-members"></a>Membri importanti di ToolStrip  
  
|nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Ottiene o imposta il bordo del contenitore padre un <xref:System.Windows.Forms.ToolStrip> è ancorato.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Ottiene o imposta un valore che indica se le operazioni di trascinamento e rilascio e ridisposizione degli elementi devono essere gestite privatamente dalla classe <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Ottiene o imposta un valore che indica come il <xref:System.Windows.Forms.ToolStrip> definisce i relativi elementi.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Ottiene o imposta se un <xref:System.Windows.Forms.ToolStripItem> è collegata la <xref:System.Windows.Forms.ToolStrip> o <xref:System.Windows.Forms.ToolStripOverflowButton> può spostarsi tra i due.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Ottiene un valore che indica se un <xref:System.Windows.Forms.ToolStripItem> altri elementi vengono visualizzati in un elenco a discesa elenco quando il <xref:System.Windows.Forms.ToolStripItem> si fa clic.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Ottiene l'oggetto <xref:System.Windows.Forms.ToolStripItem> che rappresenta il pulsante di overflow di un oggetto <xref:System.Windows.Forms.ToolStrip> con l'overflow abilitato.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Ottiene o imposta una <xref:System.Windows.Forms.ToolStripRenderer> usato per personalizzare l'aspetto e comportamento (aspetto) di un <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Ottiene o imposta gli stili di disegno da applicare al <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Eccezione generata quando il <xref:System.Windows.Forms.ToolStrip.Renderer%2A> le modifiche alle proprietà.|  
  
 Il <xref:System.Windows.Forms.ToolStrip> flessibilità del controllo viene ottenuta tramite l'uso di un numero di classi correlate. Ecco alcune delle più importanti:  
  
### <a name="important-toolstrip-companion-classes"></a>Classi importanti correlate al controllo ToolStrip  
  
|nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Sostituisce e aggiunge funzionalità per il <xref:System.Windows.Forms.MainMenu> classe.|  
|<xref:System.Windows.Forms.StatusStrip>|Sostituisce e aggiunge funzionalità per il <xref:System.Windows.Forms.StatusBar> classe.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Sostituisce e aggiunge funzionalità per il <xref:System.Windows.Forms.ContextMenu> classe.|  
|<xref:System.Windows.Forms.ToolStripItem>|Classe base astratta che gestisce gli eventi e il layout per tutti gli elementi che un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, o <xref:System.Windows.Forms.ToolStripDropDown> può contenere.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Fornisce un contenitore con un pannello su ciascun lato del form in cui è possibile disporre i controlli in vari modi.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Gestisce la funzionalità di disegno per <xref:System.Windows.Forms.ToolStrip> oggetti.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Fornisce l'aspetto di stile Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Controlla il rendering e il raggruppamento verticale/orizzontale dei controlli <xref:System.Windows.Forms.ToolStrip> nonché l'unione degli oggetti <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> e <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Specifica lo stile di disegno (personalizzata, Windows XP o Microsoft Office Professional) applicato a più <xref:System.Windows.Forms.ToolStrip> gli oggetti contenuti in un form.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Specifica lo stile di disegno (personalizzata, Windows XP o Microsoft Office Professional) applicato a uno <xref:System.Windows.Forms.ToolStrip> oggetto contenuto in un form.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Ospita altri controlli che non sono specificamente <xref:System.Windows.Forms.ToolStrip> controlli, ma si vuole <xref:System.Windows.Forms.ToolStrip> funzionalità.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Specifica se un <xref:System.Windows.Forms.ToolStripItem> deve essere disposto in principale <xref:System.Windows.Forms.ToolStrip>, sull'overflow <xref:System.Windows.Forms.ToolStrip>, o nessuna delle due.|  
  
 Per altre informazioni, vedere [riepilogo della tecnologia ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) e [architettura del controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>

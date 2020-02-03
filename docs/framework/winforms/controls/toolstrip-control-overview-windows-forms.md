---
title: Cenni preliminari sul controllo ToolStrip
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741071"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Panoramica del controllo ToolStrip (Windows Form)
Il Windows Forms controllo <xref:System.Windows.Forms.ToolStrip> e le classi associate forniscono un Framework comune per combinare gli elementi dell'interfaccia utente nelle barre degli strumenti, nelle barre di stato e nei menu. i controlli <xref:System.Windows.Forms.ToolStrip> offrono un'esperienza avanzata in fase di progettazione che include l'attivazione e la modifica sul posto, il layout personalizzato e il rafting, ovvero la capacità delle barre degli strumenti di condividere lo spazio orizzontale o verticale.  
  
 Anche se <xref:System.Windows.Forms.ToolStrip> sostituisce e aggiunge funzionalità al controllo nelle versioni precedenti, la <xref:System.Windows.Forms.ToolBar> viene mantenuta sia per la compatibilità con le versioni precedenti che per un uso futuro, se lo si desidera.  
  
## <a name="features-of-the-toolstrip-controls"></a>Funzionalità dei controlli ToolStrip  
 Usare il controllo <xref:System.Windows.Forms.ToolStrip> per:  
  
- Presentare un'interfaccia utente comune tra i contenitori.  
  
- Creazione di barre degli strumenti facilmente personalizzabili e di uso comune che supportano interfacce utente e funzionalità di layout avanzate, ad esempio l'ancoraggio, il raggruppamento di pulsanti, i pulsanti con testo e immagini, i pulsanti e i controlli a discesa, i pulsanti di overflow e il riordinamento della fase di esecuzione degli elementi <xref:System.Windows.Forms.ToolStrip>.  
  
- Supporto dell'overflow e riordinamento degli elementi in fase di esecuzione. La funzionalità di overflow sposta gli elementi in un menu a discesa quando lo spazio disponibile non è sufficiente per visualizzarli in una <xref:System.Windows.Forms.ToolStrip>.  
  
- Supportare l'aspetto e il comportamento tipici del sistema operativo tramite un modello di rendering comune.  
  
- Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo in cui si gestiscono gli eventi per altri controlli.  
  
- Trascinare gli elementi da una <xref:System.Windows.Forms.ToolStrip> a un'altra o all'interno di un <xref:System.Windows.Forms.ToolStrip>.  
  
- Creare controlli a discesa e editor di tipi di interfaccia utente con layout avanzati in una <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Usare la classe <xref:System.Windows.Forms.ToolStripControlHost> per usare altri controlli in una <xref:System.Windows.Forms.ToolStrip> e ottenere <xref:System.Windows.Forms.ToolStrip> funzionalità.  
  
 È possibile estendere la funzionalità e modificare l'aspetto e il comportamento usando il <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>e <xref:System.Windows.Forms.ToolStripManager> insieme alle enumerazioni <xref:System.Windows.Forms.ToolStripRenderMode> e <xref:System.Windows.Forms.ToolStripManagerRenderMode>.  
  
 Il controllo <xref:System.Windows.Forms.ToolStrip> è altamente configurabile ed estendibile e fornisce molte proprietà, metodi ed eventi per personalizzare l'aspetto e il comportamento. Di seguito sono riportati alcuni membri degni di Nota:  
  
### <a name="important-toolstrip-members"></a>Membri ToolStrip importanti  
  
|Name|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Ottiene o imposta il bordo del contenitore padre a cui è ancorato un <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Ottiene o imposta un valore che indica se le operazioni di trascinamento e rilascio e ridisposizione degli elementi devono essere gestite privatamente dalla classe <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Ottiene o imposta un valore che indica il modo in cui il <xref:System.Windows.Forms.ToolStrip> definisce gli elementi.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Ottiene o imposta un valore che indica se un <xref:System.Windows.Forms.ToolStripItem> è collegato al <xref:System.Windows.Forms.ToolStrip> o <xref:System.Windows.Forms.ToolStripOverflowButton> oppure se può essere fluttuato tra i due.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Ottiene un valore che indica se un <xref:System.Windows.Forms.ToolStripItem> Visualizza altri elementi in un elenco a discesa quando si fa clic sull'<xref:System.Windows.Forms.ToolStripItem>.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Ottiene l'oggetto <xref:System.Windows.Forms.ToolStripItem> che rappresenta il pulsante di overflow di un oggetto <xref:System.Windows.Forms.ToolStrip> con l'overflow abilitato.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Ottiene o imposta un <xref:System.Windows.Forms.ToolStripRenderer> utilizzato per personalizzare l'aspetto e il comportamento (aspetto) di un <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Ottiene o imposta gli stili di disegno da applicare al <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Generato quando la proprietà <xref:System.Windows.Forms.ToolStrip.Renderer%2A> viene modificata.|  
  
 La flessibilità del controllo <xref:System.Windows.Forms.ToolStrip> viene eseguita tramite l'utilizzo di una serie di classi complementari. Di seguito sono riportati alcuni dei più importanti:  
  
### <a name="important-toolstrip-companion-classes"></a>Classi complementari di ToolStrip importanti  
  
|Name|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Sostituisce e aggiunge funzionalità alla classe <xref:System.Windows.Forms.MainMenu>.|  
|<xref:System.Windows.Forms.StatusStrip>|Sostituisce e aggiunge funzionalità alla classe <xref:System.Windows.Forms.StatusBar>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Sostituisce e aggiunge funzionalità alla classe <xref:System.Windows.Forms.ContextMenu>.|  
|<xref:System.Windows.Forms.ToolStripItem>|Classe di base astratta che gestisce gli eventi e il layout di tutti gli elementi che possono essere contenuti in un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>o <xref:System.Windows.Forms.ToolStripDropDown>.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Fornisce un contenitore con un pannello su ogni lato del form in cui i controlli possono essere disposti in diversi modi.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Gestisce la funzionalità di disegno per gli oggetti <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Fornisce l'aspetto di tipo Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Controlla il rendering e il raggruppamento verticale/orizzontale dei controlli <xref:System.Windows.Forms.ToolStrip> nonché l'unione degli oggetti <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> e <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Specifica lo stile di disegno (personalizzato, Windows XP o Microsoft Office Professional) applicato a più oggetti <xref:System.Windows.Forms.ToolStrip> contenuti in un modulo.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Specifica lo stile di disegno (personalizzato, Windows XP o Microsoft Office Professional) applicato a un <xref:System.Windows.Forms.ToolStrip> oggetto contenuto in un modulo.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Ospita altri controlli che non sono specificamente <xref:System.Windows.Forms.ToolStrip> controlli ma per i quali si desidera <xref:System.Windows.Forms.ToolStrip> funzionalità.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Specifica se un <xref:System.Windows.Forms.ToolStripItem> deve essere disposto sulla <xref:System.Windows.Forms.ToolStrip>principale, sulla <xref:System.Windows.Forms.ToolStrip>di overflow o su nessuno dei due.|  
  
 Per ulteriori informazioni, vedere [Panoramica della tecnologia ToolStrip](toolstrip-technology-summary.md) e [architettura del controllo ToolStrip](toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>

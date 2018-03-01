---
title: Architettura del controllo DataGridView (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b3e51b87cdd766adcc10aa3f682647b28fbbe4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="datagridview-control-architecture-windows-forms"></a>Architettura del controllo DataGridView (Windows Form)
Il <xref:System.Windows.Forms.DataGridView> controllo e le relative classi sono progettate per essere un sistema flessibile ed estendibile per la visualizzazione e modifica di dati tabulari. Queste classi sono contenute nel <xref:System.Windows.Forms?displayProperty=nameWithType> dello spazio dei nomi e nomi con il prefisso "DataGridView".  
  
## <a name="architecture-elements"></a>Elementi dell'architettura  
 Il database primario <xref:System.Windows.Forms.DataGridView> classi correlate derivano da <xref:System.Windows.Forms.DataGridViewElement>. Il modello a oggetti seguente viene illustrato il <xref:System.Windows.Forms.DataGridViewElement> gerarchia di ereditarietà.  
  
 ![Modello a oggetti DataGridViewElement](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")  
Modello a oggetti DataGridViewElement  
  
 Il <xref:System.Windows.Forms.DataGridViewElement> classe fornisce un riferimento all'elemento padre <xref:System.Windows.Forms.DataGridView> controllare e ha un <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà che contiene un valore che rappresenta una combinazione di valori dal <xref:System.Windows.Forms.DataGridViewElementStates> enumerazione.  
  
 Le sezioni seguenti descrivono il <xref:System.Windows.Forms.DataGridView> complementare classi in modo più dettagliato.  
  
### <a name="datagridviewelementstates"></a>Oggetto DataGridViewElementStates  
 Il <xref:System.Windows.Forms.DataGridViewElementStates> enumerazione contiene i valori seguenti:  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 I valori di questa enumerazione possono essere combinati con gli operatori logici OR bit per bit, pertanto la <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà in grado di esprimere più di uno stato in una sola volta. Ad esempio, un <xref:System.Windows.Forms.DataGridViewElement> che può essere contemporaneamente <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, e <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.  
  
### <a name="cells-and-bands"></a>Le celle e bande  
 Il <xref:System.Windows.Forms.DataGridView> controllo comprende due tipi fondamentali di oggetti: celle e bande. Tutte le celle derivano il <xref:System.Windows.Forms.DataGridViewCell> classe di base. I due tipi di bande, <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewRow>, entrambi derivano dalla <xref:System.Windows.Forms.DataGridViewBand> classe di base.  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo interagisce con diverse classi, ma sono i più comuni <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, e <xref:System.Windows.Forms.DataGridViewRow>.  
  
### <a name="datagridviewcell"></a>Oggetto DataGridViewCell  
 La cella è l'unità fondamentale di interazione per i <xref:System.Windows.Forms.DataGridView>. La visualizzazione si basa sulle celle e immissione di dati viene spesso eseguita tramite le celle. È possibile accedere alle celle con il <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> insieme del <xref:System.Windows.Forms.DataGridViewRow> classe ed è possibile accedere alle celle selezionate utilizzando il <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> insieme del <xref:System.Windows.Forms.DataGridView> controllo. Il modello a oggetti seguente viene illustrato l'utilizzo e Mostra il <xref:System.Windows.Forms.DataGridViewCell> gerarchia di ereditarietà.  
  
 ![Modello a oggetti DataGridViewCell](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")  
Modello a oggetti DataGridViewCell  
  
 Il <xref:System.Windows.Forms.DataGridViewCell> tipo è una classe base astratta da cui derivano tutti i tipi di cella. <xref:System.Windows.Forms.DataGridViewCell>e i tipi derivati non sono controlli Windows Form, ma alcuni controlli Windows Form host. Supportato da una cella qualsiasi funzionalità di modifica viene in genere gestita da un controllo ospitato.  
  
 <xref:System.Windows.Forms.DataGridViewCell>gli oggetti non controllare l'aspetto e le funzionalità di disegno nello stesso modo dei controlli Windows Form. Al contrario, il <xref:System.Windows.Forms.DataGridView> è responsabile per l'aspetto del relativo <xref:System.Windows.Forms.DataGridViewCell> oggetti. È possibile modificare in modo significativo l'aspetto e il comportamento di celle tramite l'interazione con il <xref:System.Windows.Forms.DataGridView> proprietà e gli eventi del controllo. Quando si dispone di requisiti speciali per le personalizzazioni che vanno oltre le capacità del <xref:System.Windows.Forms.DataGridView> (controllo), è possibile implementare la propria classe che deriva da <xref:System.Windows.Forms.DataGridViewCell> o una delle relative classi figlio.  
  
 L'elenco seguente mostra le classi derivate da <xref:System.Windows.Forms.DataGridViewCell>:  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   I tipi di cella personalizzato  
  
### <a name="datagridviewcolumn"></a>Elemento DataGridViewColumn  
 Lo schema del <xref:System.Windows.Forms.DataGridView> archivio dati collegati del controllo è espresso il <xref:System.Windows.Forms.DataGridView> colonne del controllo. È possibile accedere il <xref:System.Windows.Forms.DataGridView> colonne del controllo utilizzando il <xref:System.Windows.Forms.DataGridView.Columns%2A> insieme. È possibile accedere alle colonne selezionate utilizzando il <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> insieme. Il modello a oggetti seguente viene illustrato l'utilizzo e Mostra il <xref:System.Windows.Forms.DataGridViewColumn> gerarchia di ereditarietà.  
  
 ![Modello a oggetti DataGridViewColumn](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")  
Modello a oggetti DataGridViewColumn  
  
 Alcuni dei tipi di cella chiave hanno tipi di colonna corrispondenti. Questi sono derivati dalla <xref:System.Windows.Forms.DataGridViewColumn> classe di base.  
  
 L'elenco seguente mostra le classi derivate da <xref:System.Windows.Forms.DataGridViewColumn>:  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   Tipi di colonna personalizzati  
  
### <a name="datagridview-editing-controls"></a>Controlli di modifica DataGridView  
 Le celle che supportano le funzionalità avanzate di modifica in genere utilizzano un controllo derivato da un controllo Windows Form. Questi controlli implementano anche il <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaccia. Il modello a oggetti seguente viene illustrato l'utilizzo di questi controlli.  
  
 ![Modello oggetto di controllo di modifica DataGridView](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")  
Modifica modello a oggetti controllo DataGridView  
  
 Vengono forniti i seguenti controlli di modificando con il <xref:System.Windows.Forms.DataGridView> controllo:  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Per informazioni sulla creazione di controlli personalizzati di modifica, vedere [come: i controlli Host nelle celle del controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 Nella tabella seguente viene illustrata la relazione tra i tipi di cella, i tipi di colonna e i controlli di modifica.  
  
|Tipo di cella|Controllo ospitato|Tipo di colonna|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|N/D|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|n/d|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|n/d|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|N/D|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 Il <xref:System.Windows.Forms.DataGridViewRow> Visualizza di classe campi dati di un record dai dati di archivio a cui il <xref:System.Windows.Forms.DataGridView> controllo associato. È possibile accedere il <xref:System.Windows.Forms.DataGridView> righe del controllo utilizzando il <xref:System.Windows.Forms.DataGridView.Rows%2A> insieme. È possibile accedere alle righe selezionate utilizzando il <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> insieme. Il modello a oggetti seguente viene illustrato l'utilizzo e Mostra il <xref:System.Windows.Forms.DataGridViewRow> gerarchia di ereditarietà.  
  
 ![Modello a oggetti DataGridViewRow](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")  
Modello a oggetti DataGridViewRow  
  
 È possibile derivare tipi personalizzati dalla <xref:System.Windows.Forms.DataGridViewRow> classe, anche se ciò corrisponderà in genere non necessario. Il <xref:System.Windows.Forms.DataGridView> controllo dispone di numerosi eventi correlati alla riga e proprietà per personalizzare il comportamento del relativo <xref:System.Windows.Forms.DataGridViewRow> oggetti.  
  
 Se si abilita il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> viene visualizzata una riga speciale per l'aggiunta di nuove righe di proprietà, come l'ultima riga. Questa riga fa parte di <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta, ma dispone di funzionalità speciali che potrebbero richiedere attenzione. Per ulteriori informazioni, vedere [mediante la riga dei nuovi record nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sul controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [Personalizzazione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [Uso della riga per i nuovi record del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)

---
title: Architettura del controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742534"
---
# <a name="datagridview-control-architecture-windows-forms"></a>Architettura del controllo DataGridView (Windows Form)
Il controllo <xref:System.Windows.Forms.DataGridView> e le classi correlate sono progettati per essere un sistema flessibile ed estendibile per la visualizzazione e la modifica dei dati tabulari. Queste classi sono tutte contenute nello spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> e sono tutte denominate con il prefisso "DataGridView".  
  
## <a name="architecture-elements"></a>Elementi dell'architettura  
 Le classi principali <xref:System.Windows.Forms.DataGridView> complementari derivano da <xref:System.Windows.Forms.DataGridViewElement>. Nel modello a oggetti seguente viene illustrata la gerarchia di ereditarietà <xref:System.Windows.Forms.DataGridViewElement>.  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewElement.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 La classe <xref:System.Windows.Forms.DataGridViewElement> fornisce un riferimento al controllo <xref:System.Windows.Forms.DataGridView> padre e ha una proprietà <xref:System.Windows.Forms.DataGridViewElement.State%2A>, che contiene un valore che rappresenta una combinazione di valori dell'enumerazione <xref:System.Windows.Forms.DataGridViewElementStates>.  
  
 Le sezioni seguenti descrivono in modo più dettagliato le classi <xref:System.Windows.Forms.DataGridView> complementari.  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 L'enumerazione <xref:System.Windows.Forms.DataGridViewElementStates> contiene i valori seguenti:  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 I valori di questa enumerazione possono essere combinati con gli operatori logici bit per bit, quindi la proprietà <xref:System.Windows.Forms.DataGridViewElement.State%2A> può esprimere più di uno stato in una sola volta. Ad esempio, un <xref:System.Windows.Forms.DataGridViewElement> può essere contemporaneamente <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>e <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.  
  
### <a name="cells-and-bands"></a>Celle e bande  
 Il controllo <xref:System.Windows.Forms.DataGridView> è costituito da due tipi fondamentali di oggetti, ovvero celle e bande. Tutte le celle derivano dalla classe di base <xref:System.Windows.Forms.DataGridViewCell>. I due tipi di bande, <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewRow>, derivano entrambi dalla classe di base <xref:System.Windows.Forms.DataGridViewBand>.  
  
 Il controllo <xref:System.Windows.Forms.DataGridView> interagisce con diverse classi, ma il più comunemente rilevato sono <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>e <xref:System.Windows.Forms.DataGridViewRow>.  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 La cella è l'unità fondamentale di interazione per la <xref:System.Windows.Forms.DataGridView>. La visualizzazione è centrata sulle celle e l'immissione dei dati viene spesso eseguita tramite le celle. È possibile accedere alle celle usando la raccolta <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> della classe <xref:System.Windows.Forms.DataGridViewRow> ed è possibile accedere alle celle selezionate usando la raccolta <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> del controllo <xref:System.Windows.Forms.DataGridView>. Nel modello a oggetti seguente viene illustrato questo utilizzo e viene illustrata la gerarchia di ereditarietà <xref:System.Windows.Forms.DataGridViewCell>.  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewCell.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 Il tipo di <xref:System.Windows.Forms.DataGridViewCell> è una classe di base astratta dalla quale derivano tutti i tipi di cella. <xref:System.Windows.Forms.DataGridViewCell> e i tipi derivati non sono Windows Forms controlli, ma alcuni controlli Windows Forms host. Qualsiasi funzionalità di modifica supportata da una cella viene in genere gestita da un controllo ospitato.  
  
 <xref:System.Windows.Forms.DataGridViewCell> oggetti non controllano l'aspetto e le funzionalità di disegno in modo analogo ai controlli Windows Forms. Il <xref:System.Windows.Forms.DataGridView> è invece responsabile dell'aspetto degli oggetti <xref:System.Windows.Forms.DataGridViewCell>. È possibile influenzare in modo significativo l'aspetto e il comportamento delle celle interagendo con le proprietà e gli eventi del controllo <xref:System.Windows.Forms.DataGridView>. Quando si hanno requisiti speciali per le personalizzazioni che esulano dalle funzionalità del controllo <xref:System.Windows.Forms.DataGridView>, è possibile implementare una classe personalizzata che deriva da <xref:System.Windows.Forms.DataGridViewCell> o da una delle relative classi figlio.  
  
 Nell'elenco seguente vengono illustrate le classi derivate da <xref:System.Windows.Forms.DataGridViewCell>:  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- Tipi di cella personalizzati  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 Lo schema dell'archivio dati associato del controllo <xref:System.Windows.Forms.DataGridView> è espresso nelle colonne del controllo <xref:System.Windows.Forms.DataGridView>. È possibile accedere alle colonne del controllo <xref:System.Windows.Forms.DataGridView> tramite la raccolta di <xref:System.Windows.Forms.DataGridView.Columns%2A>. È possibile accedere alle colonne selezionate utilizzando la raccolta <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. Nel modello a oggetti seguente viene illustrato questo utilizzo e viene illustrata la gerarchia di ereditarietà <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewColumn.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 Alcuni tipi di cella chiave hanno tipi di colonna corrispondenti. Sono derivati dalla classe di base <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 Nell'elenco seguente vengono illustrate le classi derivate da <xref:System.Windows.Forms.DataGridViewColumn>:  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- Tipi di colonna personalizzati  
  
### <a name="datagridview-editing-controls"></a>Controlli di modifica DataGridView  
 Le celle che supportano la funzionalità di modifica avanzata utilizzano in genere un controllo ospitato derivato da un controllo Windows Forms. Questi controlli implementano anche l'interfaccia <xref:System.Windows.Forms.IDataGridViewEditingControl>. Nel modello a oggetti seguente viene illustrato l'utilizzo di questi controlli.  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti del controllo di modifica DataGridView.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 Con il controllo <xref:System.Windows.Forms.DataGridView> vengono forniti i controlli di modifica seguenti:  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Per informazioni sulla creazione di controlli di modifica personalizzati, vedere [How to: Host Controls in Windows Forms celle DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 Nella tabella seguente viene illustrata la relazione tra i tipi di cella, i tipi di colonna e i controlli di modifica.  
  
|Tipo di cella|Controllo ospitato|Tipo di colonna|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|N/D|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|N/D|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|N/D|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|N/D|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 La classe <xref:System.Windows.Forms.DataGridViewRow> Visualizza i campi dati di un record dall'archivio dati a cui è associato il controllo <xref:System.Windows.Forms.DataGridView>. È possibile accedere alle righe del controllo <xref:System.Windows.Forms.DataGridView> tramite la raccolta di <xref:System.Windows.Forms.DataGridView.Rows%2A>. È possibile accedere alle righe selezionate utilizzando la raccolta <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>. Nel modello a oggetti seguente viene illustrato questo utilizzo e viene illustrata la gerarchia di ereditarietà <xref:System.Windows.Forms.DataGridViewRow>.  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewRow.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 È possibile derivare i propri tipi dalla classe <xref:System.Windows.Forms.DataGridViewRow>, anche se in genere non è necessario. Il controllo <xref:System.Windows.Forms.DataGridView> dispone di diversi eventi e proprietà correlati alle righe per la personalizzazione del comportamento degli oggetti <xref:System.Windows.Forms.DataGridViewRow>.  
  
 Se si Abilita la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> del controllo <xref:System.Windows.Forms.DataGridView>, viene visualizzata una riga speciale per l'aggiunta di nuove righe come ultima riga. Questa riga fa parte della raccolta di <xref:System.Windows.Forms.DataGridView.Rows%2A>, ma dispone di funzionalità speciali che potrebbero richiedere attenzione. Per ulteriori informazioni, vedere [utilizzo della riga per i nuovi record nel controllo DataGridView Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul controllo DataGridView](datagridview-control-overview-windows-forms.md)
- [Personalizzazione del controllo DataGridView di Windows Form](customizing-the-windows-forms-datagridview-control.md)
- [Uso della riga per i nuovi record del controllo DataGridView di Windows Form](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)

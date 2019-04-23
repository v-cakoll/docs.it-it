---
title: Architettura del controllo DataGridView (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 892168ec282fbf168c43515e0718fe5486a345a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130260"
---
# <a name="datagridview-control-architecture-windows-forms"></a>Architettura del controllo DataGridView (Windows Form)
Il <xref:System.Windows.Forms.DataGridView> controllo e le classi correlate sono progettate per essere un sistema flessibile ed estendibile per la visualizzazione e modifica di dati tabulari. Tutte queste classi sono contenute nel <xref:System.Windows.Forms?displayProperty=nameWithType> dello spazio dei nomi essi sono denominati con il prefisso "DataGridView".  
  
## <a name="architecture-elements"></a>Elementi dell'architettura  
 Il database primario <xref:System.Windows.Forms.DataGridView> complementare classi derivano da <xref:System.Windows.Forms.DataGridViewElement>. Il modello a oggetti seguente viene illustrato il <xref:System.Windows.Forms.DataGridViewElement> gerarchia di ereditarietà.  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewElement.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 Il <xref:System.Windows.Forms.DataGridViewElement> classe fornisce un riferimento all'elemento padre <xref:System.Windows.Forms.DataGridView> controllano e dispone di un <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà, che contiene un valore che rappresenta una combinazione di valori dal <xref:System.Windows.Forms.DataGridViewElementStates> enumerazione.  
  
 Le sezioni seguenti descrivono la <xref:System.Windows.Forms.DataGridView> companion in classi in modo più dettagliato.  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 Il <xref:System.Windows.Forms.DataGridViewElementStates> enumerazione contiene i valori seguenti:  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 I valori di questa enumerazione possono essere combinati con gli operatori logici bit per bit, pertanto il <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà possibile esprimere in una sola volta più di uno stato. Ad esempio, un <xref:System.Windows.Forms.DataGridViewElement> può essere contemporaneamente <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, e <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.  
  
### <a name="cells-and-bands"></a>Le celle e bande  
 Il <xref:System.Windows.Forms.DataGridView> comprende due tipi principali di oggetti: le celle e bande. Tutte le celle derivano dal <xref:System.Windows.Forms.DataGridViewCell> classe di base. I due tipi di bande, <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewRow>, entrambi derivano dal <xref:System.Windows.Forms.DataGridViewBand> classe di base.  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo interagisce con diverse classi, ma sono le più comuni <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, e <xref:System.Windows.Forms.DataGridViewRow>.  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 La cella è l'unità fondamentale di interazione per i <xref:System.Windows.Forms.DataGridView>. La visualizzazione si basa su celle e immissione di dati viene spesso eseguita tramite le celle. Le celle è possibile accedere usando il <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> raccolta del <xref:System.Windows.Forms.DataGridViewRow> classe ed è possibile accedere alle celle selezionate tramite il <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> raccolta del <xref:System.Windows.Forms.DataGridView> controllo. Il modello a oggetti seguente ne illustra l'utilizzo e viene illustrato il <xref:System.Windows.Forms.DataGridViewCell> gerarchia di ereditarietà.  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewCell.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 Il <xref:System.Windows.Forms.DataGridViewCell> tipo è una classe base astratta, da cui derivano tutti i tipi di cella. <xref:System.Windows.Forms.DataGridViewCell> e non i relativi tipi derivati sono controlli Windows Form, ma alcuni controlli Windows Form host. Nessuna funzionalità di modifica supportata da una cella viene in genere gestita da un controllo ospitato.  
  
 <xref:System.Windows.Forms.DataGridViewCell> gli oggetti non controllano proprio aspetto e funzionalità di disegno nello stesso modo dei controlli Windows Form. Al contrario, il <xref:System.Windows.Forms.DataGridView> è responsabile per l'aspetto del relativo <xref:System.Windows.Forms.DataGridViewCell> oggetti. È possibile modificare in modo significativo l'aspetto e il comportamento di celle tramite l'interazione con il <xref:System.Windows.Forms.DataGridView> proprietà e gli eventi del controllo. Quando si hanno requisiti speciali per le personalizzazioni che vanno oltre le capacità dei <xref:System.Windows.Forms.DataGridView> (controllo), è possibile implementare una classe che deriva da <xref:System.Windows.Forms.DataGridViewCell> o una delle relative classi figlio.  
  
 Nell'elenco seguente vengono illustrate le classi derivate da <xref:System.Windows.Forms.DataGridViewCell>:  
  
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
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 Lo schema del <xref:System.Windows.Forms.DataGridView> archivio di dati collegati del controllo è espressa nel <xref:System.Windows.Forms.DataGridView> colonne del controllo. È possibile accedere la <xref:System.Windows.Forms.DataGridView> colonne del controllo utilizzando il <xref:System.Windows.Forms.DataGridView.Columns%2A> raccolta. È possibile accedere alle colonne selezionate tramite il <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> raccolta. Il modello a oggetti seguente ne illustra l'utilizzo e viene illustrato il <xref:System.Windows.Forms.DataGridViewColumn> gerarchia di ereditarietà.  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewColumn.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 Alcuni dei tipi di cella chiave hanno tipi di colonna corrispondenti. Questi sono derivati dal <xref:System.Windows.Forms.DataGridViewColumn> classe di base.  
  
 Nell'elenco seguente vengono illustrate le classi derivate da <xref:System.Windows.Forms.DataGridViewColumn>:  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   I tipi di colonna personalizzata  
  
### <a name="datagridview-editing-controls"></a>Controlli di modifica DataGridView  
 Le celle che supportano le funzionalità avanzate di modifica in genere usano un controllo ospitato che deriva da un controllo Windows Form. Questi controlli implementano anche il <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaccia. Il modello a oggetti seguente viene illustrato l'utilizzo di questi controlli.  
  
 ![Diagramma che mostra la gerarchia del modello oggetto di controllo di modifica DataGridView.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 I seguenti controlli di modifica forniti con il <xref:System.Windows.Forms.DataGridView> controllo:  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Per informazioni sulla creazione di controlli personalizzati di modifica, vedere [come: Inserire controlli in Windows Form celle DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 Nella tabella seguente viene illustrata la relazione tra i tipi di cella, tipi di colonna e i controlli di modifica.  
  
|Tipo di cella|Controllo ospitato|Tipo di colonna|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|N/D|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|N/D|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|N/D|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|N/D|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 Il <xref:System.Windows.Forms.DataGridViewRow> classe visualizza i campi dati di un record dai dati di archivio a cui il <xref:System.Windows.Forms.DataGridView> controllo associato. È possibile accedere la <xref:System.Windows.Forms.DataGridView> righe del controllo utilizzando il <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta. È possibile accedere alle righe selezionate tramite il <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> raccolta. Il modello a oggetti seguente ne illustra l'utilizzo e viene illustrato il <xref:System.Windows.Forms.DataGridViewRow> gerarchia di ereditarietà.  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewRow.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 È possibile derivare tipi personalizzati dal <xref:System.Windows.Forms.DataGridViewRow> classe, anche se ciò in genere non sarà più necessario. Il <xref:System.Windows.Forms.DataGridView> controllo dispone di diversi eventi correlati alla riga e le proprietà per personalizzare il comportamento del relativo <xref:System.Windows.Forms.DataGridViewRow> oggetti.  
  
 Se si abilita il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> viene visualizzata una riga speciale per l'aggiunta di nuove righe di proprietà, come l'ultima riga. Questa riga fa parte di <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta, ma ha funzionalità speciali che potrebbero richiedere attenzione. Per altre informazioni, vedere [usando la riga per i nuovi record nel controllo DataGridView Windows Form](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul controllo DataGridView](datagridview-control-overview-windows-forms.md)
- [Personalizzazione del controllo DataGridView di Windows Form](customizing-the-windows-forms-datagridview-control.md)
- [Uso della riga per i nuovi record del controllo DataGridView di Windows Form](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)

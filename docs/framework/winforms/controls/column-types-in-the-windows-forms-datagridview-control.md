---
title: Tipi di colonna nel controllo DataGridView di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: 6630323b66265f478151ec80ab8b225c0b653917
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Tipi di colonna nel controllo DataGridView di Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo utilizza diversi tipi di colonna per visualizzare le informazioni e consentire agli utenti di modificare o aggiungere informazioni.  
  
 Quando si associa un <xref:System.Windows.Forms.DataGridView> controllo e impostare il <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> proprietà `true`, colonne vengono generate automaticamente in base ai tipi di colonna predefinito appropriati per i tipi di dati contenuti nell'origine dati associata.  
  
 È anche possibile creare manualmente le istanze di una qualsiasi delle classi di colonna e aggiungerli alla raccolta restituita dal <xref:System.Windows.Forms.DataGridView.Columns%2A> proprietà. È possibile creare queste istanze da utilizzare come colonne non associate oppure è possibile associarli manualmente. Le colonne associate manualmente sono utili, ad esempio, quando si desidera sostituire una colonna di un tipo generata automaticamente con una colonna di un altro tipo.  
  
 La tabella seguente descrive le varie classi di colonna disponibili da utilizzare per il <xref:System.Windows.Forms.DataGridView> controllo.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Utilizzato con i valori basati su testo. Generato automaticamente quando si associa a numeri e stringhe.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Utilizzato con <xref:System.Boolean> e <xref:System.Windows.Forms.CheckState> valori. Generato automaticamente durante l'associazione a valori di questi tipi.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Consente di visualizzare immagini. Generato automaticamente durante l'associazione a matrici di byte, <xref:System.Drawing.Image> , oggetti o <xref:System.Drawing.Icon> oggetti.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Consente di visualizzare i pulsanti in celle. Non generata automaticamente durante l'associazione. In genere utilizzate come colonne non associate.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Consente di visualizzare gli elenchi a discesa nelle celle. Non generata automaticamente durante l'associazione. In genere associati a dati manualmente.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Consente di visualizzare i collegamenti nelle celle. Non generata automaticamente durante l'associazione. In genere associati a dati manualmente.|  
|Tipo di colonna personalizzato|È possibile creare la propria classe di colonna tramite l'eredità di <xref:System.Windows.Forms.DataGridViewColumn> classe o una qualsiasi delle classi derivate per fornire un aspetto personalizzato, il comportamento o controlli ospitati. Per altre informazioni, vedere [procedura: personalizzare celle e colonne nel controllo DataGridView Windows Form dall'estensione di comportamento Their e l'aspetto](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Questi tipi di colonna sono descritti più dettagliatamente nelle sezioni seguenti.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 Il <xref:System.Windows.Forms.DataGridViewTextBoxColumn> è un tipo di colonna generica per l'utilizzo con i valori basati su testo, ad esempio stringhe e numeri. In modalità di modifica, un <xref:System.Windows.Forms.TextBox> controllo viene visualizzato nella cella attiva, consentendo agli utenti di modificare il valore della cella.  
  
 I valori delle celle vengono automaticamente convertiti in stringhe per la visualizzazione. I valori immessi o modificati dall'utente vengono analizzati automaticamente per creare un valore di cella del tipo di dati appropriato. È possibile personalizzare queste conversioni gestendo il <xref:System.Windows.Forms.DataGridView.CellFormatting> e <xref:System.Windows.Forms.DataGridView.CellParsing> gli eventi del <xref:System.Windows.Forms.DataGridView> controllo.  
  
 Il tipo di dati di valore di cella di una colonna è incluso il <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> proprietà della colonna.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 Il <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> viene utilizzato con <xref:System.Boolean> e <xref:System.Windows.Forms.CheckState> valori. <xref:System.Boolean> i valori vengono visualizzati come caselle di controllo a due o tre stati in base al valore di <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> proprietà. Quando la colonna è associata a <xref:System.Windows.Forms.CheckState> valori, il <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> valore della proprietà è `true` per impostazione predefinita.  
  
 In genere, i valori di cella di casella di controllo vengono utilizzati per l'archiviazione, come gli altri dati, o per l'esecuzione di operazioni bulk. Se si desidera rispondere immediatamente quando gli utenti di fare clic su una cella di casella di controllo, è possibile gestire il <xref:System.Windows.Forms.DataGridView.CellClick> evento, ma questo evento si verifica prima che il valore della cella viene aggiornato. Se è necessario il nuovo valore al momento della selezione, è possibile calcolare il valore previsto in base al valore corrente. Un altro approccio consiste nell'eseguire immediatamente il commit della modifica e gestire il <xref:System.Windows.Forms.DataGridView.CellValueChanged> eventi per rispondere a esso. Per eseguire il commit della modifica quando la cella è selezionata, è necessario gestire il <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> evento. Nel gestore, se la cella corrente contiene una casella di controllo, chiamare il <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> (metodo) e passare il <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> valore.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 Il <xref:System.Windows.Forms.DataGridViewImageColumn> consente di visualizzare immagini. Colonne di tipo image possono essere popolate automaticamente da un'origine dati, popolate manualmente per le colonne non associate o dinamicamente in un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento.  
  
 La compilazione automatica di una colonna di immagini da un'origine dati funziona con le matrici di byte in una vasta gamma di formati di immagine, inclusi tutti i formati supportati dalla <xref:System.Drawing.Image> classe e il formato di immagine OLE utilizzato da Microsoft® Access e database di esempio Northwind.  
  
 La compilazione di una colonna di tipo image manuale è utile quando si desidera fornire la funzionalità di un <xref:System.Windows.Forms.DataGridViewButtonColumn>, ma con un aspetto personalizzato. È possibile gestire il <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> evento per rispondere alle selezioni nella cella di un'immagine.  
  
 La compilazione delle celle di una colonna di immagine in un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento è utile quando si desidera fornire immagini per i valori calcolati o i valori in formati non di immagine. Ad esempio, è possibile una colonna "A rischio" con valori di stringa, ad esempio `"high"`, `"middle"`, e `"low"` che si desidera visualizzare come icone. In alternativa, potrebbe essere una colonna di "Image" che contiene i percorsi delle immagini che devono essere caricati anziché il contenuto binario delle immagini.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 Con il <xref:System.Windows.Forms.DataGridViewButtonColumn>, è possibile visualizzare una colonna di celle che contengono pulsanti. Ciò è utile quando si desidera fornire un modo semplice per gli utenti di eseguire azioni su un record specifico, ad esempio un ordine di inserimento o la visualizzazione di record figlio in una finestra separata.  
  
 Colonne di pulsanti non vengono generate automaticamente quando l'associazione a dati un <xref:System.Windows.Forms.DataGridView> controllo. Per utilizzare le colonne di pulsanti, è necessario crearle manualmente e aggiungerli alla raccolta restituita dal <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> proprietà.  
  
 È possibile rispondere alle selezioni nelle celle a pulsante gestendo il <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> evento.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 Con il <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, è possibile visualizzare una colonna di celle che contengono le caselle di riepilogo a discesa. Ciò è utile per l'immissione di dati nei campi che possono contenere solo valori particolari, ad esempio la colonna Category della tabella Products nel database di esempio Northwind.  
  
 È possibile popolare l'elenco di riepilogo a discesa usato per tutte le celle nello stesso modo è necessario popolare un <xref:System.Windows.Forms.ComboBox> elenco a discesa, sia manualmente tramite la raccolta restituita dal <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> , proprietà o mediante l'associazione a un'origine dati tramite il <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>, e <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> proprietà. Per ulteriori informazioni, vedere [controllo ComboBox](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md).  
  
 È possibile associare i valori di cella effettivo per l'origine dati utilizzata dal <xref:System.Windows.Forms.DataGridView> controllo impostando il <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> proprietà del <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>.  
  
 Colonne di caselle combinate non vengono generate automaticamente quando l'associazione a dati un <xref:System.Windows.Forms.DataGridView> controllo. Per utilizzare le colonne di casella combinata, è necessario crearle manualmente e aggiungerli alla raccolta restituita dal <xref:System.Windows.Forms.DataGridView.Columns%2A> proprietà.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 Con il <xref:System.Windows.Forms.DataGridViewLinkColumn>, è possibile visualizzare una colonna di celle che contengono collegamenti ipertestuali. Ciò è utile per i valori di URL nell'origine dati o un'alternativa alla colonna di pulsanti per i comportamenti speciali, ad esempio aprendo una finestra con record figlio.  
  
 Le colonne di collegamenti non vengono generate automaticamente quando l'associazione a dati un <xref:System.Windows.Forms.DataGridView> controllo. Per utilizzare le colonne di collegamento, è necessario crearle manualmente e aggiungerli alla raccolta restituita dal <xref:System.Windows.Forms.DataGridView.Columns%2A> proprietà.  
  
 È possibile rispondere alle selezioni dei collegamenti mediante la gestione di <xref:System.Windows.Forms.DataGridView.CellContentClick> evento. Questo evento è diverso da quello di <xref:System.Windows.Forms.DataGridView.CellClick> e <xref:System.Windows.Forms.DataGridView.CellMouseClick> che si verificano quando un utente fa clic in un punto qualsiasi in una cella.  
  
 La <xref:System.Windows.Forms.DataGridViewLinkColumn> classe fornisce diverse proprietà per la modifica dell'aspetto di collegamenti prima, durante e dopo che è stato fatto clic su essi.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewImageColumn>  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewLinkColumn>  
 [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Procedura: visualizzare immagini in celle del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 [Procedura: Usare le colonne di immagini nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)  
 [Personalizzazione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)

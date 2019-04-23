---
title: Tipi di colonna nel controllo DataGridView di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: a33cf4cd865921c04ef10c7fccf3a67c3d22de73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115674"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Tipi di colonna nel controllo DataGridView di Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo utilizza diversi tipi di colonna per visualizzare le informazioni e consentire agli utenti di modificare o aggiungere informazioni.  
  
 Quando si associa un <xref:System.Windows.Forms.DataGridView> controllare e impostare il <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> proprietà `true`, vengono generate automaticamente colonne con tipi di colonna predefiniti appropriati per i tipi di dati contenuti nell'origine dati associata.  
  
 È anche possibile creare manualmente le istanze delle classi di colonna e aggiungerli alla raccolta restituita dal <xref:System.Windows.Forms.DataGridView.Columns%2A> proprietà. È possibile creare queste istanze per l'uso come colonne non associate, oppure è possibile associarli manualmente. Le colonne manualmente associate sono utili, ad esempio, quando si desidera sostituire una colonna generato automaticamente di un tipo con una colonna di un altro tipo.  
  
 La tabella seguente descrive le varie classi di colonne disponibili per l'uso in di <xref:System.Windows.Forms.DataGridView> controllo.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Utilizzato con i valori basati su testo. Generato automaticamente quando si associa a stringhe e numeri.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Utilizzato con <xref:System.Boolean> e <xref:System.Windows.Forms.CheckState> valori. Generato automaticamente quando si associa a valori di questi tipi.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Consente di visualizzare le immagini. Generato automaticamente quando si associa a matrici di byte <xref:System.Drawing.Image> oggetti, o <xref:System.Drawing.Icon> oggetti.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Consente di visualizzare i pulsanti in celle. Generato automaticamente durante l'associazione. In genere utilizzate come colonne non associate.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Consente di visualizzare gli elenchi a discesa nelle celle. Generato automaticamente durante l'associazione. In genere associato a dati manualmente.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Consente di visualizzare i collegamenti nelle celle. Generato automaticamente durante l'associazione. In genere associato a dati manualmente.|  
|Il tipo di colonna personalizzato|È possibile creare la propria classe di colonna tramite l'eredità di <xref:System.Windows.Forms.DataGridViewColumn> classe o una qualsiasi delle relative classi derivate per fornire un aspetto personalizzato, il comportamento o controlli ospitati. Per altre informazioni, vedere [Procedura: Personalizzare celle e colonne nel controllo DataGridView Windows Form estendendone il comportamento e aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Questi tipi di colonna sono descritti più dettagliatamente nelle sezioni seguenti.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 Il <xref:System.Windows.Forms.DataGridViewTextBoxColumn> è un tipo di colonna per utilizzo generico per l'uso con i valori basati su testo, ad esempio stringhe e numeri. In modalità di modifica, un <xref:System.Windows.Forms.TextBox> controllo viene visualizzato nella cella attiva, consentendo agli utenti di modificare il valore della cella.  
  
 I valori delle celle vengono automaticamente convertiti in stringhe per la visualizzazione. I valori immessi o modificati dall'utente vengono analizzati automaticamente per creare un valore di cella di tipo di dati appropriato. È possibile personalizzare queste conversioni gestendo il <xref:System.Windows.Forms.DataGridView.CellFormatting> e <xref:System.Windows.Forms.DataGridView.CellParsing> eventi del <xref:System.Windows.Forms.DataGridView> controllo.  
  
 Il tipo di dati di valore di cella di una colonna viene specificato nel <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> proprietà della colonna.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 Il <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> viene usata con <xref:System.Boolean> e <xref:System.Windows.Forms.CheckState> valori. <xref:System.Boolean> i valori visualizzati come caselle di controllo dello stato di due o tre stati, in base al valore di <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> proprietà. Quando la colonna è associata a <xref:System.Windows.Forms.CheckState> valori, il <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> è il valore di proprietà `true` per impostazione predefinita.  
  
 In genere, i valori di cella di casella di controllo sono progettati per l'archiviazione, come gli altri dati, o per l'esecuzione delle operazioni bulk. Se si desidera rispondere immediatamente quando gli utenti di fare clic su una cella di casella di controllo, è possibile gestire il <xref:System.Windows.Forms.DataGridView.CellClick> evento, ma questo evento si verifica prima dell'aggiornamento del valore della cella. Se è necessario il nuovo valore al momento della selezione, è possibile calcolare qual è il valore previsto in base al valore corrente. Un altro approccio consiste nell'eseguire immediatamente il commit della modifica e gestisce il <xref:System.Windows.Forms.DataGridView.CellValueChanged> eventi per rispondere a esso. Per eseguire il commit della modifica quando si fa clic sulla cella, è necessario gestire il <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> evento. Nel gestore, se la cella corrente è una cella di casella di controllo, chiamare il <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> metodo e passare il <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> valore.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 Il <xref:System.Windows.Forms.DataGridViewImageColumn> consente di visualizzare immagini. Colonne di tipo Image può essere popolati automaticamente da un'origine dati, popolati manualmente per colonne non associate o popolati dinamicamente in un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento.  
  
 Il popolamento automatico di una colonna di immagine da un'origine dati funziona con le matrici di byte in un'ampia gamma di formati di immagine, inclusi tutti i formati supportati dal <xref:System.Drawing.Image> classe e il formato di immagine OLE usati da Microsoft® Access e database di esempio Northwind.  
  
 La compilazione di una colonna di tipo image manuale è utile quando si desidera fornire la funzionalità di un <xref:System.Windows.Forms.DataGridViewButtonColumn>, ma con un aspetto personalizzato. È possibile gestire il <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> eventi per rispondere alle selezioni all'interno di una cella di immagine.  
  
 La compilazione delle celle di una colonna di immagine in un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting> eventi sono utili quando si desidera fornire immagini per i valori calcolati o i valori in formati non di immagine. Ad esempio, si potrebbe essere una colonna con valori di stringa "A rischio", ad esempio `"high"`, `"middle"`, e `"low"` che si desidera visualizzare come le icone. In alternativa, potrebbe essere una colonna di "Image" che contiene i percorsi delle immagini che devono essere caricati anziché il contenuto binario delle immagini.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 Con la <xref:System.Windows.Forms.DataGridViewButtonColumn>, è possibile visualizzare una colonna di celle che contengono pulsanti. Ciò è utile quando si desidera fornire un modo semplice per gli utenti di eseguire azioni sui record specifico, ad esempio un ordine o visualizzare i record figlio in una finestra separata.  
  
 Colonne di pulsanti non vengono generate automaticamente quando l'associazione dati un <xref:System.Windows.Forms.DataGridView> controllo. Per usare le colonne di pulsanti, è necessario crearli manualmente e aggiungerli alla raccolta restituita dal <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> proprietà.  
  
 È possibile rispondere all'interazione dell'utente in celle a pulsante gestendo il <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> evento.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 Con la <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, è possibile visualizzare una colonna di celle che contengono le caselle di riepilogo a discesa. Ciò è utile per l'immissione di dati nei campi che possono includere solo particolari valori, ad esempio la colonna categoria della tabella Products nel database di esempio Northwind.  
  
 È possibile popolare l'elenco di riepilogo a discesa usato per tutte le celle nello stesso modo, potrebbe popolare un <xref:System.Windows.Forms.ComboBox> elenco a discesa, sia manualmente tramite la raccolta restituita dal <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> proprietà, o mediante l'associazione a un'origine dati mediante il <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>, e <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> proprietà. Per altre informazioni, vedere [controllo ComboBox](combobox-control-windows-forms.md).  
  
 È possibile associare i valori di cella effettivo per l'origine dati usata per il <xref:System.Windows.Forms.DataGridView> controllo impostando il <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> proprietà del <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>.  
  
 Le colonne di casella combinata non vengono generate automaticamente quando l'associazione a dati un <xref:System.Windows.Forms.DataGridView> controllo. Per utilizzare le colonne di casella combinata, è necessario crearli manualmente e aggiungerli alla raccolta restituita dal <xref:System.Windows.Forms.DataGridView.Columns%2A> proprietà.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 Con la <xref:System.Windows.Forms.DataGridViewLinkColumn>, è possibile visualizzare una colonna di celle che contengono collegamenti ipertestuali. Ciò è utile per i valori di URL nell'origine dati o come alternativa alla colonna di pulsanti per comportamenti speciali, ad esempio aprendo una finestra con i record figlio.  
  
 Le colonne di collegamenti non vengono generate automaticamente quando l'associazione dati un <xref:System.Windows.Forms.DataGridView> controllo. Per utilizzare le colonne di collegamento, è necessario crearli manualmente e aggiungerli alla raccolta restituita dal <xref:System.Windows.Forms.DataGridView.Columns%2A> proprietà.  
  
 È possibile rispondere all'interazione dell'utente nei collegamenti gestendo il <xref:System.Windows.Forms.DataGridView.CellContentClick> evento. Questo evento è diverso dal <xref:System.Windows.Forms.DataGridView.CellClick> e <xref:System.Windows.Forms.DataGridView.CellMouseClick> eventi che si verificano quando un utente fa clic in qualsiasi punto in una cella.  
  
 Il <xref:System.Windows.Forms.DataGridViewLinkColumn> classe fornisce diverse proprietà per la modifica dell'aspetto dei collegamenti prima, durante e dopo che è stato fatto clic su di essi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewButtonColumn>
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewImageColumn>
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>
- <xref:System.Windows.Forms.DataGridViewLinkColumn>
- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Procedura: Visualizzare immagini in celle del controllo DataGridView Windows Form](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
- [Procedura: Usare le colonne di immagini nel controllo DataGridView Windows Form](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)
- [Personalizzazione del controllo DataGridView di Windows Form](customizing-the-windows-forms-datagridview-control.md)

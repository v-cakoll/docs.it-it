---
title: Scenari del controllo DataGridView (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 7350b0da19650b99bcfd456f93e994492a56d7e3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648100"
---
# <a name="datagridview-control-scenarios-windows-forms"></a>Scenari del controllo DataGridView (Windows Form)
Con la <xref:System.Windows.Forms.DataGridView> (controllo), è possibile visualizzare dati tabulari forniti da un'ampia gamma di origini dati. Per le operazioni semplici, è possibile inserire manualmente un <xref:System.Windows.Forms.DataGridView> e modificare i dati direttamente tramite il controllo. In genere, tuttavia, si verrà archiviano i dati in un'origine dati esterna e associare il controllo tramite un <xref:System.Windows.Forms.BindingSource> componente.  
  
 In questo argomento vengono descritti alcuni scenari comuni che coinvolgono il <xref:System.Windows.Forms.DataGridView> controllo.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>Scenario 1: Visualizzazione di piccole quantità di dati  
 Non è necessario archiviare i dati in un'origine dati esterna per visualizzarlo nel <xref:System.Windows.Forms.DataGridView> controllo. Se si lavora con una piccola quantità di dati, è possibile popolare il controllo se stessi e manipolare i dati tramite il controllo. Questa operazione viene definita *modalità non associata*. Per altre informazioni, vedere [Procedura: Creare un controllo DataGridView di Windows non associato form](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- In modalità non associata, il controllo viene popolato manualmente.  
  
- Modalità non associata è particolarmente adatta per piccole quantità di dati di sola lettura.  
  
- Modalità non associata è adatta anche per le tabelle del foglio di calcolo, ideali per scarsamente popolate.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>Scenario 2: Visualizzare e aggiornare i dati archiviati in un'origine dati esterna  
 È possibile usare il <xref:System.Windows.Forms.DataGridView> controllano come interfaccia utente (UI) tramite cui gli utenti possono accedere ai dati presenti in un'origine dati, ad esempio una tabella di database o una raccolta di oggetti business. Per altre informazioni, vedere [Procedura: Associare i dati per i Windows Form controllo DataGridView](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- Modalità di associazione consente di connettersi a un'origine dati, generare automaticamente colonne basate sulla proprietà dell'origine dati o le colonne del database e popolare automaticamente il controllo.  
  
- Modalità di associazione è adatto per l'interazione dell'utente è intensa con i dati. I dati possono essere formattati per la visualizzazione e i dati specificati dall'utente possono essere analizzati in formato previsto dall'origine dati. Immissione di dati di formattazione degli errori e degli errori di vincolo di database può essere rilevati in modo che gli utenti possono essere avvisati e celle errate possono essere corretti.  
  
- Funzionalità aggiuntive, ad esempio l'ordinamento di colonna, il blocco e il riordinamento consentono agli utenti di visualizzare i dati in modo più idoneo per il flusso di lavoro.  
  
- Supporto per gli Appunti consente agli utenti di copiare i dati dall'applicazione in altre applicazioni.  
  
## <a name="scenario-3-advanced-data"></a>Scenario 3: Dati avanzati  
 Se si hanno esigenze particolari che non si applica il modello di associazione di dati standard, è possibile gestire l'interazione tra il controllo e i dati implementando *modalità virtuale*. È necessaria l'implementazione della modalità virtuale è l'implementazione di uno o più gestori di eventi che consentono le informazioni di richiesta controllo sulle celle come le informazioni.  
  
 Ad esempio, se si lavora con grandi quantità di dati, è possibile implementare modalità virtuale per garantire efficienza ottimale. Modalità virtuale è anche utile per mantenere i valori delle colonne non associate visualizzato insieme a colonne recuperate da un'altra origine dati.  
  
 Per altre informazioni sulla modalità virtuale, vedere [procedura dettagliata: Implementazione della modalità virtuale in Windows il controllo DataGridView form](implementing-virtual-mode-wf-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- Modalità virtuale è adatto per la visualizzazione di grandi quantità di dati quando è necessario ottimizzare le prestazioni.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>Scenario 4: Il ridimensionamento automatico delle righe e colonne  
 Quando si visualizzano i dati che vengono aggiornati regolarmente, è possibile ridimensionare automaticamente le righe e colonne per garantire che tutto il contenuto è visibile. Il <xref:System.Windows.Forms.DataGridView> controllo offre diverse opzioni che consentono di abilitare o disabilitare il ridimensionamento manuale il, ridimensionare a livello di codice in momenti specifici o ridimensionamento automaticamente quando il contenuto cambia. Per altre informazioni, vedere [opzioni di ridimensionamento nel controllo DataGridView Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- Il ridimensionamento manuale consente agli utenti di modificare larghezze e altezze di cella.  
  
- Il ridimensionamento automatico consente di mantenere le dimensioni delle celle in modo che il contenuto di cella non viene mai troncato.  
  
- Il ridimensionamento a livello di codice consente di ridimensionare le celle a orari prestabiliti per evitare la riduzione delle prestazioni di ridimensionamento automatico continua.  
  
## <a name="scenario-5-simple-customization"></a>Scenario 5: Semplice personalizzazione  
 Il <xref:System.Windows.Forms.DataGridView> controllo offre diversi modi per modificare l'aspetto di base e il comportamento. Per altre informazioni, vedere [stili della cella nel controllo DataGridView Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle> gli oggetti consentono di specificare il colore, tipo di carattere, formattazione e posizionamento informazioni a più livelli e per i singoli elementi del controllo.  
  
- Stili della cella possono essere a più livelli e condiviso da più elementi, consentendo il riutilizzo del codice.  
  
## <a name="scenario-6-advanced-customization"></a>Scenario 6: Personalizzazione avanzata  
 Il <xref:System.Windows.Forms.DataGridView> controllo offre diversi modi per personalizzare l'aspetto e comportamento.  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- È possibile fornire il proprio codice di disegno di cella. Per altre informazioni, vedere [Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Form](customize-the-appearance-of-cells-in-the-datagrid.md).  
  
- È possibile fornire il proprio disegno di riga. Ciò è utile, ad esempio, per creare le righe con contenuto che si estende su più colonne. Per altre informazioni, vedere [Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView Windows Form](customize-the-appearance-of-rows-in-the-datagrid.md).  
  
- È possibile implementare le classi di celle e colonne per personalizzare l'aspetto delle celle. Per altre informazioni, vedere [Procedura: Personalizzare celle e colonne in Windows il controllo DataGridView di form estendendone il comportamento e aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
- È possibile implementare le classi di celle e colonne per ospitare i controlli diversi da quelli forniti da tipi di colonna predefiniti. Per altre informazioni, vedere [Procedura: Inserire controlli in Windows Form celle DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Panoramica sul controllo DataGridView](datagridview-control-overview-windows-forms.md)

---
title: Scenari del controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 160d967c6445fb753cb6c73babfb02a734a07e28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742467"
---
# <a name="datagridview-control-scenarios-windows-forms"></a>Scenari del controllo DataGridView (Windows Form)
Con il controllo <xref:System.Windows.Forms.DataGridView> è possibile visualizzare i dati tabulari da diverse origini dati. Per usi semplici, è possibile popolare manualmente un <xref:System.Windows.Forms.DataGridView> e modificare i dati direttamente tramite il controllo. In genere, tuttavia, i dati vengono archiviati in un'origine dati esterna e il controllo viene associato tramite un componente <xref:System.Windows.Forms.BindingSource>.  
  
 In questo argomento vengono descritti alcuni degli scenari comuni che coinvolgono il controllo <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>Scenario 1: visualizzazione di piccole quantità di dati  
 Non è necessario archiviare i dati in un'origine dati esterna per visualizzarli nel controllo <xref:System.Windows.Forms.DataGridView>. Se si lavora con una piccola quantità di dati, è possibile popolare il controllo autonomamente e manipolare i dati tramite il controllo. Questa operazione è denominata *modalità non associata*. Per altre informazioni, vedere [procedura: creare un controllo Windows Forms DataGridView non associato](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- In modalità non associata è necessario popolare il controllo manualmente.  
  
- La modalità non associata è particolarmente indicata per piccole quantità di dati di sola lettura.  
  
- La modalità non associata è inoltre adatta per le tabelle di tipo foglio di calcolo o con popolamento sparse.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>Scenario 2: visualizzazione e aggiornamento dei dati archiviati in un'origine dati esterna  
 È possibile utilizzare il controllo <xref:System.Windows.Forms.DataGridView> come interfaccia utente tramite la quale gli utenti possono accedere ai dati conservati in un'origine dati, ad esempio una tabella di database o una raccolta di oggetti business. Per altre informazioni, vedere [procedura: associare dati al controllo DataGridView Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- La modalità associata consente di connettersi a un'origine dati, generare automaticamente le colonne in base alle proprietà dell'origine dati o alle colonne del database e popolare automaticamente il controllo.  
  
- La modalità associata è adatta per l'interazione utente con i dati. I dati possono essere formattati per la visualizzazione e i dati specificati dall'utente possono essere analizzati nel formato previsto dall'origine dati. È possibile rilevare errori di formattazione dell'immissione dei dati ed errori di vincoli del database in modo che gli utenti possano ricevere avvisi e correggere le celle errate.  
  
- Funzionalità aggiuntive quali l'ordinamento delle colonne, il blocco e il riordino consentono agli utenti di visualizzare i dati nel modo più pratico per il proprio flusso di lavoro.  
  
- Il supporto degli Appunti consente agli utenti di copiare i dati dall'applicazione in altre applicazioni.  
  
## <a name="scenario-3-advanced-data"></a>Scenario 3: dati avanzati  
 Se si hanno esigenze speciali che il modello di data binding standard non è indirizzato, è possibile gestire l'interazione tra il controllo e i dati implementando la *modalità virtuale*. Implementando la modalità virtuale si intende implementare uno o più gestori eventi che consentono al controllo di richiedere informazioni sulle celle, in base alle informazioni necessarie.  
  
 Se, ad esempio, si lavora con grandi quantità di dati, è consigliabile implementare la modalità virtuale per garantire l'efficienza ottimale. La modalità virtuale è utile anche per mantenere i valori delle colonne non associate visualizzate insieme alle colonne recuperate da un'altra origine dati.  
  
 Per ulteriori informazioni sulla modalità virtuale, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- La modalità virtuale è adatta per la visualizzazione di grandi quantità di dati quando è necessario ottimizzare le prestazioni.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>Scenario 4: ridimensionamento automatico di righe e colonne  
 Quando si visualizzano dati aggiornati regolarmente, è possibile ridimensionare automaticamente le righe e le colonne per assicurarsi che tutto il contenuto sia visibile. Il controllo <xref:System.Windows.Forms.DataGridView> offre diverse opzioni che consentono di abilitare o disabilitare il ridimensionamento manuale, ridimensionare a livello di codice a intervalli specifici o ridimensionarsi automaticamente ogni volta che il contenuto viene modificato. Per ulteriori informazioni, vedere [Opzioni di ridimensionamento nel controllo DataGridView Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- Il ridimensionamento manuale consente agli utenti di modificare le altezze e le larghezze delle celle.  
  
- Il ridimensionamento automatico consente di mantenere le dimensioni delle celle, in modo che il contenuto delle celle non venga mai troncato.  
  
- Il ridimensionamento a livello di codice consente di ridimensionare le celle in momenti specifici per evitare la riduzione delle prestazioni del ridimensionamento automatico continuo.  
  
## <a name="scenario-5-simple-customization"></a>Scenario 5: personalizzazione semplice  
 Il controllo <xref:System.Windows.Forms.DataGridView> offre molti modi per modificare l'aspetto e il comportamento di base. Per ulteriori informazioni, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti consentono di fornire informazioni relative a colore, tipo di carattere, formattazione e posizionamento a più livelli e a singoli elementi del controllo.  
  
- Gli stili delle celle possono essere sovrapposti e condivisi da più elementi, consentendo il riutilizzo del codice.  
  
## <a name="scenario-6-advanced-customization"></a>Scenario 6: personalizzazione avanzata  
 Il controllo <xref:System.Windows.Forms.DataGridView> offre molti modi per personalizzare l'aspetto e il comportamento.  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
- È possibile fornire codice personalizzato per il disegno di celle. Per altre informazioni, vedere [procedura: personalizzare l'aspetto delle celle nel controllo DataGridView Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md).  
  
- È possibile specificare un disegno di riga personalizzato. Questa operazione è utile, ad esempio, per creare righe con contenuto che si estende su più colonne. Per altre informazioni, vedere [procedura: personalizzare l'aspetto delle righe nel controllo Windows Forms DataGridView](customize-the-appearance-of-rows-in-the-datagrid.md).  
  
- È possibile implementare classi di celle e colonne personalizzate per personalizzare l'aspetto delle celle. Per altre informazioni, vedere [How to: Customize Cells and Columns nel Windows Forms controllo DataGridView estendendo il comportamento e l'aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
- È possibile implementare classi di celle e colonne personalizzate per ospitare controlli diversi da quelli forniti dai tipi di colonna predefiniti. Per altre informazioni, vedere [How to: Host Controls in Windows Forms celle DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Panoramica sul controllo DataGridView](datagridview-control-overview-windows-forms.md)

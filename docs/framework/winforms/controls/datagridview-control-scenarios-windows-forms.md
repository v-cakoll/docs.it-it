---
title: Scenari del controllo DataGridView (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38e5337f775d98f8729c62b3481c3e839bff2252
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="datagridview-control-scenarios-windows-forms"></a>Scenari del controllo DataGridView (Windows Form)
Con il <xref:System.Windows.Forms.DataGridView> (controllo), è possibile visualizzare dati tabulari forniti da un'ampia gamma di origini dati. Per le operazioni semplici, è possibile inserire manualmente un <xref:System.Windows.Forms.DataGridView> e modificare i dati direttamente tramite il controllo. In genere, tuttavia, si verrà archiviano i dati in un'origine dati esterna e associare il controllo a esso tramite un <xref:System.Windows.Forms.BindingSource> componente.  
  
 In questo argomento vengono descritti alcuni scenari comuni che coinvolgono la <xref:System.Windows.Forms.DataGridView> controllo.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>Scenario 1: Visualizzazione di piccole quantità di dati  
 Non è necessario archiviare i dati in un'origine dati esterna per visualizzarlo nel <xref:System.Windows.Forms.DataGridView> controllo. Se si lavora con una piccola quantità di dati, è possibile popolare il controllo manualmente e modificare i dati tramite il controllo. Si tratta di *modalità non associata*. Per ulteriori informazioni, vedere [procedura: creare un controllo DataGridView di Windows Form non associato](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
-   In modalità non associata, il controllo viene popolato manualmente.  
  
-   Modalità non associata è particolarmente indicata per piccole quantità di dati di sola lettura.  
  
-   Modalità non associata è adatta anche per le tabelle formato foglio di calcolo o scarsamente popolate.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>Scenario 2: Visualizzare e aggiornare i dati archiviati in un'origine dati esterna  
 È possibile utilizzare il <xref:System.Windows.Forms.DataGridView> controllare come un'interfaccia utente (UI) tramite cui gli utenti possono accedere ai dati presenti in un'origine dati, ad esempio una tabella di database o una raccolta di oggetti business. Per ulteriori informazioni, vedere [procedura: associare dati al controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
-   Modalità di associazione consente di connettersi a un'origine dati, generare automaticamente le colonne in base alla proprietà dell'origine dati o le colonne del database e popolare automaticamente il controllo.  
  
-   Modalità di associazione è appropriata per l'interazione con i dati utente è intensa. Per la visualizzazione di dati possono essere formattati e dati utente specificato possono essere analizzati nel formato previsto dall'origine dati. Immissione di dati di formattazione vincolo errori e database può essere rilevati in modo che gli utenti possono essere avvisati e celle errate possono essere corretti.  
  
-   Funzionalità aggiuntive, ad esempio l'ordinamento delle colonne, il blocco e il riordino consentire agli utenti di visualizzare i dati in modo più idoneo per il flusso di lavoro.  
  
-   Supporto per gli Appunti consente agli utenti di copiare i dati dall'applicazione in uso in altre applicazioni.  
  
## <a name="scenario-3-advanced-data"></a>Scenario 3: Avanzata dei dati  
 Se si hanno esigenze particolari che non si applica il modello di associazione dati standard, è possibile gestire l'interazione tra il controllo e i dati mediante l'implementazione *modalità virtuale*. È necessario implementare la modalità virtuale è l'implementazione di uno o più gestori di eventi che consentono il controllo richiesta informazioni sulle celle.  
  
 Ad esempio, se si lavora con grandi quantità di dati, è consigliabile implementare la modalità virtuale per garantire l'efficienza ottimale. Modalità virtuale consente inoltre di mantenere i valori delle colonne visualizzate insieme a colonne recuperati da un'altra origine dati.  
  
 Per ulteriori informazioni sulla modalità virtuale, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
-   Modalità virtuale è adatta per la visualizzazione di grandi quantità di dati quando è necessario ottimizzare le prestazioni.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>Scenario 4: Il ridimensionamento automatico delle righe e colonne  
 Quando si visualizzano i dati che vengono aggiornati periodicamente, è possibile ridimensionare automaticamente le righe e colonne per garantire che tutto il contenuto è visibile. Il <xref:System.Windows.Forms.DataGridView> controllo fornisce diverse opzioni che consentono di abilitare o disabilitare manualmente il ridimensionamento, ridimensionare a livello di codice in momenti specifici o ridimensionare automaticamente quando il contenuto cambia. Per ulteriori informazioni, vedere [opzioni di ridimensionamento nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
-   Ridimensionamento manuale consente agli utenti di modificare larghezze e altezze cella.  
  
-   Il ridimensionamento automatico consente di mantenere le dimensioni delle celle in modo che il contenuto di cella non viene mai troncato.  
  
-   Il ridimensionamento a livello di codice consente di ridimensionare le celle in momenti specifici per evitare la riduzione delle prestazioni di ridimensionamento automatico continua.  
  
## <a name="scenario-5-simple-customization"></a>Scenario 5: Personalizzazione semplice  
 Il <xref:System.Windows.Forms.DataGridView> controllo fornisce molti modi per modificare l'aspetto di base e il comportamento. Per ulteriori informazioni, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>oggetti consentono di specificare il colore, tipo di carattere, la formattazione, le informazioni sul posizionamento a più livelli e per i singoli elementi del controllo.  
  
-   Stili della cella possono essere a più livelli e condiviso da più elementi, consentendo il riutilizzo del codice.  
  
## <a name="scenario-6-advanced-customization"></a>Scenario 6: Personalizzazione avanzata  
 Il <xref:System.Windows.Forms.DataGridView> controllo fornisce molti modi per personalizzare l'aspetto e comportamento.  
  
### <a name="scenario-key-points"></a>Punti chiave dello scenario  
  
-   È possibile fornire il proprio codice di disegno della cella. Per ulteriori informazioni, vedere [procedura: personalizzare l'aspetto di celle nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md).  
  
-   È possibile fornire il proprio disegno di riga. Questo metodo è utile, ad esempio, per creare le righe con contenuto che si estende su più colonne. Per ulteriori informazioni, vedere [procedura: personalizzare l'aspetto delle righe nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md).  
  
-   È possibile implementare le classi di celle e colonne per personalizzare l'aspetto delle celle. Per ulteriori informazioni, vedere [procedura: personalizzare celle e colonne nel controllo DataGridView Windows Form dall'estensione di comportamento relativi e l'aspetto](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
-   È possibile implementare le classi di celle e colonne per i controlli host diversi da quelli forniti dai tipi di colonna predefinito. Per ulteriori informazioni, vedere [come: i controlli Host nelle celle del controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 [Panoramica sul controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)

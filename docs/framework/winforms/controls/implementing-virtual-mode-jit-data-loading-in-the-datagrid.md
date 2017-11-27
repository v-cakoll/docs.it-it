---
title: Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bddac01a0d85ae985b54587619bcac6de5f966f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form
Uno dei motivi per implementare la modalità virtuale nel <xref:System.Windows.Forms.DataGridView> controllo consiste nel recuperare i dati solo quando è necessario. Si tratta di *il caricamento dei dati di just-in-time*.  
  
 Se si lavora con una tabella di dimensioni molto grande in un database remoto, ad esempio, si potrebbe desidera evitare ritardi di avvio recuperando solo i dati necessari per la visualizzazione e il recupero di dati aggiuntivi solo quando l'utente scorre nuove righe all'interno della visualizzazione. Se i computer client che esegue l'applicazione dispongono di una quantità limitata di memoria disponibile per l'archiviazione dei dati, è anche possibile eliminare i dati non utilizzati durante il recupero dei nuovi valori dal database.  
  
 Nelle sezioni seguenti viene descritto come utilizzare un <xref:System.Windows.Forms.DataGridView> controllo con una cache di just-in-time.  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: implementare la modalità virtuale con caricamento dati JIT nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>Il modulo  
 L'esempio di codice seguente definisce un form contenente una proprietà di sola lettura <xref:System.Windows.Forms.DataGridView> controllo che interagisce con un `Cache` mediante un <xref:System.Windows.Forms.DataGridView.CellValueNeeded> gestore dell'evento. Il `Cache` oggetto gestisce i valori archiviati localmente e utilizza un `DataRetriever` oggetto per recuperare i valori della tabella Orders del database Northwind di esempio. Il `DataRetriever` oggetto che implementa il `IDataPageRetriever` interfaccia necessaria per il `Cache` classe, viene anche utilizzato per inizializzare il <xref:System.Windows.Forms.DataGridView> controllo righe e colonne.  
  
 Il `IDataPageRetriever`, `DataRetriever`, e `Cache` tipi sono descritti più avanti in questo argomento.  
  
> [!NOTE]
>  L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>L'interfaccia IDataPageRetriever  
 L'esempio di codice seguente definisce il `IDataPageRetriever` interfaccia viene implementata dalla `DataRetriever` classe. L'unico metodo dichiarato in questa interfaccia è il `SupplyPageOfData` metodo, che richiede un indice di riga iniziale e un conteggio del numero di righe in una singola pagina di dati. Questi valori vengono utilizzati dall'implementatore per recuperare un subset di dati da un'origine dati.  
  
 Oggetto `Cache` oggetto utilizza un'implementazione di questa interfaccia durante la costruzione per caricare due pagine iniziali di dati. Ogni volta che è necessario un valore non memorizzato nella cache, la cache scarta una di queste pagine e richiede una nuova pagina contenente il valore di `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>La classe DataRetriever  
 L'esempio di codice seguente definisce il `DataRetriever` classe che implementa il `IDataPageRetriever` interfaccia per il recupero delle pagine di dati da un server. Il `DataRetriever` classe fornisce anche `Columns` e `RowCount` proprietà, che il <xref:System.Windows.Forms.DataGridView> controllo utilizzato per creare le colonne necessarie e aggiungere il numero appropriato di righe vuote di <xref:System.Windows.Forms.DataGridView.Rows%2A> insieme. Aggiunta di righe vuote è necessaria in modo che il controllo si comporteranno come se contenesse tutti i dati nella tabella. Ciò significa che la casella di scorrimento nella barra di scorrimento avrà le dimensioni appropriate e che l'utente sarà in grado di accedere a qualsiasi riga della tabella. Le righe vengono compilate i <xref:System.Windows.Forms.DataGridView.CellValueNeeded> gestore eventi solo quando lo scorrimento nella visualizzazione.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>La classe di Cache  
 L'esempio di codice seguente definisce il `Cache` (classe), che gestisce due pagine di dati compilate tramite un `IDataPageRetriever` implementazione. Il `Cache` classe definisce un inner `DataPage` struttura, che contiene un <xref:System.Data.DataTable> per archiviare i valori in una cache singola pagina e che calcola gli indici di riga che rappresentano i limiti superiori e inferiori della pagina.  
  
 La `Cache` classe carica due pagine di dati in fase di costruzione. Ogni volta che il <xref:System.Windows.Forms.DataGridView.CellValueNeeded> evento richiede un valore, il `Cache` oggetto determina se il valore è disponibile in una delle due pagine e, in caso affermativo, lo restituisce. Se il valore non è disponibile localmente, il `Cache` oggetto determina quale delle due pagine più righe attualmente visualizzate e la sostituisce con uno nuovo contenente il valore richiesto, il quale viene quindi restituito.  
  
 Supponendo che il numero di righe in una pagina di dati è pari al numero di righe che possono essere visualizzati sullo schermo in una sola volta, questo modello consente agli utenti di paging di una tabella da restituire in modo efficiente per la pagina visualizzata più di recente.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Considerazioni aggiuntive  
 Esempi di codice precedenti vengono forniti come una dimostrazione in fase di caricamento di dati. È necessario modificare il codice per le proprie esigenze ottenere la massima efficienza. Come minimo, è necessario scegliere un valore appropriato per il numero di righe per pagina di dati nella cache. Questo valore viene passato il `Cache` costruttore. Il numero di righe per pagina deve essere non sia minore del numero di righe che possono essere visualizzati contemporaneamente nel <xref:System.Windows.Forms.DataGridView> controllo.  
  
 Per ottenere risultati ottimali, è necessario eseguire il test delle prestazioni e usabilità per determinare i requisiti di sistema e gli utenti. È necessario prendere in considerazione diversi fattori includono la quantità di memoria nei computer client che eseguono l'applicazione, della larghezza di banda della connessione di rete utilizzata e la latenza del server utilizzato. La larghezza di banda e latenza deve essere determinate in momenti di picco.  
  
 Per migliorare le prestazioni di scorrimento dell'applicazione, è possibile aumentare la quantità di dati archiviati in locale. Per migliorare il tempo di avvio, tuttavia, è necessario evitare di caricare troppi dati inizialmente. Si consiglia di modificare la `Cache` classe per aumentare il numero di pagine di dati può archiviare. L'utilizzo di più pagine di dati può migliorare le prestazioni di scorrimento, ma è necessario determinare il numero ideale di righe in una pagina di dati, a seconda della larghezza di banda e latenza del server. Con pagine di dimensioni ridotte, il server di accesso a più di frequente, ma richiederà meno tempo per restituire i dati richiesti. Se la latenza è più un problema di larghezza di banda, si desidera utilizzare le pagine di dati più grande.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Modo virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [Procedura: Implementare la modalità virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)

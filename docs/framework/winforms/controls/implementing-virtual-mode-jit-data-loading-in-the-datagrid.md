---
title: Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form
ms.date: 03/30/2017
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
ms.openlocfilehash: fa40f1657a433f5f4ade3de25648ca04c37dfa67
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962593"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form
Un motivo per implementare la <xref:System.Windows.Forms.DataGridView> modalità virtuale nel controllo consiste nel recuperare i dati solo quando è necessario. Questa operazione viene chiamata *caricamento dati JIT*.  
  
 Se si utilizza una tabella di grandi dimensioni in un database remoto, ad esempio, è possibile evitare ritardi di avvio recuperando solo i dati necessari per la visualizzazione e il recupero di dati aggiuntivi solo quando l'utente scorre le nuove righe nella visualizzazione. Se nei computer client in cui è in esecuzione l'applicazione è disponibile una quantità limitata di memoria per l'archiviazione dei dati, potrebbe essere necessario rimuovere i dati non utilizzati durante il recupero di nuovi valori dal database.  
  
 Le sezioni seguenti descrivono come usare un <xref:System.Windows.Forms.DataGridView> controllo con una cache just-in-time.  
  
 Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Implementare la modalità virtuale con caricamento dati JIT nel Windows Forms controllo](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)DataGridView.  
  
## <a name="the-form"></a>Il modulo  
 Nell'esempio di codice seguente viene definito un form contenente un <xref:System.Windows.Forms.DataGridView> controllo di sola lettura che interagisce con un `Cache` oggetto <xref:System.Windows.Forms.DataGridView.CellValueNeeded> tramite un gestore eventi. L' `Cache` oggetto gestisce i valori archiviati localmente e utilizza un `DataRetriever` oggetto per recuperare i valori dalla tabella Orders del database Northwind di esempio. L' `DataRetriever` oggetto, che implementa l' `IDataPageRetriever` interfaccia richiesta dalla `Cache` classe, viene utilizzato anche per inizializzare le <xref:System.Windows.Forms.DataGridView> righe e le colonne del controllo.  
  
 I `IDataPageRetriever`tipi `DataRetriever`, e`Cache` sono descritti più avanti in questo argomento.  
  
> [!NOTE]
> L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>Interfaccia IDataPageRetriever  
 Nell'esempio `IDataPageRetriever` `DataRetriever` di codice seguente viene definita l'interfaccia implementata dalla classe. L'unico metodo dichiarato in questa interfaccia è il `SupplyPageOfData` metodo, che richiede un indice di riga iniziale e un conteggio del numero di righe in una singola pagina di dati. Questi valori vengono utilizzati dall'implementatore per recuperare un subset di dati da un'origine dati.  
  
 Un `Cache` oggetto usa un'implementazione di questa interfaccia durante la costruzione per caricare due pagine iniziali di dati. Ogni volta che è necessario un valore non memorizzato nella cache, nella cache viene eliminata una di queste pagine e viene richiesta una nuova pagina che `IDataPageRetriever`contiene il valore da.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>Classe DataRetriever  
 Nell'esempio di codice seguente viene `DataRetriever` definita la classe, che `IDataPageRetriever` implementa l'interfaccia per recuperare le pagine di dati da un server. La `DataRetriever` classe fornisce `Columns` inoltre le `RowCount` proprietà e, utilizzate <xref:System.Windows.Forms.DataGridView> dal controllo per creare le colonne necessarie <xref:System.Windows.Forms.DataGridView.Rows%2A> e aggiungere il numero appropriato di righe vuote alla raccolta. L'aggiunta delle righe vuote è necessaria in modo che il controllo si comporti come se contiene tutti i dati nella tabella. Ciò significa che la casella di scorrimento della barra di scorrimento avrà le dimensioni appropriate e l'utente sarà in grado di accedere a qualsiasi riga della tabella. Le righe vengono riempite dal <xref:System.Windows.Forms.DataGridView.CellValueNeeded> gestore eventi solo quando vengono visualizzate.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>Classe cache  
 Nell'esempio di codice seguente viene `Cache` definita la classe, che gestisce due pagine di dati popolate tramite un' `IDataPageRetriever` implementazione. La `Cache` classe definisce una struttura `DataPage` interna, che contiene un <xref:System.Data.DataTable> oggetto per archiviare i valori in una singola pagina della cache e che calcola gli indici di riga che rappresentano i limiti superiore e inferiore della pagina.  
  
 La `Cache` classe carica due pagine di dati in fase di costruzione. Ogni volta <xref:System.Windows.Forms.DataGridView.CellValueNeeded> che l'evento richiede un valore `Cache` , l'oggetto determina se il valore è disponibile in una delle due pagine e, in caso affermativo, lo restituisce. Se il valore non è disponibile localmente, l' `Cache` oggetto determina quale delle due pagine è più lontana dalle righe attualmente visualizzate e sostituisce la pagina con una nuova che contiene il valore richiesto, che viene quindi restituito.  
  
 Supponendo che il numero di righe in una pagina di dati corrisponda al numero di righe che possono essere visualizzate contemporaneamente sullo schermo, questo modello consente agli utenti di eseguire il paging della tabella per tornare in modo efficiente alla pagina visualizzata più di recente.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Considerazioni aggiuntive  
 Gli esempi di codice precedenti vengono forniti come dimostrazione del caricamento di dati JIT. Sarà necessario modificare il codice in base alle proprie esigenze per ottenere la massima efficienza. Come minimo, sarà necessario scegliere un valore appropriato per il numero di righe per pagina di dati nella cache. Questo valore viene passato `Cache` al costruttore. Il numero di righe per pagina deve essere inferiore al numero di righe che possono essere visualizzate contemporaneamente nel <xref:System.Windows.Forms.DataGridView> controllo.  
  
 Per ottenere risultati ottimali, sarà necessario eseguire test delle prestazioni e test di usabilità per determinare i requisiti del sistema e degli utenti. Alcuni fattori che è necessario considerare includono la quantità di memoria nei computer client che eseguono l'applicazione, la larghezza di banda disponibile della connessione di rete utilizzata e la latenza del server utilizzata. La larghezza di banda e la latenza devono essere determinate in momenti di picco sull'utilizzo.  
  
 Per migliorare le prestazioni di scorrimento dell'applicazione, è possibile aumentare la quantità di dati archiviati localmente. Per migliorare il tempo di avvio, tuttavia, è necessario evitare il caricamento iniziale di troppi dati. Potrebbe essere necessario modificare la `Cache` classe per aumentare il numero di pagine di dati che è in grado di archiviare. L'utilizzo di più pagine di dati può migliorare l'efficienza dello scorrimento, ma sarà necessario determinare il numero ideale di righe in una pagina di dati, a seconda della larghezza di banda disponibile e della latenza del server. Con le pagine più piccole, l'accesso al server sarà più frequente, ma il tempo necessario per restituire i dati richiesti sarà inferiore. Se la latenza è maggiore di un problema rispetto alla larghezza di banda, è consigliabile utilizzare pagine di dati di dimensioni maggiori.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Procedura: Implementare la modalità virtuale con caricamento dati JIT nel controllo Windows Forms DataGridView](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)

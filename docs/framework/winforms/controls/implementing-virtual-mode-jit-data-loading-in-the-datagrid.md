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
ms.openlocfilehash: c8290fe7722dba564bf5addab662a9f6b62d924f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607881"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form
Uno dei motivi per implementare la modalità virtuale nel <xref:System.Windows.Forms.DataGridView> controllo consiste nel recuperare i dati solo quando necessario. Questa operazione viene definita *caricamento dei dati just-in-time*.  
  
 Se si lavora con una tabella di dimensioni molto grande in un database remoto, ad esempio, è possibile evitare ritardi di avvio recuperando solo i dati necessari per la visualizzazione e il recupero dei dati aggiuntivi solo quando l'utente scorre nuove righe all'interno della visualizzazione. Se il computer client che eseguono l'applicazione dispone di una quantità limitata di memoria disponibile per l'archiviazione dei dati, è possibile anche rimuovere i dati non usati durante il recupero dei nuovi valori dal database.  
  
 Le sezioni seguenti descrivono come usare un <xref:System.Windows.Forms.DataGridView> controllo con una cache di just-in-time.  
  
 Per copiare il codice in questo argomento come singolo listato, vedere [come: Implementare il modo virtuale con il caricamento dei dati Just-In-Time in di Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>Il modulo  
 L'esempio di codice seguente definisce un modulo che contiene una proprietà di sola lettura <xref:System.Windows.Forms.DataGridView> controllo che interagisce con un `Cache` dell'oggetto tramite un <xref:System.Windows.Forms.DataGridView.CellValueNeeded> gestore dell'evento. Il `Cache` oggetto gestisce i valori archiviati in locale e Usa un `DataRetriever` oggetto per recuperare i valori della tabella Orders del database di esempio Northwind. Il `DataRetriever` oggetto che implementa le `IDataPageRetriever` interfaccia richiesta dal `Cache` classe, viene anche utilizzato per inizializzare il <xref:System.Windows.Forms.DataGridView> controllare le righe e colonne.  
  
 Il `IDataPageRetriever`, `DataRetriever`, e `Cache` tipi sono descritti più avanti in questo argomento.  
  
> [!NOTE]
>  L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>L'interfaccia IDataPageRetriever  
 L'esempio di codice seguente definisce la `IDataPageRetriever` interfaccia, che viene implementato dal `DataRetriever` classe. L'unico metodo dichiarata in questa interfaccia è il `SupplyPageOfData` metodo, che richiede un indice di riga iniziale e un conteggio del numero di righe in una singola pagina di dati. Questi valori vengono usati dalla funzione di implementazione per recuperare un subset di dati da un'origine dati.  
  
 Oggetto `Cache` oggetto usa un'implementazione di questa interfaccia durante la costruzione di caricare due pagine iniziali di dati. Ogni volta che è necessario un valore non memorizzati nella cache, la cache ignora una di queste pagine e richiede una nuova pagina che contiene il valore dal `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>La classe DataRetriever  
 L'esempio di codice seguente definisce la `DataRetriever` classe che implementa il `IDataPageRetriever` interfaccia per recuperare le pagine di dati da un server. Il `DataRetriever` classe fornisce inoltre `Columns` e `RowCount` delle proprietà, che il <xref:System.Windows.Forms.DataGridView> utilizzata dal controllo per creare le colonne necessarie e per aggiungere il numero appropriato di righe vuote nel <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta. Aggiunta di righe vuote è necessaria in modo che il controllo si comporterà come se contenesse tutti i dati nella tabella. Ciò significa che la casella di scorrimento nella barra di scorrimento avranno le dimensioni appropriate e l'utente sarà in grado di accedere a qualsiasi riga della tabella. Le righe vengono compilate i <xref:System.Windows.Forms.DataGridView.CellValueNeeded> gestore dell'evento solo quando lo scorrimento nella visualizzazione.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>La classe della Cache  
 L'esempio di codice seguente definisce la `Cache` (classe), che gestisce due pagine di dati popolati attraverso un `IDataPageRetriever` implementazione. Il `Cache` classe definisce un inner `DataPage` struttura, che contiene un <xref:System.Data.DataTable> per archiviare i valori in una cache singola pagina e che calcola gli indici di riga che rappresentano i limiti superiori e inferiori della pagina.  
  
 Il `Cache` classe carica due pagine di dati in fase di costruzione. Ogni volta che il <xref:System.Windows.Forms.DataGridView.CellValueNeeded> evento richiede un valore, il `Cache` oggetto determina se il valore è disponibile in uno dei due pagine e, in questo caso, lo restituisce. Se il valore non è disponibile in locale, il `Cache` oggetto determina quale delle due pagine più righe attualmente visualizzate e sostituisce la pagina con uno nuovo che contiene il valore richiesto, che viene quindi restituito.  
  
 Supponendo che il numero di righe in una pagina di dati è identico al numero di righe che possono essere visualizzati sullo schermo in una sola volta, questo modello consente agli utenti di paging attraverso la tabella in modo efficiente tornare alla pagina visualizzata più di recente.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Considerazioni aggiuntive  
 Esempi di codice precedenti vengono forniti come una dimostrazione del caricamento dei dati just-in-time. È necessario modificare il codice per le proprie esigenze ottenere la massima efficienza. Come minimo, è necessario scegliere un valore appropriato per il numero di righe per pagina di dati nella cache. Questo valore viene passato il `Cache` costruttore. Il numero di righe per pagina deve essere non sia minore del numero di righe che possono essere visualizzati contemporaneamente nel <xref:System.Windows.Forms.DataGridView> controllo.  
  
 Per ottenere risultati ottimali, è necessario eseguire test di prestazioni e usabilità per determinare i requisiti di sistema e gli utenti. È necessario prendere in considerazione diversi fattori includono la quantità di memoria nei computer client che eseguono l'applicazione, la larghezza di banda disponibile della connessione di rete utilizzata e la latenza del server utilizzato. La larghezza di banda e latenza che deve essere determinati in momenti di picco.  
  
 Per migliorare le prestazioni di scorrimento dell'applicazione, è possibile aumentare la quantità di dati archiviati in locale. Per migliorare i tempi di avvio, tuttavia, è necessario evitare il caricamento di quantità eccessive di dati inizialmente. È possibile modificare il `Cache` classe per aumentare il numero di pagine di dati può archiviare. L'uso di più pagine di dati può migliorare le prestazioni di scorrimento, ma sarà necessario determinare il numero ideale di righe in una pagina di dati, a seconda della larghezza di banda disponibile e la latenza del server. Con pagine di dimensioni ridotte, il server si accederà più frequentemente, ma richiederà meno tempo per restituire i dati richiesti. Se la latenza è più un problema di larghezza di banda, è possibile usare le pagine di dati più grande.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
- [Procedura: Implementazione del modo virtuale con caricamento dati Just-In-Time nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)

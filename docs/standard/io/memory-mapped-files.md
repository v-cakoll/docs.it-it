---
title: File mappati alla memoria
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- memory-mapped files
- inter-process communication
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
ms.openlocfilehash: 7d80099fcfcba58cd863004ba7faf0bafa3abd09
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628020"
---
# <a name="memory-mapped-files"></a>File mappati alla memoria
Un file mappato alla memoria include il contenuto di un file nella memoria virtuale. Questo mapping tra un file e uno spazio di memoria consente a un'applicazione, inclusi più processi, di modificare il file leggendo e scrivendo direttamente nella memoria. A partire da NET Framework 4, è possibile usare il codice gestito per accedere ai file mappati alla memoria nello stesso modo in cui le funzioni Windows native accedono ai file mappati alla memoria, come descritto in [Managing Memory-Mapped Files](https://docs.microsoft.com/previous-versions/ms810613(v=msdn.10)) (Gestione di file mappati alla memoria).  
  
 Esistono due tipi di file di cui è stato eseguito il mapping alla memoria:  
  
- File persistenti di cui è stato eseguito il mapping alla memoria  
  
     I file persistenti sono file di cui è stato eseguito il mapping alla memoria associati a un file di origine su un disco. Quando l'ultimo processo ha terminato di usare il file, i dati vengono salvati nel file di origine sul disco. Questi file di cui è stato eseguito il mapping alla memoria sono adatti per usare file di origine di dimensioni molto grandi.  
  
- File non persistenti di cui è stato eseguito il mapping alla memoria  
  
     I file non persistenti sono file di cui è stato eseguito il mapping alla memoria non associati a un file su un disco. Quando l'ultimo processo ha terminato di usare il file, i dati vanno persi e il file viene recuperato dalla Garbage Collection. Questi file sono adatti per la creazione di memoria condivisa per le comunicazioni interprocesso (IPC).  
  
## <a name="processes-views-and-managing-memory"></a>Processi, visualizzazioni e gestione della memoria  
 I file di cui è stato eseguito il mapping alla memoria non possono essere condivisi tra più processi. I processi possono eseguire il mapping allo stesso file di cui è stato eseguito il mapping alla memoria usando un nome comune assegnato dal processo che ha creato il file.  
  
 Per usare un file di cui è stato eseguito il mapping alla memoria, è necessario creare una visualizzazione dell'intero file di cui è stato eseguito il mapping alla memoria o di una parte. È anche possibile creare più visualizzazioni alla stessa parte del file di cui è stato eseguito il mapping alla memoria, creando quindi una memoria simultanea. Per rimanere simultanee, due visualizzazioni devono essere create dallo stesso file di cui è stato eseguito il mapping alla memoria.  
  
 Potrebbero essere necessarie più visualizzazioni anche se le dimensioni del file sono superiori a quelle dello spazio di memoria logica dell'applicazione disponibile per il mapping alla memoria (2 GB in un computer a 32 bit).  
  
 Esistono due tipi di visualizzazioni: visualizzazione di accesso a flusso e visualizzazione di accesso casuale. Usare le visualizzazioni di accesso a flusso per l'accesso sequenziale a un file. Questa opzione è consigliata per i file non persistenti e la comunicazione interprocesso. Le visualizzazioni di accesso casuale sono preferibili per l'uso di file persistenti.  
  
 I file di cui è stato eseguito il mapping alla memoria sono accessibili tramite il gestore della memoria del sistema operativo, in modo che il file venga automaticamente partizionato in un numero di pagine e sia accessibile se necessario. Non è necessario occuparsi personalmente della gestione della memoria.  
  
 La figura seguente illustra come più processi possono avere contemporaneamente più visualizzazioni sovrapposte per lo stesso file di cui è stato eseguito il mapping alla memoria.

 L'immagine seguente illustra più visualizzazioni sovrapposte per un file di cui è stato eseguito il mapping alla memoria:  
  
 ![Screenshot che illustra le visualizzazioni per un file di cui è stato eseguito il mapping alla memoria.](./media/memory-mapped-files/memory-map-persist-file.png)  
  
## <a name="programming-with-memory-mapped-files"></a>Programmazione con i file di cui è stato eseguito il mapping alla memoria  
 La tabella seguente fornisce una guida all'uso di oggetti di file di cui è stato eseguito il mapping alla memoria e dei relativi membri.  
  
|Attività|Metodi o proprietà da usare|  
|----------|----------------------------------|  
|Ottenere un oggetto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> che rappresenta un file persistente di cui è stato eseguito il mapping alla memoria da un file su disco.|Metodo<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> .|  
|Ottenere un oggetto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> che rappresenta un file non persistente di cui è stato eseguito il mapping alla memoria (non associato a un file su disco).|Metodo<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> .<br /><br /> - oppure -<br /><br /> Metodo<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> .|  
|Ottenere un oggetto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> di un file esistente di cui è stato eseguito il mapping alla memoria (persistente o non persistente).|Metodo<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> .|  
|Ottenere un oggetto <xref:System.IO.UnmanagedMemoryStream> per una visualizzazione accessibile in sequenza per il file di cui è stato eseguito il mapping alla memoria.|Metodo<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> .|  
|Ottenere un oggetto <xref:System.IO.UnmanagedMemoryAccessor> per una visualizzazione di accesso casuale per un file di cui è stato eseguito il mapping alla memoria.|Metodo<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> .|  
|Ottenere un oggetto <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> da usare con il codice non gestito.|Proprietà <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.<br /><br /> - oppure -<br /><br /> Proprietà <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.<br /><br /> - oppure -<br /><br /> Proprietà <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.|  
|Ritardare l'allocazione della memoria finché non viene creata una visualizzazione (solo file non persistenti).<br /><br /> Per determinare la dimensione di paging del sistema corrente, usare la proprietà <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>.|Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> con il valore <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>.<br /><br /> - oppure -<br /><br /> Metodi <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> che hanno un'enumerazione <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> come parametro.|  
  
### <a name="security"></a>Sicurezza  
 È possibile applicare i diritti di accesso quando si crea un file di cui è stato eseguito il mapping alla memoria, usando i metodi seguenti che accettano un'enumerazione <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> come parametro:  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 È possibile specificare i diritti di accesso per l'apertura di un file esistente di cui è stato eseguito il mapping alla memoria usando i metodi <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> che accettano <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> come parametro.  
  
 È anche possibile includere un oggetto <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> che contiene le regole di accesso predefinite.  
  
 Per applicare regole di accesso nuove o modificate a un file di cui è stato eseguito il mapping alla memoria, usare il metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>. Per recuperare le regole di accesso o controllo da un file esistente, usare il metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>.  
  
## <a name="examples"></a>Esempi  
  
### <a name="persisted-memory-mapped-files"></a>File persistenti di cui è stato eseguito il mapping alla memoria  
 I metodi <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> creano un file di cui viene eseguito il mapping alla memoria da un file esistente su disco.  
  
 L'esempio seguente crea una visualizzazione di cui viene eseguito il mapping alla memoria di una parte di un file molto grande e ne modifica una parte.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
 
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

 L'esempio seguente apre lo stesso file di cui è stato eseguito il mapping alla memoria per un altro processo.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a>File non persistenti di cui è stato eseguito il mapping alla memoria  
 I metodi <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> e <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> creano un file di cui viene eseguito il mapping alla memoria del quale non viene eseguito il mapping a un file esistente su disco.  
  
 L'esempio seguente è costituito da tre processi separati (applicazioni console) che scrivono i valori booleani in un file di cui è stato eseguito il mapping alla memoria. Si verifica la sequenza di azioni seguente:  
  
1. `Process A` crea il file di cui viene eseguito il mapping alla memoria e vi scrive un valore.  
  
2. `Process B` apre il file di cui è stato eseguito il mapping alla memoria e vi scrive un valore.  
  
3. `Process C` apre il file di cui è stato eseguito il mapping alla memoria e vi scrive un valore.  
  
4. `Process A` legge e visualizza i valori dal file di cui è stato eseguito il mapping alla memoria.  
  
5. Dopo che `Process A` è terminato con il file di cui è stato eseguito il mapping alla memoria, il file viene immediatamente recuperato dalla Garbage Collection.  
  
 Per eseguire questo esempio, seguire questa procedura:  
  
1. Compilare le applicazioni e aprire tre finestre del prompt dei comandi.  
  
2. Nella prima finestra del prompt dei comandi eseguire `Process A`.  
  
3. Nella seconda finestra del prompt dei comandi eseguire `Process B`.  
  
4. Tornare a `Process A` e premere INVIO.  
  
5. Nella terza finestra del prompt dei comandi eseguire `Process C`.  
  
6. Tornare a `Process A` e premere INVIO.  
  
 L'output di `Process A` è indicato di seguito:  
  
```console  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 **Process A**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 **Process B**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 **Process C**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [I/O di file e di flussi](../../../docs/standard/io/index.md)

---
title: File mappati alla memoria
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- memory-mapped files
- inter-process communiation
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
caps.latest.revision: "24"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2602d431aada7b3e0ee226eed319903492022ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="memory-mapped-files"></a>File mappati alla memoria
Un file mappato alla memoria include il contenuto di un file nella memoria virtuale. Questo mapping tra uno spazio di memoria e di file consente a un'applicazione, con più processi modificare il file da leggere e scrivere direttamente alla memoria. A partire dal [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile utilizzare codice gestito per accedere ai file mappati alla memoria nello stesso modo che le funzioni Windows native accedere ai file mappati alla memoria, come descritto in [gestione di file Win32](http://go.microsoft.com/fwlink/?linkid=180801).  
  
 Esistono due tipi di file mappati alla memoria:  
  
-   File mappato alla memoria persistenti  
  
     File persistenti sono file mappato alla memoria associati a un file di origine in un disco. Quando l'ultimo processo ha completato l'utilizzo con il file, i dati vengono salvati nel file di origine sul disco. Questi file mappato alla memoria sono adatti per l'utilizzo di file di origine molto elevata.  
  
-   File mappato alla memoria non persistenti  
  
     File persistenti non sono file mappati alla memoria non sono associati a un file su disco. Quando l'ultimo processo ha completato l'utilizzo con il file, i dati vengono persi e il file viene recuperato da garbage collection. Questi file sono adatti per la creazione di memoria condivisa per le comunicazioni interprocesso (IPC).  
  
## <a name="processes-views-and-managing-memory"></a>Processi, viste e gestione della memoria  
 File mappato alla memoria possono essere condivisi tra più processi. Processi possono eseguire il mapping allo stesso file mappato alla memoria utilizzando un nome comune che viene assegnato dal processo di cui è stato creato.  
  
 Per utilizzare un file mappato alla memoria, è necessario creare una visualizzazione dell'intero file mappato alla memoria o una parte di esso. È inoltre possibile creare più visualizzazioni alla stessa parte del file mappato alla memoria, in modo da creare memoria simultanea. Per le due viste rimangano simultanee, devono essere creati dallo stesso file mappato alla memoria.  
  
 Visualizzazioni multiple potrebbero inoltre essere necessarie se il file è maggiore della dimensione dello spazio di memoria logica dell'applicazione disponibile per il mapping (2 GB in un computer a 32 bit) di memoria.  
  
 Esistono due tipi di visualizzazioni: visualizzazione di accesso e visualizzazione di accesso casuale di flusso. Utilizzare le visualizzazioni di accesso di flusso per l'accesso sequenziale in un file. Questa è consigliata per i file non persistenti e IPC. Le visualizzazioni ad accesso casuale sono preferibili per l'utilizzo dei file persistenti.  
  
 File mappati alla memoria sono accessibili tramite il gestore di memoria del sistema operativo, in modo che il file viene automaticamente partizionato in un numero di pagine e accedere in base alle esigenze. Non è necessario gestire personalmente la gestione della memoria.  
  
 La figura seguente mostra come più processi possono avere più e sovrapposti viste nello stesso file mappato alla memoria nello stesso momento.  
  
 ![Mostra visualizzazioni a una memoria &#45; il file mappato. ] (../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")  
Più e sovrapposte viste in un file mappato alla memoria  
  
## <a name="programming-with-memory-mapped-files"></a>Programmazione con i file mappati alla memoria  
 Nella tabella seguente viene fornita una Guida per l'utilizzo di oggetti del file mappato alla memoria e i relativi membri.  
  
|Attività|Metodi o proprietà da utilizzare|  
|----------|----------------------------------|  
|Per ottenere un <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> oggetto che rappresenta un file mappato alla memoria persistente da un file su disco.|Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>.|  
|Per ottenere un <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> oggetto che rappresenta un file mappato alla memoria non persistente (non associato a un file su disco).|Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>.<br /><br /> -oppure-<br /><br /> Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>.|  
|Per ottenere un <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> oggetto di un file mappato alla memoria esistente (persistente o non persistente).|Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType>.|  
|Per ottenere un <xref:System.IO.UnmanagedMemoryStream> oggetto per una visualizzazione in sequenza a cui si accede al file mappato alla memoria.|Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType>.|  
|Per ottenere un <xref:System.IO.UnmanagedMemoryAccessor> dell'oggetto per una visualizzazione ad accesso casuale mappato alla memoria dannoso.|Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType>.|  
|Per ottenere un <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> oggetto da usare con codice non gestito.|Proprietà <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.<br /><br /> -oppure-<br /><br /> Proprietà <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.<br /><br /> -oppure-<br /><br /> Proprietà <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.|  
|Per ritardare l'allocazione della memoria fino a una vista viene creata (solo file di non persistente).<br /><br /> (Per determinare le dimensioni della pagina corrente del sistema, utilizzare il <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> proprietà.)|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>metodo con il <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> valore.<br /><br /> -oppure-<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>metodi che presentano un <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumerazione come parametro.|  
  
### <a name="security"></a>Sicurezza  
 È possibile applicare i diritti di accesso quando si crea un file mappato alla memoria, utilizzando i metodi seguenti che accettano un <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumerazione come parametro:  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 È possibile specificare i diritti di accesso per l'apertura di un file mappato alla memoria esistente utilizzando il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> metodi che accettano un <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> come parametro.  
  
 Inoltre, è possibile includere un <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> oggetto che contiene le regole di accesso predefinito.  
  
 Per applicare le regole di accesso nuove o modificate in un file mappato alla memoria, utilizzare il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> metodo. Per recuperare l'accesso o controllare le regole da un file esistente, utilizzare il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> metodo.  
  
## <a name="examples"></a>Esempi  
  
### <a name="persisted-memory-mapped-files"></a>File mappato alla memoria persistenti  
 Il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> metodi creano un file mappato alla memoria da un file esistente sul disco.  
  
 Nell'esempio seguente viene creata una visualizzazione mappato alla memoria di una parte di un file molto grande e modifica di una parte di esso.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 Nell'esempio seguente viene aperto lo stesso file mappato alla memoria per un altro processo.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a>File mappato alla memoria non persistenti  
 Il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> e <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> metodi consentono di creare un file mappato alla memoria non è mappato a un file esistente sul disco.  
  
 Nell'esempio seguente è costituito da tre processi separati (applicazioni console) che scrivono i valori booleani in un file mappato alla memoria. Si verifica la sequenza di azioni seguente:  
  
1.  `Process A`Crea il file mappato alla memoria e scrive un valore.  
  
2.  `Process B`Apre il file mappato alla memoria e scrive un valore.  
  
3.  `Process C`Apre il file mappato alla memoria e scrive un valore.  
  
4.  `Process A`legge e visualizza i valori del file mappato alla memoria.  
  
5.  Dopo aver `Process A` è terminato con il file mappato alla memoria, il file viene immediatamente recuperato tramite garbage collection.  
  
 Per eseguire questo esempio, eseguire le operazioni seguenti:  
  
1.  Compilare le applicazioni e aprire tre finestre prompt dei comandi.  
  
2.  Nella prima finestra prompt dei comandi, eseguire `Process A`.  
  
3.  Nella seconda finestra prompt dei comandi, eseguire `Process B`.  
  
4.  Tornare alla `Process A` e premere INVIO.  
  
5.  Nella terza finestra prompt dei comandi, eseguire `Process C`.  
  
6.  Tornare alla `Process A` e premere INVIO.  
  
 L'output di `Process A` è indicato di seguito:  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 **Processo**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 **Processo B**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 **Processo C**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)

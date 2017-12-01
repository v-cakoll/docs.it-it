---
title: 'Procedura dettagliata: utilizzo di BatchBlock e BatchedJoinBlock per migliorare l''efficienza'
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
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc74b4acc5b29395c05e7c8302caefeb51718282
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a>Procedura dettagliata: utilizzo di BatchBlock e BatchedJoinBlock per migliorare l'efficienza
La libreria del flusso di dati TPL fornisce la <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> classi in modo che è possibile ricevere e buffer di dati da una o più origini e quindi vengono propagati all'esterno come una raccolta di dati memorizzati nel buffer. Questo meccanismo di batch è utile quando si raccolgono dati da una o più origini e quindi elaborare più elementi di dati come un batch. Ad esempio, si consideri un'applicazione che utilizza i flussi di dati per inserire i record in un database. Questa operazione può essere più efficiente se più elementi vengono inseriti nello stesso momento anziché uno alla volta, in modo sequenziale. Questo documento viene descritto come utilizzare il <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> operazioni di inserimento di classe per migliorare l'efficienza di tale database. Viene inoltre descritto come utilizzare la <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> classe per acquisire i risultati e tutte le eccezioni che si verificano quando il programma legge da un database.  
  
> [!TIP]
>  La libreria del flusso di dati TPL (spazio dei nomi <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) non viene distribuita con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Per installare il <xref:System.Threading.Tasks.Dataflow> dello spazio dei nomi, Apri il progetto in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], scegliere **Gestisci pacchetti NuGet** dal menu progetto e cercare online il `Microsoft.Tpl.Dataflow` pacchetto.  
  
## <a name="prerequisites"></a>Prerequisiti  
  
1.  Leggere la sezione di blocchi Join nel [flussi di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) documento prima di iniziare questa procedura dettagliata.  
  
2.  Verificare di disporre di una copia del database Northwind, sdf, disponibile nel computer. Questo file si trova in genere nella cartella % Files%\Microsoft SQL Server Compact Edition\v3.5\Samples.\\.  
  
    > [!IMPORTANT]
    >  In alcune versioni di Windows, è possibile connettersi a sdf se [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] è in esecuzione in modalità senza privilegi di amministratore. Per connettersi a sdf, avviare [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] prompt dei comandi nel **Esegui come amministratore** modalità.  
  
 Questa procedura dettagliata contiene le sezioni seguenti:  
  
-   [Creazione dell'applicazione Console](#creating)  
  
-   [Definizione della classe dipendente](#employeeClass)  
  
-   [Definizione di operazioni di Database di dipendenti](#operations)  
  
-   [Aggiunta di dati dipendenti al Database senza l'utilizzo del buffer](#nonBuffering)  
  
-   [Utilizzo del buffer per aggiungere i dati dei dipendenti nel database](#buffering)  
  
-   [Utilizzando Join memorizzato nel buffer per leggere i dati dei dipendenti dal Database](#bufferedJoin)  
  
-   [Esempio completo](#complete)  
  
<a name="creating"></a>   
## <a name="creating-the-console-application"></a>Creazione dell'applicazione Console  
  
<a name="consoleApp"></a>   
1.  In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], creare un Visual c# o Visual Basic **applicazione Console** progetto. In questo documento, il progetto viene denominato `DataflowBatchDatabase`.  
  
2.  Nel progetto, aggiungere un riferimento a System.Data.SqlServerCe.dll e un riferimento a System.Threading.Tasks.Dataflow.dll.  
  
3.  Verificare che in Form1.cs (Form1. vb per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contiene quanto segue `using` (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) le istruzioni.  
  
     [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
     [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]  
  
4.  Aggiungere i membri dei dati seguenti alla classe `Program`.  
  
     [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
     [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]  
  
<a name="employeeClass"></a>   
## <a name="defining-the-employee-class"></a>Definizione della classe dipendente  
 Aggiungere il `Program` classe il `Employee` classe.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
 [!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]  
  
 Il `Employee` classe contiene tre proprietà, `EmployeeID`, `LastName`, e `FirstName`. Queste proprietà corrispondono al `Employee ID`, `Last Name`, e `First Name` colonne il `Employees` tabella nel database Northwind. Per questa dimostrazione, il `Employee` classe definisce inoltre il `Random` metodo, che crea un `Employee` oggetto con valori casuali per le relative proprietà.  
  
<a name="operations"></a>   
## <a name="defining-employee-database-operations"></a>Definizione di operazioni di Database di dipendenti  
 Aggiungere il `Program` classe il `InsertEmployees`, `GetEmployeeCount`, e `GetEmployeeID` metodi.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
 [!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]  
  
 Il `InsertEmployees` metodo aggiunge nuovi record employee nel database. Il `GetEmployeeCount` metodo recupera il numero di voci di `Employees` tabella. Il `GetEmployeeID` che consente di recuperare l'identificatore del primo dipendente che ha il nome fornito. Ognuno di questi metodi accetta una stringa di connessione al database Northwind e utilizza la funzionalità nel `System.Data.SqlServerCe` dello spazio dei nomi per comunicare con il database.  
  
<a name="nonBuffering"></a>   
## <a name="adding-employee-data-to-the-database-without-using-buffering"></a>Aggiunta di dati dipendenti al Database senza l'utilizzo del buffer  
 Aggiungere il `Program` classe il `AddEmployees` e `PostRandomEmployees` metodi.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
 [!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]  
  
 Il `AddEmployees` metodo aggiunge i dati dei dipendenti casuali al database utilizzando i flussi di dati. Crea un <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> che chiama il `InsertEmployees` metodo per aggiungere una voce di dipendente per il database. Il `AddEmployees` chiama quindi il `PostRandomEmployees` metodo per registrare più `Employee` oggetti per il <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> oggetto. Il `AddEmployees` metodo attende quindi per tutte le operazioni al fine di inserimento.  
  
<a name="buffering"></a>   
## <a name="using-buffering-to-add-employee-data-to-the-database"></a>Utilizzo del buffer per aggiungere i dati dei dipendenti nel database  
 Aggiungere il `Program` classe il `AddEmployeesBatched` metodo.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
 [!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]  
  
 Questo metodo è simile a `AddEmployees`, ad eccezione del fatto che viene utilizzato anche il <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> classe per memorizzare nel buffer più `Employee` oggetti prima dell'invio di tali oggetti per il <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> oggetto. Poiché il <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> classe propaga più elementi come una raccolta, il <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> oggetto viene modificato per funzionare su una matrice di `Employee` oggetti. Come nel `AddEmployees` (metodo), `AddEmployeesBatched` chiamate il `PostRandomEmployees` metodo per registrare più `Employee` oggetti; tuttavia, `AddEmployeesBatched` invia questi oggetti per il <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> oggetto. Il `AddEmployeesBatched` metodo attende inoltre che tutte le operazioni al fine di inserimento.  
  
<a name="bufferedJoin"></a>   
## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a>Utilizzando Join memorizzato nel buffer per leggere i dati dei dipendenti dal Database  
 Aggiungere il `Program` classe il `GetRandomEmployees` metodo.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
 [!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]  
  
 Questo metodo visualizza informazioni sui dipendenti casuali nella console. Crea più casuale `Employee` oggetti e le chiamate di `GetEmployeeID` metodo per recuperare l'identificatore univoco per ogni oggetto. Poiché il `GetEmployeeID` metodo genera un'eccezione se nessun dipendente corrispondenti con nomi e cognomi specificati, il `GetRandomEmployees` metodo utilizza il <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> classe per archiviare `Employee` oggetti per le chiamate con esito positivo per `GetEmployeeID` e <xref:System.Exception?displayProperty=nameWithType> oggetti per le chiamate che non riescono. Il <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> oggetto in questo esempio agisce su un <xref:System.Tuple%602> oggetto che contiene un elenco di `Employee` oggetti e un elenco di <xref:System.Exception> oggetti. Il <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> oggetto propaga questi dati quando la somma della classe ricevuta `Employee` e <xref:System.Exception> il numero di oggetti è uguale alla dimensione di batch.  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a>Esempio completo  
 L'esempio seguente mostra il codice completo. Il `Main` metodo confronta il tempo necessario per eseguire le operazioni di inserimento in batch di database rispetto al tempo per eseguire le operazioni di inserimento del database non in batch. Viene inoltre illustrato l'utilizzo di join memorizzato nel buffer per leggere i dati dei dipendenti dal database e anche la segnalazione errori.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
 [!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]  
  
## <a name="see-also"></a>Vedere anche  
 [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)

---
title: "Procedura dettagliata: utilizzo di BatchBlock e BatchedJoinBlock per migliorare l'efficienza"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
ms.openlocfilehash: 4b2b6a6124bf8cc0fb3b379607135283678e3268
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091353"
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a>Procedura dettagliata: utilizzo di BatchBlock e BatchedJoinBlock per migliorare l'efficienza

La libreria del flusso di dati TPL fornisce le classi <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> che consentono di ricevere e memorizzare nel buffer i dati di una o più origini e quindi propagare tali dati come unica raccolta. Questo meccanismo di invio in batch è utile quando si raccolgono dati da una o più origini e quindi si elaborano più elementi dati come batch. Ad esempio, si consideri un'applicazione che usa un flusso di dati per inserire record in un database. Questa operazione può essere più efficiente se nello stesso momento vengono inseriti più elementi anziché uno alla volta, in modo sequenziale. Questo documento descrive come usare la classe <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> per migliorare l'efficienza di tali operazioni di inserimento nel database. Descrive anche come usare la classe <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> per acquisire sia i risultati che le eventuali eccezioni che si verificano durante la lettura da database da parte del programma.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="prerequisites"></a>Prerequisites

1. Prima di iniziare questa procedura dettagliata, leggere la sezione sui blocchi join nel documento [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).

2. Verificare di avere una copia del database Northwind, Northwind.sdf, disponibile nel computer. Questo file si trova in genere nella cartella %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.

    > [!IMPORTANT]
    > In alcune versioni di Windows non è possibile connettersi a Northwind.sdf se Visual Studio è in esecuzione in modalità senza privilegi di amministratore. Per connettersi a Northwind.sdf, avviare Visual Studio o un Prompt dei comandi per gli sviluppatori per Visual Studio in modalità **Esegui come amministratore**.

Questa procedura dettagliata contiene le sezioni seguenti:

- [Creazione dell'applicazione console](#creating)

- [Definizione della classe Employee](#employeeClass)

- [Definizione delle operazioni dei dipendenti sul database](#operations)

- [Aggiunta di dati dei dipendenti al database senza utilizzare il bufferingAdding Employee Data to the Database without Using Buffering](#nonBuffering)

- [Uso della memorizzazione nel buffer per aggiungere dati dei dipendenti nel database](#buffering)

- [Uso di un join memorizzato nel buffer per leggere dati dei dipendenti dal database](#bufferedJoin)

- [Esempio completo](#complete)

<a name="creating"></a>

## <a name="creating-the-console-application"></a>Creazione dell'applicazione console

1. In Visual Studio creare un progetto **di applicazione console** di Visual C. In questo documento, il progetto viene denominato `DataflowBatchDatabase`.

2. Nel progetto aggiungere un riferimento a System.Data.SqlServerCe.dll e un riferimento a System.Threading.Tasks.Dataflow.dll.

3. Assicurarsi che in Form1.cs (Form1.vb per Visual Basic) siano contenute le seguenti istruzioni `using` (`Imports` in Visual Basic).

    [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
    [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]

4. Aggiungere i membri dei dati seguenti alla classe `Program`.

    [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
    [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]

<a name="employeeClass"></a>

## <a name="defining-the-employee-class"></a>Definizione della classe Employee

Aggiungere alla classe `Program` la classe `Employee`.

[!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
[!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]

La classe `Employee` contiene tre proprietà, `EmployeeID`, `LastName` e `FirstName`. Queste proprietà corrispondono alle colonne `Employee ID`, `Last Name` e `First Name` nella tabella `Employees` del database Northwind. Per questa dimostrazione, la classe `Employee` definisce anche il metodo `Random`, che crea un oggetto `Employee` con valori casuali per le relative proprietà.

<a name="operations"></a>

## <a name="defining-employee-database-operations"></a>Definizione delle operazioni dei dipendenti sul database

Aggiungere alla classe `Program` i metodi `InsertEmployees`, `GetEmployeeCount` e `GetEmployeeID`.

[!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
[!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]

Il metodo `InsertEmployees` aggiunge nuovi record di dipendenti nel database. Il metodo `GetEmployeeCount` recupera il numero di voci nella tabella `Employees`. Il metodo `GetEmployeeID` recupera l'identificatore del primo dipendente con il nome specificato. Ognuno di questi metodi accetta una stringa di connessione al database Northwind e usa la funzionalità nello spazio dei nomi `System.Data.SqlServerCe` per comunicare con il database.

<a name="nonBuffering"></a>

## <a name="adding-employee-data-to-the-database-without-using-buffering"></a>Aggiunta di dati dei dipendenti al database senza usare la memorizzazione nel buffer

Aggiungere alla classe `Program` i metodi `AddEmployees` e `PostRandomEmployees`.

[!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
[!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]

Il metodo `AddEmployees` aggiunge dati di dipendenti casuali al database usando un flusso di dati. Crea un oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> che chiama il metodo `InsertEmployees` per aggiungere una voce di dipendente al database. Il metodo `AddEmployees` chiama quindi il metodo `PostRandomEmployees` per registrare più oggetti `Employee` nell'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>. Il metodo `AddEmployees` attende quindi il completamento di tutte le operazioni di inserimento.

<a name="buffering"></a>

## <a name="using-buffering-to-add-employee-data-to-the-database"></a>Uso della memorizzazione nel buffer per aggiungere dati dei dipendenti nel database

Aggiungere alla classe `Program` il metodo `AddEmployeesBatched`.

[!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
[!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]

Questo metodo è simile ad `AddEmployees`, ad eccezione del fatto che usa anche la classe <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> per memorizzare nel buffer più oggetti `Employee` prima di inviare questi ultimi all'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>. Poiché la classe <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> propaga più elementi come raccolta, l'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> viene modificato in modo da operare su una matrice di oggetti `Employee`. Come nel metodo `AddEmployees`, `AddEmployeesBatched` chiama il metodo `PostRandomEmployees` per registrare più oggetti `Employee`. `AddEmployeesBatched` tuttavia invia questi oggetti nell'oggetto <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>. Il metodo `AddEmployeesBatched` attende anche il completamento di tutte le operazioni di inserimento.

<a name="bufferedJoin"></a>

## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a>Uso di un join memorizzato nel buffer per leggere dati dei dipendenti dal database

Aggiungere alla classe `Program` il metodo `GetRandomEmployees`.

[!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
[!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]

Questo metodo visualizza informazioni su dipendenti casuali nella console. Crea diversi oggetti `Employee` casuali e chiama il metodo `GetEmployeeID` per recuperare l'identificatore univoco per ogni oggetto. Poiché il metodo `GetEmployeeID` genera un'eccezione se non esiste alcun dipendente corrispondenti al nome e al cognome specificati, il metodo `GetRandomEmployees` usa la classe <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> per archiviare oggetti `Employee` per le chiamate a `GetEmployeeID` con esito positivo e oggetti <xref:System.Exception?displayProperty=nameWithType> per le chiamate con esito negativo. L'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> in questo esempio opera su un oggetto <xref:System.Tuple%602> contenente un elenco di oggetti `Employee` e un elenco di oggetti <xref:System.Exception>. L'oggetto <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> propaga questi dati quando la somma del numero degli oggetti `Employee` e <xref:System.Exception> ricevuti è uguale alla dimensione del batch.

<a name="complete"></a>

## <a name="the-complete-example"></a>Esempio completo

L'esempio seguente mostra il codice completo. Il metodo `Main` confronta il tempo necessario per eseguire operazioni di inserimento in batch nel database rispetto al tempo necessario per eseguire operazioni di inserimento non in batch nel database stesso. Viene anche illustrato l'uso di un join memorizzato nel buffer per leggere dati dei dipendenti dal database e anche segnalare eventuali errori.

[!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
[!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]

## <a name="see-also"></a>Vedere anche

- [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)

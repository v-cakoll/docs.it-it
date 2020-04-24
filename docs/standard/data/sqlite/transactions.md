---
title: Transazioni
ms.date: 12/13/2019
description: Informazioni su come usare le transazioni.
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447139"
---
# <a name="transactions"></a>Transazioni

Le transazioni consentono di raggruppare più istruzioni SQL in una singola unità di lavoro di cui viene eseguito il commit nel database come un'unica unità atomica. Se un'istruzione nella transazione ha esito negativo, è possibile eseguire il rollback delle modifiche apportate dalle istruzioni precedenti. Stato iniziale del database in cui è stata avviata la transazione. L'uso di una transazione può anche migliorare le prestazioni in SQLite quando si apportano numerose modifiche al database in una sola volta.

## <a name="concurrency"></a>Concorrenza

In SQLite, solo una transazione può presentare modifiche in sospeso nel database alla volta. Per questo motivo, è possibile <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> che si `Execute` verifichi il <xref:Microsoft.Data.Sqlite.SqliteCommand> timeout delle chiamate a e dei metodi in se un'altra transazione impiega troppo tempo per il completamento.

Per ulteriori informazioni sul blocco, i tentativi e i timeout, vedere [errori del database](database-errors.md).

## <a name="isolation-levels"></a>Livelli di isolamento

Per impostazione predefinita, le transazioni sono **serializzabili** in SQLite. Questo livello di isolamento garantisce che tutte le modifiche apportate all'interno di una transazione siano completamente isolate. Altre istruzioni eseguite all'esterno della transazione non sono interessate dalle modifiche della transazione.

SQLite supporta anche **Read uncommitted** quando si usa una cache condivisa. Questo livello consente letture dirty, letture non ripetibili e Phantom:

- Una *lettura dirty* si verifica quando le modifiche in sospeso in una transazione vengono restituite da una query all'esterno della transazione, ma viene eseguito il rollback delle modifiche apportate alla transazione. I risultati contengono dati che non sono mai stati effettivamente sottoposte a commit nel database.

- Una *lettura non ripetibile* si verifica quando una transazione esegue una query sulla stessa riga due volte, ma i risultati sono diversi perché sono stati modificati tra le due query da un'altra transazione.

- Gli oggetti *fantasma* sono righe che vengono modificate o aggiunte per soddisfare la clausola WHERE di una query durante una transazione. Se consentito, la stessa query può restituire righe diverse quando viene eseguita due volte nella stessa transazione.

Microsoft. Data. sqlite considera il valore IsolationLevel passato <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> a come livello minimo. Il livello di isolamento effettivo verrà promosso a Read uncommitted o Serializable.

Il codice seguente simula una lettura dirty. Si noti che la stringa di connessione `Cache=Shared`deve includere.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]

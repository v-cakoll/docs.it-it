---
title: Collation
ms.date: 12/13/2019
description: Informazioni su come creare una sequenza di ordinamento personalizzata.
ms.openlocfilehash: 0942ad4523a149ad74321cbe0f63021f53303579
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447027"
---
# <a name="collation"></a>Collation

Le sequenze di confronto vengono usate da SQLite quando si confrontano i valori di testo per determinare l'ordine e l'uguaglianza. È possibile specificare le regole di confronto da utilizzare per la creazione di colonne o per operazione nelle query SQL. SQLite include tre sequenze di confronto per impostazione predefinita.

| Collation | Descrizione                               |
| --------- | ----------------------------------------- |
| RTRIM     | Ignora lo spazio vuoto finale               |
| NOCASE    | Senza distinzione tra maiuscole e minuscole per i caratteri ASCII A-Z |
| BINARY    | Distinzione tra maiuscole e minuscole. Confronta i byte direttamente   |

## <a name="custom-collation"></a>Regole di confronto personalizzate

È anche possibile definire sequenze di fascicolazione personalizzate oppure eseguire l'override di quelle predefinite usando <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>. Nell'esempio seguente viene illustrato come eseguire l'override delle regole di confronto nocase per supportare i caratteri Unicode. Il [codice di esempio completo](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) è disponibile in GitHub.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like (operatore)

L'operatore LIKE in SQLite non rispetta le regole di confronto. L'implementazione predefinita ha la stessa semantica delle regole di confronto nocase. Non fa distinzione tra maiuscole e minuscole per i caratteri ASCII da A A Z.

È possibile rendere facilmente l'operatore LIKE con distinzione tra maiuscole e minuscole usando l'istruzione pragma seguente:

```sql
PRAGMA case_sensitive_like = 0
```

Per informazioni dettagliate sull'override dell'implementazione dell'operatore LIKE, vedere [funzioni definite dall'utente](user-defined-functions.md) .

## <a name="see-also"></a>Vedere anche

* [Funzioni definite dall'utente](user-defined-functions.md)
* [Sintassi SQL](https://www.sqlite.org/lang.html)

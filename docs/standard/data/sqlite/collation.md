---
title: Regole di confronto
ms.date: 12/13/2019
description: Scopri come creare una sequenza di confronto personalizzata.
ms.openlocfilehash: b93c82a4ace154b8293b05effa8f9e9294fa7708
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79506541"
---
# <a name="collation"></a>Regole di confronto

Le sequenze di confronto vengono utilizzate da SQLite quando si confrontano i valori TEXT per determinare l'ordine e l'uguaglianza. È possibile specificare le regole di confronto da utilizzare quando si creano colonne o per ogni operazione nelle query SQL. SQLite include tre sequenze di confronto per impostazione predefinita.

| Regole di confronto | Descrizione                               |
| --------- | ----------------------------------------- |
| RTRIM     | Ignora gli spazi vuoti finali               |
| NESSUN CASO    | Senza distinzione tra maiuscole e minuscole per i caratteri ASCII dalla A alla z |
| BINARY    | Sensitive. Confronta direttamente i byte   |

## <a name="custom-collation"></a>Regole di confronto personalizzate

È inoltre possibile definire sequenze di confronto personalizzate o <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>eseguire l'override di quelle incorporate utilizzando . Nell'esempio seguente viene illustrato l'override delle regole di confronto NOCASE per supportare i caratteri Unicode. Il [codice di esempio completo](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) è disponibile su GitHub.The full sample code is available on GitHub.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like (operatore)

L'operatore LIKE in SQLite non rispetta le regole di confronto. L'implementazione predefinita ha la stessa semantica delle regole di confronto NOCASE. È solo senza distinzione tra maiuscole e minuscole per i caratteri ASCII dalla A alla z.

È possibile rendere facilmente l'operatore LIKE tra maiuscole e minuscole utilizzando la seguente istruzione pragma:

```sql
PRAGMA case_sensitive_like = 1
```

Vedere [Funzioni definite dall'utente](user-defined-functions.md) per informazioni dettagliate sull'override dell'implementazione dell'operatore LIKE.

## <a name="see-also"></a>Vedere anche

* [Funzioni definite dall'utente](user-defined-functions.md)
* [Sintassi SQL](https://www.sqlite.org/lang.html)

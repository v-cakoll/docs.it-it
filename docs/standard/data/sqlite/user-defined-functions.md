---
title: Funzioni definite dall'utente
ms.date: 12/13/2019
description: Informazioni su come creare funzioni scalari e di aggregazione definite dall'utente.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447174"
---
# <a name="user-defined-functions"></a>Funzioni definite dall'utente

La maggior parte dei database ha un sottolinguaggio procedurale di SQL che è possibile usare per definire funzioni personalizzate. SQLite, tuttavia, viene eseguito in-process con l'app. Anziché dover apprendere un nuovo dialetto di SQL, è possibile usare semplicemente il linguaggio di programmazione dell'app.

## <a name="scalar-functions"></a>Funzioni scalari

Le funzioni scalari restituiscono un singolo valore scalare per ogni riga di una query. Definire nuove funzioni scalari ed eseguire l'override di quelle predefinite <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>usando.

Per [Data types](types.md) un elenco di parametri e tipi restituiti supportati per l' `func` argomento, vedere tipi di dati.

Se si `state` specifica l'argomento, il valore passerà a ogni chiamata della funzione. Usare questa operazione per evitare chiusure.

Specificare `isDeterministic` se la funzione è deterministica per consentire a SQLite di usare ottimizzazioni aggiuntive durante la compilazione delle query.

Nell'esempio seguente viene illustrato come aggiungere una funzione scalare per calcolare il raggio di un cilindro.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a>Operatori

Gli operatori SQLite seguenti vengono implementati dalle funzioni scalari corrispondenti. La definizione di queste funzioni scalari nell'app sostituirà il comportamento di questi operatori.

| Operatore          | Funzione      |
| ----------------- | ------------- |
| X GLOB Y          | Glob (Y, X)    |
| X COME Y          | like (Y, X)    |
| X COME ESCAPE Y Z | like (Y, X, Z) |
| X CORRISPONDENZA Y         | Match (Y, X)   |
| X REGEXP Y        | RegExp (Y, X)  |

Nell'esempio seguente viene illustrato come definire la funzione regexp per abilitare l'operatore corrispondente. SQLite non include un'implementazione predefinita della funzione RegExp.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a>Funzioni di aggregazione

Le funzioni di aggregazione restituiscono un singolo valore aggregato per tutte le righe di una query. Definire ed eseguire l'override di <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>funzioni di aggregazione tramite.

L' `seed` argomento specifica lo stato iniziale del contesto. Usare questo per evitare anche le chiusure.

L' `func` argomento viene richiamato una volta per ogni riga. Usare il contesto per accumulare un risultato finale. Restituisce il contesto. Questo modello consente al contesto di essere un tipo valore o non modificabile.

Se non `resultSelector` si specifica alcun oggetto, viene utilizzato lo stato finale del contesto come risultato. Ciò consente di semplificare la definizione di funzioni quali SUM e count che devono solo incrementare un numero ogni riga e restituirla.

Specificare `resultSelector` per calcolare il risultato finale dal contesto dopo l'iterazione in tutte le righe.

Per [Data types](types.md) un elenco dei tipi di parametro supportati per l'argomento e `func` i tipi restituiti per `resultSelector`, vedere tipi di dati.

Se la funzione è deterministica, `isDeterministic` specificare per consentire a SQLite di usare ottimizzazioni aggiuntive durante la compilazione delle query.

Nell'esempio seguente viene definita una funzione di aggregazione per calcolare la deviazione standard di una colonna.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a>Errors

Se una funzione definita dall'utente genera un'eccezione, il messaggio viene restituito a SQLite. SQLite genera quindi un errore e Microsoft. Data. sqlite genererà una Sqliteexception. Per ulteriori informazioni, vedere [errori del database](database-errors.md).

Per impostazione predefinita, il codice di errore SQLite di errore verrà SQLITE_ERROR (o 1). È tuttavia possibile modificarlo generando un oggetto <xref:Microsoft.Data.Sqlite.SqliteException> nella funzione con l'oggetto desiderato. <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode>

## <a name="debugging"></a>Debug

SQLite chiama direttamente l'implementazione. Ciò consente di aggiungere punti di interruzione che si attivano mentre SQLite sta valutando le query. L'esperienza di debug .NET completa è disponibile per semplificare la creazione di funzioni definite dall'utente.

## <a name="see-also"></a>Vedi anche

* [Tipi di dati](types.md)
* [Funzioni di base di SQLite](https://www.sqlite.org/lang_corefunc.html)
* [Funzioni di aggregazione SQLite](https://www.sqlite.org/lang_aggfunc.html)

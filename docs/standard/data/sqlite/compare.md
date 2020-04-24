---
title: Confronto con System. Data. SQLite
ms.date: 12/13/2019
description: Descrive alcune delle differenze tra le librerie Microsoft. Data. sqlite e System. Data. SQLite.
ms.openlocfilehash: 076bbc6f746cf9296c96ec73047397a21a3b2558
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900705"
---
# <a name="comparison-to-systemdatasqlite"></a>Confronto con System. Data. SQLite

In 2005, Robert Simpson ha creato System. Data. SQLite, un provider SQLite per ADO.NET 2,0. In 2010, il team SQLite ha assunto la manutenzione e lo sviluppo del progetto. È anche importante notare che il team mono ha biforcato il codice in 2007 come mono. Data. sqlite. System. Data. SQLite ha una lunga cronologia ed è diventato un provider ADO.NET stabile e completo completo di strumenti di Visual Studio. Le nuove versioni continuano a spedire gli assembly compatibili con ogni versione di .NET Framework alla versione 2,0 e persino .NET Compact Framework 3,5.

La prima versione di .NET Core (rilasciata in 2016) è un'implementazione unica, leggera, moderna e multipiattaforma di .NET. Le API e le API obsolete con alternative più moderne sono state intenzionalmente rimosse. ADO.NET non includeva alcuna API del set di dati (compresi DataTable e DataAdapter).

Il team Entity Framework aveva una certa familiarità con la codebase System. Data. SQLite. Brice Liguori, un membro del team EF, ha precedentemente aiutato il team SQLite a aggiungere il supporto per Entity Framework versioni 5 e 6. Brice è stato anche sperimentato con la propria implementazione di un provider SQLite ADO.NET intorno all'ora in cui è stato pianificato .NET Core. Dopo una discussione molto estesa, il team di Entity Framework ha deciso di creare Microsoft. Data. sqlite in base al prototipo di Brice. Ciò consentirebbe loro di creare una nuova implementazione leggera e moderna che verrebbe allineata con gli obiettivi di .NET Core.

Come esempio di ciò che si intende per più moderno, ecco il codice per creare una [funzione definita dall'utente](user-defined-functions.md) sia in System. Data. SQLite che in Microsoft. Data. sqlite.

```csharp
// System.Data.SQLite
connection.BindFunction(
    new SQLiteFunctionAttribute("ceiling", 1, FunctionType.Scalar),
    (Func<object[], object>)((object[] args) => Math.Ceiling((double)((object[])args[1])[0])),
    null);

// Microsoft.Data.Sqlite
connection.CreateFunction(
    "ceiling",
    (double arg) => Math.Ceiling(arg));
```

In 2017, .NET Core 2,0 ha riscontrato un cambiamento nella strategia. Era stato deciso che la compatibilità con .NET Framework era fondamentale per il successo di .NET Core. Molte delle API rimosse, incluse le API del set di dati, sono state aggiunte nuovamente. Analogamente a quanto avveniva per molti altri, questo System. Data. SQLite non è stato in grado di eseguire il porting anche a .NET Core. L'obiettivo originale di Microsoft. Data. SQLite per essere leggero e moderno rimane comunque. Per informazioni dettagliate sulle API ADO.NET non implementate da Microsoft. Data. SQLite, vedere [limitazioni di ADO.NET](adonet-limitations.md) .

Quando vengono aggiunte nuove funzionalità a Microsoft. Data. SQLite, viene presa in considerazione la progettazione di System. Data. SQLite. Quando possibile, si tenta di ridurre al minimo le modifiche tra i due per semplificare la transizione tra di essi.

## <a name="data-types"></a>Tipi di dati

La differenza principale tra Microsoft. Data. sqlite e System. Data. SQLite è il modo in cui vengono gestiti i tipi di dati. Come descritto in [tipi di dati](types.md), Microsoft. Data. SQLite non tenta di nascondere l'eccentricità sottostante di SQLite, che consente di specificare qualsiasi stringa arbitraria come tipo di colonna e dispone solo di quattro tipi primitivi: Integer, Real, text e BLOB.

System. Data. SQLite applica una semantica aggiuntiva ai tipi di colonna che li mappano direttamente ai tipi .NET. Questa operazione fornisce al provider un aspetto più fortemente tipizzato, ma presenta alcuni bordi approssimativi. Ad esempio, devono introdurre una nuova istruzione SQL (tipi) per specificare i tipi di colonna delle espressioni nelle istruzioni SELECT.

## <a name="connection-strings"></a>Stringhe di connessione

Microsoft. Data. SQLite ha un numero molto inferiore di parole chiave per la [stringa di connessione](connection-strings.md) . La tabella seguente illustra le alternative che è possibile usare in alternativa.

| Parola chiave          | Alternativa                                         |
| ---------------- | --------------------------------------------------- |
| Dimensione cache (%):       | Invia`PRAGMA cache_size = <pages>`                  |
| Timeout predefinito  | Usare la proprietà DefaultTimeout in SqliteConnection |
| FailIfMissing    | Utilizzare `Mode=ReadWrite`.                                |
| FullUri          | Usare la parola chiave dell'origine dati                         |
| Modalità Journal     | Invia`PRAGMA journal_mode = <mode>`                 |
| Formato legacy    | Invia`PRAGMA legacy_file_format = 1`                |
| Numero massimo di pagine   | Invia`PRAGMA max_page_count = <pages>`              |
| Dimensioni pagina        | Invia`PRAGMA page_size = <bytes>`                   |
| Sola lettura        | Utilizzare `Mode=ReadOnly`.                                 |
| Sincrono      | Invia`PRAGMA synchronous = <mode>`                  |
| Uri              | Usare la parola chiave dell'origine dati                         |
| UseUTF16Encoding | Invia`PRAGMA encoding = 'UTF-16'`                   |

## <a name="authorization"></a>Autorizzazione

Microsoft. Data. SQLite non contiene alcuna API che espone il callback di autorizzazione di SQLite. Usare [#13835](https://github.com/dotnet/efcore/issues/13835) di problema per fornire commenti e suggerimenti su questa funzionalità.

## <a name="data-change-notifications"></a>Notifiche delle modifiche dei dati

Microsoft. Data. SQLite non contiene alcuna API che espone le notifiche di modifica dei dati di SQLite. Usare [#13827](https://github.com/dotnet/efcore/issues/13827) di problema per fornire commenti e suggerimenti su questa funzionalità.

## <a name="virtual-table-modules"></a>Moduli della tabella virtuale

Microsoft. Data. SQLite non dispone di alcuna API per la creazione di moduli di tabella virtuale. Usare [#13823](https://github.com/dotnet/efcore/issues/13823) di problema per fornire commenti e suggerimenti su questa funzionalità.

## <a name="see-also"></a>Vedi anche

* [Tipi di dati](types.md)
* [Stringhe di connessione](connection-strings.md)
* [Crittografia](encryption.md)
* [Limitazioni di ADO.NET](adonet-limitations.md)
* [Limitazioni di elegante](dapper-limitations.md)

---
title: Articoli sulla procedura (Guida a C#)
description: Raccolta di suggerimenti rapidi e brevi esempi di codice evidenziati
ms.date: 12/20/2017
ms.openlocfilehash: 81ef8106add757cf3c83aa7dc130f5474b936461
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794702"
---
# <a name="how-to-c"></a>Procedura (C#)

Nella sezione How to della Guida di C# è possibile trovare risposte rapide alle domande più comuni. In alcuni casi gli articoli possono essere elencati in più sezioni. Volevamo semplificarne la ricerca rendendoli disponibili in più percorsi.

## <a name="general-c-concepts"></a>Concetti generali di C#

Sono disponibili diversi suggerimenti e consigli che sono procedure comuni per gli sviluppatori C#:

- [Inizializzare oggetti usando un inizializzatore di oggetto](../programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md).
- [Informazioni sulle differenze tra il passaggio a un metodo di uno struct e di una classe](../programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md).
- [Usare l'overload degli operatori](../language-reference/operators/operator-overloading.md).
- [Implementare e chiamare un metodo di estensione personalizzato](../programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).
- Anche i programmatori C# potrebbero voler [usare lo `My` spazio dei nomi da Visual Basic](../programming-guide/namespaces/how-to-use-the-my-namespace.md).
- [Creare un nuovo metodo per un tipo `enum` usando i metodi di estensione](../programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).

### <a name="class-and-struct-members"></a>Membri di classi e struct

Per implementare il programma è necessario creare classi e struct. Queste tecniche sono comunemente usate durante la scrittura di classi o struct.

- [Dichiarare proprietà implementate automaticamente](../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).
- [Dichiarare e usare proprietà di lettura/scrittura](../programming-guide/classes-and-structs/how-to-declare-and-use-read-write-properties.md).
- [Definire costanti](../programming-guide/classes-and-structs/how-to-define-constants.md).
- [Eseguire l'override del metodo `ToString` per specificare l'output della stringa](../programming-guide/classes-and-structs/how-to-override-the-tostring-method.md).
- [Definire le proprietà astratte](../programming-guide/classes-and-structs/how-to-define-abstract-properties.md).
- [Usare le funzionalità relative alla documentazione XML per documentare il codice](../programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md).
- [Implementare in modo esplicito i membri di interfaccia](../programming-guide/interfaces/how-to-explicitly-implement-interface-members.md) per mantenere concisa l'interfaccia pubblica.
- [Implementare in modo esplicito i membri di due interfacce](../programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md).

### <a name="working-with-collections"></a>Uso delle raccolte

Questi articoli contengono informazioni sull'uso delle raccolte di dati.

- [Inizializzare un dizionario con un inizializzatore di insieme](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md).

## <a name="working-with-strings"></a>Uso delle stringhe

Le stringhe sono il tipo di dati di base usato per visualizzare o modificare il testo. Questi articoli illustrano le procedure comuni da seguire con le stringhe.

- [Confrontare le stringhe](compare-strings.md).
- [Modificare il contenuto di una stringa](modify-string-contents.md).
- [Determinare se una stringa rappresenta un numero](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Usare `String.Split` per separare stringhe](parse-strings-using-split.md).
- [Unire più stringhe in una](concatenate-multiple-strings.md).
- [Eseguire la ricerca di testo in una stringa](search-strings.md).

## <a name="convert-between-types"></a>Eseguire la conversione tra tipi

Potrebbe essere necessario convertire un oggetto in un tipo diverso.

- [Determinare se una stringa rappresenta un numero](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Eseguire la conversione tra stringhe che rappresentano numeri esadecimali e numero](../programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).
- [Convertire una stringa in un oggetto `DateTime`](../../standard/base-types/parsing-datetime.md).
- [Convertire una matrice di byte in un Integer](../programming-guide/types/how-to-convert-a-byte-array-to-an-int.md).
- [Convertire una stringa in un numero](../programming-guide/types/how-to-convert-a-string-to-a-number.md).
- [Usare i criteri di ricerca e gli operatori `as` e `is` per eseguire il cast sicuro a un tipo diverso](safely-cast-using-pattern-matching-is-and-as-operators.md).
- [Definire le conversioni di tipi personalizzate](../language-reference/operators/user-defined-conversion-operators.md).
- [Determinare se un tipo è un tipo di valore nullable](../language-reference/builtin-types/nullable-value-types.md#how-to-identify-a-nullable-value-type).
- [Eseguire la conversione tra tipi di valore nullable e non nullable](../language-reference/builtin-types/nullable-value-types.md#conversion-from-a-nullable-value-type-to-an-underlying-type).

## <a name="equality-and-ordering-comparisons"></a>Confronti di uguaglianza e ordinamento

È possibile creare tipi che definiscono regole specifiche per verificare l'uguaglianza o definire un ordinamento naturale tra oggetti di quel tipo.

- [Testare l'uguaglianza di riferimenti](../programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).
- [Definire l'uguaglianza di valori per un tipo](../programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).

## <a name="exception-handling"></a>Gestione delle eccezioni

I programmi .NET segnalano il lavoro incompleto dei metodi generando eccezioni. Questi articoli contengono informazioni sull'uso delle eccezioni.

- [Gestire eccezioni usando `try` e `catch`](../programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md).
- [Eseguire la pulizia delle risorse usando le clausole `finally`](../programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md).
- [Recuperare eccezioni non CLS (Common Language Specification)](../programming-guide/exceptions/how-to-catch-a-non-cls-exception.md).

## <a name="delegates-and-events"></a>Delegati ed eventi

I delegati e gli eventi offrono una funzionalità per strategie che riguardano blocchi di codice con accoppiamento libero.

- [Dichiarare, crearne un'istanza e usare delegati](../programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md).
- [Combinare delegati multicast](../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md).

Gli eventi offrono un meccanismo per pubblicare o sottoscrivere notifiche.

- [Eseguire e annullare la sottoscrizione di eventi](../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).
- [Implementare eventi dichiarati in interfacce](../programming-guide/events/how-to-implement-interface-events.md).
- [Conformità alle linee guida di .NET Framework quando il codice pubblica eventi](../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).
- [Generare eventi definiti in classi base da classi derivate](../programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md).
- [Implementare funzioni di accesso a eventi personalizzati](../programming-guide/events/how-to-implement-custom-event-accessors.md).

## <a name="linq-practices"></a>Procedure LINQ

LINQ consente di scrivere codice per eseguire query su qualsiasi origine dati che supporta il criterio di espressione di query LINQ. Questi articoli contengono informazioni sul criterio e sull'uso di origini dati diverse.

- [Eseguire la query di una raccolta](../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).
- [Usare espressioni lambda in una query](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-in-a-query.md).
- [Usare `var` in espressioni di query](../programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).
- [Restituire sottoinsiemi di proprietà degli elementi in una query](../programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).
- [Scrivere query con filtro complesso](../programming-guide/concepts/linq/how-to-write-queries-with-complex-filtering.md).
- [Ordinare elementi di un'origine dati](../programming-guide/concepts/linq/how-to-sort-elements.md).
- [Ordinare elementi in base a più chiavi](../programming-guide/concepts/linq/how-to-sort-elements-on-multiple-keys.md).
- [Controllare il tipo di una proiezione](../programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md).
- [Contare le occorrenze di un valore in una sequenza di origine](../programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md).
- [Calcolare valori intermedi](../programming-guide/concepts/linq/how-to-calculate-intermediate-values.md).
- [Unire dati di più origini](../programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md).
- [Trovare la differenza dei set tra due sequenze](../programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md).
- [Eseguire il debug di risultati di query vuoti](../programming-guide/concepts/linq/how-to-debug-empty-query-results-sets.md).
- [Aggiungere metodi personalizzati per le query LINQ](../programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md).

## <a name="multiple-threads-and-async-processing"></a>Più thread ed elaborazione asincrona

I programmi moderni usano spesso operazioni asincrone. Questi articoli contengono informazioni sull'uso di queste tecniche.

- [Migliorare le prestazioni di operazioni asincrone usando `System.Threading.Tasks.Task.WhenAll`](../programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).
- [Eseguire più richieste Web in parallelo tramite `async` e `await`](../programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md).
- [Usare un pool di thread](../../standard/threading/the-managed-thread-pool.md#using-the-thread-pool).

## <a name="command-line-args-to-your-program"></a>Argomenti della riga di comando per il programma

I programmi C# contengono generalmente argomenti della riga di comando. Questi articoli spiegano come accedere a tali argomenti ed elaborarli.

- [Recuperare tutti gli argomenti della riga di comando con `for`](../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md).

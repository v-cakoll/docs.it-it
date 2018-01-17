---
title: Articoli sulla procedura (Guida a C#)
description: Raccolta di suggerimenti rapidi e brevi esempi di codice evidenziati
author: billwagner
ms.author: wiwagn
ms.date: 12/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: cfe7115717fcca834d87b7bcdc64ddd1df8ef843
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-c"></a>Procedura (C#)

Nella sezione della Guida a C# dedicata alla procedura è possibile trovare rapidamente le risposte alle domande più frequenti. In alcuni casi gli articoli possono essere elencati in più sezioni. Volevamo semplificarne la ricerca rendendoli disponibili in più percorsi. 

## <a name="general-c-concepts"></a>Concetti generali di C#

Esistono alcuni suggerimenti e consigli comuni per le procedure di sviluppo di C#.

- [Inizializzare oggetti usando un inizializzatore di oggetto](../programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md).
- [Informazioni sulle differenze tra il passaggio a un metodo di uno struct e di una classe](../programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md).
- [Come usare espressioni lambda](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).
- [Risolvere conflitti di nomi di tipo tramite l'alias dello spazio dei nomi globale](../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).
- [Usare l'overload degli operatori](../programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md).
- [Implementare e chiamare un metodo di estensione personalizzato](../programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).
- È possibile che i programmatori C# vogliano [usare lo spazio dei nomi `My` di VB](../programming-guide/namespaces/how-to-use-the-my-namespace.md).
- [Creare un nuovo metodo per un tipo `enum` usando i metodi di estensione](../programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).

### <a name="class-and-struct-members"></a>Membri di classi e struct

Per implementare il programma è necessario creare classi e struct. Queste tecniche sono comunemente usate durante la scrittura di classi o struct.

- [Dichiarare proprietà implementate automaticamente](../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).
- [Dichiarare e usare proprietà di lettura/scrittura](../programming-guide/classes-and-structs/how-to-declare-and-use-read-write-properties.md).
- [Definire costanti](../programming-guide/classes-and-structs/how-to-define-constants.md).
- [Eseguire l'override del metodo `ToString` per specificare l'output della stringa](../programming-guide/classes-and-structs/how-to-override-the-tostring-method.md).
- [Definire proprietà astratte](../programming-guide/classes-and-structs/how-to-define-abstract-properties.md).
- [Usare le funzionalità relative alla documentazione XML per documentare il codice](../programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md).
- [Implementare in modo esplicito i membri di interfaccia](../programming-guide/interfaces/how-to-explicitly-implement-interface-members.md) per mantenere concisa l'interfaccia pubblica.
- [Implementare in modo esplicito i membri di due interfacce](../programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md).

### <a name="working-with-collections"></a>Uso delle raccolte

Questi articoli contengono informazioni sull'uso delle raccolte di dati.

- [Inizializzare un dizionario con un inizializzatore di insieme](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md).
- [Accedere a tutti gli elementi in una raccolta tramite `foreach`](../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md).

## <a name="strings"></a>stringhe

Le stringhe sono il tipo di dati di base usato per visualizzare o modificare il testo. Questi articoli illustrano le procedure comuni da seguire con le stringhe.

- [Confrontare stringhe](../programming-guide/strings/how-to-compare-strings.md).
- [Modificare il contenuto di una stringa](../programming-guide/strings/how-to-modify-string-contents.md).
- [Determinare se una stringa rappresenta un numero](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Usare `String.Split` per separare stringhe](parse-strings-using-split.md).
- [Unire più stringhe in una](../programming-guide/strings/how-to-concatenate-multiple-strings.md).
- [Eseguire la ricerca di testo in una stringa](../programming-guide/strings/how-to-search-strings-using-string-methods.md).
- [Eseguire la ricerca di stringhe tramite espressioni regolari](../programming-guide/strings/how-to-search-strings-using-regular-expressions.md).

## <a name="convert-between-types"></a>Eseguire la conversione tra tipi

Potrebbe essere necessario convertire un oggetto in un tipo diverso.

- [Determinare se una stringa rappresenta un numero](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Eseguire la conversione tra stringhe che rappresentano numeri esadecimali e numero](../programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).
- [Convertire una stringa in un oggetto <xref:System.DateTime>](../programming-guide/strings/how-to-convert-a-string-to-a-datetime.md).
- [Convertire una matrice di byte in un Integer](../programming-guide/types/how-to-convert-a-byte-array-to-an-int.md).
- [Convertire una stringa in un numero](../programming-guide/types/how-to-convert-a-string-to-a-number.md).
- [Usare `as` e `is` per eseguire il cast sicuro di un tipo diverso](../programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).
- [Definire operatori di conversione per tipi `struct`](../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md).
- [Determinare se un tipo è un tipo di valore nullable](../programming-guide/nullable-types/how-to-identify-a-nullable-type.md).
- [Eseguire la conversione tra tipi di valore nullable e non nullable](../programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).

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
- [Archiviare istanze di eventi in un dizionario](../programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md).
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
- [Usare un pool di thread](../programming-guide/concepts/threading/how-to-use-a-thread-pool.md).

## <a name="command-line-args-to-your-program"></a>Argomenti della riga di comando per il programma

I programmi C# contengono generalmente argomenti della riga di comando. Questi articoli spiegano come accedere a tali argomenti ed elaborarli.

- [Recuperare tutti gli argomenti della riga di comando con `for`](../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md).
- [Recuperare tutti gli argomenti della riga di comando con `foreach`](../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md).

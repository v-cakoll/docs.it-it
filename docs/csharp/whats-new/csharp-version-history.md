---
title: Cronologia di C# - Guida a C#
description: Caratteristiche del linguaggio nelle prime versioni ed evoluzione successiva.
keywords: C#, .NET, .NET Core, Novità, Cronologia di C#
author: erikdietrich
ms.author: wiwagn
ms.date: 09/20/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: d24d190eab5896121231543e6696b6a4861b5bb8
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2018
---
# <a name="the-history-of-c"></a>Cronologia di C# #

Quali erano le caratteristiche del linguaggio nelle prime versioni e come si è evoluto negli anni successivi?

## <a name="c-version-10"></a>C# versione 1.0

Se ci si guarda indietro, ci si rende conto che C# versione 1.0 era molto simile a Java. Come affermato [negli obiettivi di progettazione dichiarati per ECMA](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html), C# cercava di essere "un linguaggio orientato a oggetti di utilizzo generico, semplice e moderno".  All'epoca, somigliare molto a Java significava aver raggiunto tali obiettivi di progettazione di allora.

Ma se si guarda ora com'era C# 1.0, la sensazione è di disorientamento. Mancavano le funzionalità asincrone predefinite e alcune delle semplici funzionalità relative ai generics che ora si danno per scontate. In realtà,i generics mancavano completamente.  E [LINQ](../linq/index.md)? Non era ancora disponibile. Ci volevano ancora alcuni anni.

Rispetto alla versione odierna, C# versione 1.0 sembra privo di funzionalità e costringeva gli sviluppatori a scrivere codice piuttosto prolisso. Da qualche parte, tuttavia, bisognava cominciare. Per la piattaforma Windows, C# versione 1.0 rappresentava una valida alternativa a Java.

## <a name="c-version-20"></a>C# versione 2.0

Qui le cose iniziano a farsi interessanti. Ecco alcune delle funzionalità principali di C# 2.0, rilasciato nel 2005 insieme a Visual Studio 2005:

- [Generics](../programming-guide/generics/index.md)
- [Tipi parziali](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [Metodi anonimi](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Tipi nullable](../programming-guide/nullable-types/index.md)
- [Iteratori](../programming-guide/concepts/iterators.md)
- [Covarianza e controvarianza](../programming-guide/concepts/covariance-contravariance/index.md)

All'inizio C# era un linguaggio orientato a oggetti (OO) piuttosto generico, ma con la versione 2.0 la situazione cambiò con grande rapidità. Dopo aver trovato una posizione stabile, gli sviluppatori di C# hanno affrontato alcuni gravi punti dolenti. E li hanno affrontati alla grande.

I generics hanno reso disponibili tipi e metodi in grado di operare su tipi arbitrari, mantenendo comunque l'indipendenza dai tipi. La classe <xref:System.Collections.Generic.List%601>, ad esempio, consente di eseguire un'iterazione attraverso `List<string>` o `List<int>` eseguendo operazioni indipendenti dai tipi su tali stringhe o tali numeri interi. Questo modo di procedere è preferibile alla creazione di eredi `ListInt` o al cast da `Object` per ogni operazione.

Con C# versione 2.0 sono arrivati gli iteratori. In breve, gli iteratori consentono di eseguire l'iterazione attraverso gli elementi di un `List` (o di altri tipi enumerabili) con un ciclo `foreach`. Grazie a questo importantissimo aspetto del linguaggio, la leggibilità del codice e la possibilità di comprenderlo sono migliorate notevolmente.

C#, tuttavia, continuava a correre dietro a Java, che aveva già rilasciato versioni che prevedevano generics e iteratori, ma questa situazione sarebbe cambiata presto. Man mano che procedevano nella loro evoluzione, infatti, i due linguaggi continuarono a differenziarsi.

## <a name="c-version-30"></a>C# versione 3.0

C# versione 3.0 è stato rilasciato alla fine del 2007, insieme a Visual Studio 2008, anche se la gamma completa delle funzionalità del linguaggio è stata in realtà rilasciata con C# versione 3.5. Questa versione rappresenta un cambiamento fondamentale, perché caratterizza C# come linguaggio di programmazione dalle caratteristiche davvero eccezionali. Ecco alcune delle funzionalità principali di questa versione:

- [Proprietà implementate automaticamente](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [Tipi anonimi](../programming-guide/classes-and-structs/anonymous-types.md)
- [Espressioni di query](../linq/query-expression-basics.md)
- [Espressioni lambda](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [Alberi delle espressioni](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [Metodi di estensione](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)

A posteriori, molte di queste funzionalità sembrano inevitabili e inseparabili, perché si fondono l'una con l'altra in modo strategico. Si pensa in genere che la funzionalità killer di questa versione di C# sia l'espressione di query, nota anche come Language-Integrated Query (LINQ),

che, grazie a una vista più particolareggiata, consente di esaminare alberi delle espressioni, espressioni lambda e tipi anonimi, le fondamenta su cui la funzionalità LINQ stessa si basa. In entrambi i casi, tuttavia, C# 3.0 ha introdotto un concetto rivoluzionario. C# 3.0 ha iniziato a creare i presupposti per la trasformazione di C# in un linguaggio ibrido, orientato a oggetti e funzionale.

In particolare, ha reso possibile scrivere query dichiarative nello stile di SQL per eseguire operazioni, tra l'altro, sulle raccolte. Anziché scrivere un ciclo `for` per calcolare la media di un elenco di numeri interi, è diventato possibile eseguire tale operazione semplicemente usando `list.Average()`. La combinazione di espressioni di query e di metodi di estensione rendeva quell'elenco di numeri interi molto più interessante.

La comprensione e l'integrazione effettive del concetto da parte degli utenti ha richiesto tempo, ma si è gradualmente realizzata. E ora, dopo anni, il codice è molto più conciso, semplice e funzionale.

## <a name="c-version-40"></a>C# versione 4.0

Per C# versione 4.0 è stato difficile essere all'altezza della rivoluzionaria versione 3.0. Con la versione 3.0, il linguaggio C# è uscito con decisione dall'ombra di Java e ha assunto una propria rilevanza. Il linguaggio stava rapidamente diventando elegante.

La versione successiva introdusse comunque alcune nuove interessanti funzionalità:

- [Associazione dinamica](../language-reference/keywords/dynamic.md)
- [Argomenti denominati/facoltativi](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [Covarianti e controvarianti generiche](../../standard/generics/covariance-and-contravariance.md)
- [Tipi di interoperabilità incorporati](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

I tipi di interoperabilità risolvevano un problema di distribuzione. Le covarianze e le controvarianze generiche offrono modalità più avanzate per l'uso dei generics, ma hanno un'aria accademica e sono probabilmente apprezzate soprattutto dagli autori di librerie e di framework. I parametri denominati e facoltativi consentono di eliminare molti overload di metodi e sono più comodi da usare. Ma nessuna di queste funzionalità è precisamente un modifica di paradigma.

La caratteristica principale è stata l'introduzione della parola chiave `dynamic`. La parola chiave `dynamic` introdotta in C# versione 4.0 offre la possibilità di eseguire l'override del compilatore per la tipizzazione in fase di compilazione. Con la parola chiave dynamic è possibile creare costrutti simili a quelli dei linguaggi tipizzati in modo dinamico, come JavaScript. È possibile creare `dynamic x = "a string"` e quindi aggiungere 6, lasciando decidere al runtime cosa deve succedere dopo.

Questo modo di procedere è suscettibile di errori ma offre anche la possibilità di usare il linguaggio in modo estremamente avanzato.

## <a name="c-version-50"></a>C# versione 5.0

C# versione 5.0 è una versione del linguaggio molto specifica. Quasi tutto l'impegno per questa versione è stato indirizzato verso un altro concetto rivoluzionario.  Ecco l'elenco delle funzionalità principali:

- [Membri asincroni](../async.md)
- [Attributi informativi sul chiamante](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

Gli attributi informativi sul chiamante consentono di recuperare facilmente informazioni sul contesto di esecuzione senza dover ricorrere a una grande quantità di codice di reflection boilerplate. Questi attributi hanno molte applicazioni nelle attività di diagnostica e di registrazione.

Ma le vere stelle di questa versione sono `async` e `await`. Con il rilascio di queste funzionalità nel 2012, C# ha cambiato di nuovo le carte in tavola, incorporando l'asincronia nel linguaggio e assegnandole un ruolo fondamentale. Tutti coloro che hanno avuto a che fare con operazioni di lunga esecuzione e con l'implementazione di reti di callback hanno molto apprezzato questa funzionalità.

## <a name="c-version-60"></a>C# versione 6.0

Le versioni 3.0 e 5.0 hanno aggiunto a C# funzionalità eccezionali per un linguaggio orientato a oggetti. Con la versione 6.0, anziché una funzionalità killer che attirasse tutta l'attenzione, sono state rilasciate molte funzionalità che hanno fatto la gioia degli utenti del linguaggio. Eccone alcune:

- [Importazioni statiche](../language-reference/keywords/using-static.md)
- [Filtri eccezioni](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [Inizializzatori di proprietà](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [Membri con corpo di espressione](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [Propagazione Null](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [Interpolazione di stringhe](../language-reference/tokens/interpolated.md)
- [Operatore nameof](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [Inizializzatore di dizionario](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md)

Ognuna di queste funzionalità è interessante in sé, ma osservandole nel loro complesso si scopre uno schema interessante. In questa versione, C# ha eliminato il boilerplate del linguaggio, per rendere il codice più conciso e leggibile. Per gli amanti della pulizia e della semplicità del codice, questa versione del linguaggio rappresenta una vittoria notevole.

Con questa versione è stata introdotta un'altra caratteristica, che di per sé non rappresenta una funzionalità tradizionale del linguaggio. È stato rilasciato [Roslyn, il compilatore come servizio](https://github.com/dotnet/roslyn). Il compilatore C# è ora scritto in C# e può essere usato all'interno dei progetti di programmazione.

## <a name="c-version-70"></a>C# versione 7.0

La versione principale più recente di C# è la 7.0. Questa versione presenta alcune delle caratteristiche evolutive e innovative di C# 6.0, ma senza il compilatore come servizio. Ecco alcune delle nuove funzionalità:

- [Variabili out](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [Tuple e decostruzione](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [Criteri di ricerca](./csharp-7.md#pattern-matching)
- [Funzioni locali](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [Membri di espressioni corpo espansi](./csharp-7.md#more-expression-bodied-members)
- [Variabili locali e valori restituiti per riferimento](./csharp-7.md#ref-locals-and-returns)

Tutte queste caratteristiche offrono nuove utili funzionalità agli sviluppatori, oltre alla possibilità di scrivere codice più pulito che mai. Una funzionalità di particolare rilievo è la possibilità di condensare la dichiarazione di variabili da usare con la parola chiave `out`, consentendo più valori restituiti tramite tupla.

Ma C# è ora destinato a un uso ancora più ampio. .NET Core ora supporta qualsiasi sistema operativo ed è decisamente orientato al cloud e alla portabilità.  Questi obiettivi, insieme alla realizzazione di nuove funzionalità, tengono sicuramente impegnati i progettisti del linguaggio.

_Articolo_ [ _originariamente pubblicato nel blog NDepend_](https://blog.ndepend.com/c-versions-look-language-history/)_, gentilmente concesso da Erik Dietrich e Patrick Smacchia._

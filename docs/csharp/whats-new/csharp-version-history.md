---
title: La cronologia di c# - Guida per c#
description: "Ciò che il linguaggio sono simili nelle prime versioni, e come è è stato migliorato dal?"
keywords: "In c#, .NET, .NET Core, quali sono le novità, cronologia di c#"
author: erikdietrich
ms.author: wiwagn
ms.date: 09/20/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: 207c97c5dd7e04f815da61bff7f44393aea86222
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="the-history-of-c"></a>La cronologia del linguaggio c# #

Cosa l'aspetto di linguaggio come nel relativo versioni meno recenti? E come è è stato migliorato in anni dopo?

## <a name="c-version-10"></a>In c# versione 1.0

Quando si torna indietro e si cerca, in c# versione 1.0 era molto simile Java. Come [in parte relativi obiettivi indicati per ECMA](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html), richiesto da un "scopo generale semplice, moderno linguaggio orientato a oggetti."  Al momento, apparire Java deve viene ottenuta questi obiettivi di progettazione iniziale.

Ma se si osserva su c# 1.0 a questo punto, si otterrebbe se stessi un al. In mancanza di funzionalità async predefinite e alcune delle funzionalità semplice intorno generics che Adotteremo per concesso. In realtà, in mancanza di generics completamente.  E [LINQ](../linq/index.md)? Non è disponibile ancora. In questo caso alcuni anni per uscire.

In c# versione 1.0 era estratto di funzionalità, rispetto a oggi. È sarebbe necessario scrivere del codice dettagliato. Tuttavia, è necessario avviare una posizione. In c# versione 1.0 è una valida alternativa alla Java nella piattaforma Windows.

## <a name="c-version-20"></a>In c# versione 2.0

Ora le cose iniziano a interessanti. Esaminiamo ora alcune funzionalità principali di c# 2.0, rilasciato nel 2005, insieme a Visual Studio 2005:

- [Generics](../programming-guide/generics/index.md)
- [Tipi parziali](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [Metodi anonimi](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Tipi nullable](../programming-guide/nullable-types/index.md)
- [Iteratori](../programming-guide/concepts/iterators.md)
- [Covarianza e controvarianza](../programming-guide/concepts/covariance-contravariance/index.md)

Mentre in c# sia stato avviato come linguaggio Oriented OO abbastanza generico, in c# versione 2.0 sono stati modificati in pochissimo tempo. Una volta che avevano loro piedi sottostanti, stavano dopo alcuni punti deboli developer grave. E si è verificato un successivamente in termini generali.

Con i generics, si dispone di tipi e metodi che possono essere applicate a un tipo arbitrario, pur mantenendo l'indipendenza dai tipi. In tal caso, ad esempio, con un <xref:System.Collections.Generic.List%601> consente di disporre di `List<string>` o `List<int>` ed eseguire operazioni sicure di tipo per tali stringhe o numeri interi mentre si scorrono le. Questo è preferibile rispetto alla creazione `ListInt` gli eredi o il cast da `Object` per ogni operazione.

Iteratori c# versione 2.0 portata. In breve, ciò consente di scorrere gli elementi in un `List` (o altri tipi enumerabili) con un `foreach` ciclo. Con questo elemento come parte del linguaggio di prima classe notevolmente migliorata la leggibilità del linguaggio e capacità di prendere in considerazione il codice.

E ancora, c# continua a essere riprodotto un po' di recupero con Java. Java era già versioni incluse generics e iteratori. Ma che comporterebbe la modifica appena come continuate evoluzione divide in due lingue.

## <a name="c-version-30"></a>In c# versione 3.0

In c# versione 3.0 è stato ricevuto la fine del 2007, insieme a Visual Studio 2008, anche se sarebbe provengono in effetti barca completa di funzionalità del linguaggio con c# versione 3.5. Questa versione è contrassegnato da una modifica importante alla crescita del linguaggio c#. Ha stabilito c# come linguaggio di programmazione davvero eccezionale. Diamo un'occhiata alcune funzionalità principali in questa versione:

- [Proprietà implementate automaticamente](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [Tipi anonimi](../programming-guide/classes-and-structs/anonymous-types.md)
- [Espressioni di query](../linq/query-expression-basics.md)
- [Espressione lambda](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [Alberi delle espressioni](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [Metodi di estensione](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)

In retrospettiva, molte di queste funzionalità sembra non separabile sia inevitabile. Tutti interagiscono in modo strategico. In genere si pensa che funzionalità killer della versione c# è l'espressione di query, noto anche come Language-Integrated Query (LINQ).

Una vista sul esamina strutture ad albero di espressione, espressioni lambda e i tipi anonimi come base su cui viene costruito LINQ. Tuttavia, in entrambi i casi, in c# 3.0 presentato un concetto rivoluzionario. In c# 3.0 ha iniziato a creare i presupposti per trasformare c# in una configurazione ibrida orientato / funzionale language.

In particolare, è ora possibile scrivere SQL di tipo query dichiarative per eseguire operazioni sulle raccolte, tra l'altro. Invece di scrivere un `for` ciclo per calcolare la media di un elenco di numeri interi, è possibile ora eseguire che semplicemente come come `list.Average()`. La combinazione di espressioni di query e i metodi di estensione reso sembrano tale elenco di numeri interi ha ricevuto molto efficiente.

Impiegato tempo per le persone effettivamente afferrare e integrare il concetto, ma quanto avveniva gradualmente. E questo punto, gli anni in un secondo momento, codice è molto più rapido, semplice e funzionale.

## <a name="c-version-40"></a>In c# versione 4.0

In c# versione 4.0 avrebbe difficoltà effettivamente all'innovativo stato della versione 3.0. Con versione 3.0, c# ha spostato il linguaggio correttamente la disconnessione dall'ombreggiatura di Java e diffusione. La lingua è stata diventando elegante.

La versione successiva introdurre alcune nuove interessanti funzionalità:

- [Associazione dinamica](../language-reference/keywords/dynamic.md)
- [Argomenti denominati e facoltativi](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [Generico covariante e controvariante](../../standard/generics/covariance-and-contravariance.md)
- [Tipi di interoperabilità incorporati](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

Tipi di interoperabilità incorporati applicate a un problema di distribuzione. La controvarianza e covarianza generica offrono maggiore potenza per utilizzare i generics, ma un po' Education e probabilmente più apprezzati dagli autori di libreria e framework. Parametri denominati e facoltativi consentono di eliminare numerosi overload del metodo e fornire comodità. Ma nessuna di queste funzionalità è modifica esattamente paradigma.

La funzionalità principale è l'introduzione del `dynamic` (parola chiave). Il `dynamic` (parola chiave) introdotti in c# versione 4.0 la possibilità di sostituire il compilatore digitazione in fase di compilazione. Utilizzando la parola chiave dinamica, è possibile creare costrutti simili a tipizzati in modo dinamico i linguaggi come JavaScript. È possibile creare un `dynamic x = "a string"` e quindi aggiungere sei, lasciandolo fino al runtime di ordinare gli azione da eseguire successivamente.

Questo offre la possibilità per gli errori, ma anche grande potenza all'interno del linguaggio.

## <a name="c-version-50"></a>In c# versione 5.0

In c# versione 5.0 è una versione molto specifici della lingua. Quasi tutto l'impegno per la versione è entrato in un altro concetto di linguaggio innovativo.  Di seguito è riportato l'elenco delle caratteristiche principali:

- [Membri asincroni](../async.md)
- [Attributi informativi sul chiamante](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

L'attributo di informazioni sul chiamante consente di recuperare facilmente informazioni sul contesto in cui si esegue senza ricorrere a grandi quantità di codice di boilerplate reflection. Include molti utilizzato nella diagnostica e le attività di registrazione.

Ma `async` e `await` sono il reale di questa versione. Quando queste funzionalità in 2012, in c# modificare il gioco nuovamente incorporando modalità asincrona nel linguaggio di prima classe partecipante. Se hai mai affrontato operazioni a esecuzione prolungata e l'implementazione di siti Web di callback, molto probabilmente apprezzato questa funzionalità del linguaggio.

## <a name="c-version-60"></a>In c# versione 6.0

Con le versioni 3.0 e 5.0, in c# fossero stati aggiunti alcuni principali caratteristiche in un linguaggio orientata agli oggetti. Con la versione 6.0, sarebbe andare fuori esegue una funzionalità killer dominante e rilasciare invece molte funzionalità che gli utenti del linguaggio estremamente. Ecco alcuni di essi:

- [Importazioni statiche](../language-reference/keywords/using-static.md)
- [Filtri eccezioni](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [Inizializzatori di proprietà](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [Membri di espressioni corpo](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [Propagazione null](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [Interpolazione di stringhe](../language-reference/keywords/interpolated-strings.md)
- [operatore nameof](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [Inizializzatore di dizionario](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md)

Ognuna di queste funzionalità è interessante in sé. Ma se si osserva li tutto, viene visualizzato un modello interessano. In questa versione, in c# eliminati boilerplate di linguaggio per rendere più brevi e leggibili. Per le ventole di codice semplice, questa versione di lingua è una notevole vittoria.

Quanto avveniva un altro elemento con questa versione, se non è una funzionalità del linguaggio tradizionale in sé. Questi rilasciati [Roslyn al compilatore come un servizio](https://github.com/dotnet/roslyn). Il compilatore c# viene ora scritto in c# e come parte delle attività di programmazione è possibile utilizzare il compilatore.

## <a name="c-version-70"></a>In c# versione 7.0

La versione principale più recente è c# versione 7.0. Questa versione presenta alcune cose evolutivo e sporadico in vein di c# 6.0, ma il compilatore non come servizio. Di seguito sono riportate alcune delle nuove funzionalità:

- [Le variabili](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [Tuple e l'eliminazione](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [Criteri di ricerca](./csharp-7.md#pattern-matching)
- [Funzioni locali](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [Membri con corpo di espressione espansa](./csharp-7.md#more-expression-bodied-members)
- [Variabili locali di riferimento e restituisce](./csharp-7.md#ref-locals-and-returns)

Tutte queste caratteristiche offrono sporadico nuove funzionalità per gli sviluppatori e la possibilità di scrivere anche codice che mai. Un'evidenziazione è condensa la dichiarazione di variabili da utilizzare con il `out` (parola chiave) e consentendo a più valori restituiti tramite tupla.

Ma, in c# è richiesta put per utilizzare sempre più ampia. .NET core ora è destinato a qualsiasi sistema operativo e il relativo occhi solidamente nel cloud e sulla portabilità.  Si occupa certamente idee e l'ora, oltre a presentarsi con le nuove funzionalità degli sviluppatori del linguaggio.

_Articolo_ [ _originariamente pubblicati sul blog di NDepend_](https://blog.ndepend.com/c-versions-look-language-history/)_, gentilmente Erik Dietrich e Patrick Smacchia._

---
title: Panoramica di C# | Guida a C#
description: Introduzione a C# Informazioni di base sul linguaggio.
ms.date: 04/05/2019
ms.openlocfilehash: b510342f957a259a6c7763441778461b3dd4ef1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "77673290"
---
# <a name="a-tour-of-the-c-language"></a>Panoramica del C# linguaggio

C#, pronunciato "See Sharp", è un linguaggio di programmazione semplice, moderno, orientato a oggetti e indipendente dai tipi. C# ha le sue radici nella famiglia di linguaggi C e risulterà immediatamente familiare ai programmatori di C, C++, Java e JavaScript.

In questa presentazione viene fornita una panoramica dei componenti principali della lingua in C# 7 e versioni successive. Per esplorare il linguaggio tramite esempi interattivi, provare [a eseguire l'introduzione alle C# ](../tutorials/intro-to-csharp/index.md) esercitazioni.

C# è un linguaggio orientato a oggetti, ma include anche il supporto per la programmazione ***orientata ai componenti***. La progettazione software contemporanea è basata in misura sempre maggiore su componenti software costituiti da pacchetti di funzionalità autonomi e autodescrittivi. L'aspetto chiave di tali componenti è che presentano un modello di programmazione con proprietà, metodi ed eventi. Presentano inoltre attributi che forniscono informazioni dichiarative sul componente. Questi componenti, infine, includono la propria documentazione. C# offre costrutti di linguaggio in grado di supportare direttamente questi concetti. Per questo motivo, C# è un linguaggio estremamente naturale in cui creare e usare componenti software.

Diverse funzionalità C# offrono un valido aiuto per la creazione di applicazioni affidabili e durevoli: ***Garbage Collection*** recupera automaticamente la memoria occupata da oggetti inutilizzati non raggiungibili, la ***gestione delle eccezioni*** offre un approccio strutturato ed estendibile al rilevamento degli errori e al ripristino, mentre la progettazione del linguaggio ***indipendente dai tipi*** rende impossibili la lettura da variabili non inizializzate, l'indicizzazione delle matrici oltre i limiti delle stesse o l'esecuzione di cast di tipo non controllati.

C# presenta un ***sistema di tipi unificato***. Tutti i tipi C#, inclusi i tipi di primitiva quali `int` e `double`, ereditano da un unico tipo `object` radice. Di conseguenza, tutti i tipi condividono un set di operazioni comuni e i valori dei diversi tipi possono essere archiviati, trasportati e gestiti in modo coerente. C#, inoltre, supporta sia i tipi riferimento sia i tipi valore definiti dall'utente, consentendo l'allocazione dinamica di oggetti e l'archiviazione inline di strutture leggere.

Per garantire che C# i programmi e le librerie possano evolversi nel tempo in modo compatibile, è stato enfatizzato il ***controllo*** delle C#versioni nel progetto. Molti linguaggi di programmazione prestano scarsa attenzione a questo aspetto e, di conseguenza, i programmi scritti in tali linguaggi si interrompono molto più spesso del necessario quando vengono introdotte nuove versioni delle librerie dipendenti. Gli aspetti C#della progettazione che sono stati influenzati direttamente dalle considerazioni sul controllo delle versioni includono i modificatori `virtual` e `override` separati, le regole per la risoluzione dell'overload del metodo e il supporto per le dichiarazioni esplicite dei membri di interfaccia.

## <a name="hello-world"></a>Hello world

Il programma "Hello World" viene tradizionalmente usato per presentare un linguaggio di programmazione. Di seguito è riportato il programma Hello, World in C#:

[!code-csharp[Hello World](~/samples/snippets/csharp/tour/hello/Program.cs)]

I file di origine C# hanno in genere l'estensione `.cs`. Supponendo che il programma "Hello, World" sia archiviato nel file *Hello.cs*, è possibile che il programma venga compilato utilizzando la riga di comando:

```console
csc hello.cs
```

che produce un assembly eseguibile denominato *Hello. exe*. L'output prodotto dall'applicazione quando viene eseguita è il seguente:

```console
Hello, World
```

> [!IMPORTANT]
> Il comando `csc` compila l'intero framework ed è possibile che non sia disponibile su tutte le piattaforme.

Il programma "Hello World" inizia con una direttiva `using` che fa riferimento allo spazio dei nomi `System`. Gli spazi dei nomi consentono di organizzare i programmi e le librerie C# in modo gerarchico. Gli spazi dei nomi contengono tipi e altri spazi dei nomi. Lo stazio dei nomi `System`, ad esempio, contiene diversi tipi, come la classe `Console` a cui viene fatto riferimento nel programma, e altri spazi dei nomi, come `IO` e `Collections`. Una direttiva `using` che fa riferimento a un determinato spazio dei nomi consente l'uso non qualificato dei tipi che sono membri di tale spazio dei nomi. Grazie alla direttiva `using`, il programma può usare `Console.WriteLine` come sintassi abbreviata per `System.Console.WriteLine`.

La classe `Hello` dichiarata dal programma "Hello World" ha un solo membro, ovvero il metodo denominato `Main`. Il metodo `Main` viene dichiarato con il modificatore static. Mentre i metodi di istanza possono fare riferimento a una particolare istanza dell'oggetto contenitore usando la parola chiave `this`, i metodi statici operano senza riferimento a un determinato oggetto. Per convenzione, un metodo statico denominato `Main` funge da punto di ingresso di un programma.

L'output del programma viene prodotto dal metodo `WriteLine` della classe `Console` nello spazio dei nomi `System`. Questa classe viene fornita da librerie di classi standard a cui, per impostazione predefinita, fa automaticamente riferimento il compilatore.

## <a name="elements-of-the-c-language"></a>Elementi della C# lingua

Oltre quelli sopra riportati, rimangono da discutere altri numerosi aspetti del linguaggio C#. Gli argomenti seguenti offrono una panoramica degli elementi del linguaggio C#. Queste panoramiche forniscono informazioni di base su tutti gli elementi del linguaggio e forniscono le informazioni necessarie per approfondire la procedura:

- [Struttura del programma](program-structure.md)
  - Vengono descritti i concetti organizzativi chiave di C#: ***programmi***, ***spazi dei nomi***, ***tipi***, ***membri*** e ***assembly***.
- [Tipi e variabili](types-and-variables.md)
  - Vengono offerte informazioni sui ***tipi valore***, i ***tipi riferimento*** e le ***variabili*** del linguaggio C#.
- [Espressioni](expressions.md)
  - Le ***espressioni*** sono costituite da ***operandi*** e ***operatori*** e producono un valore.
- [Istruzioni](statements.md)
  - Le ***istruzioni*** consentono di esprimere le azioni di un programma.
- [Classi e oggetti](classes-and-objects.md)
  - Le ***classi*** sono i tipi C# più importanti. Gli ***oggetti*** sono istanze di una classe. Le classi vengono create usando ***membri***, descritti più avanti in questo argomento.
- [Array](arrays.md)
  - Una ***matrice*** è una struttura di dati contenente una serie di variabili accessibili tramite indici calcolati.
- [Interfacce](interfaces.md)
  - Un'***interfaccia*** definisce un contratto che può essere implementato da classi e struct. Può contenere metodi, proprietà, eventi e indicizzatori. Un'interfaccia non fornisce le implementazioni dei membri che definisce, ma specifica semplicemente i membri che devono essere forniti dalle classi o dai tipi struct che la implementano.
- [Delegati](delegates.md)
  - Un ***tipo delegato*** rappresenta riferimenti ai metodi con un elenco di parametri e un tipo restituito particolari. I delegati consentono di trattare i metodi come entità che è possibile assegnare a variabili e passare come parametri. I delegati sono simili al concetto di puntatori a funzione disponibili in altri linguaggi. A differenza dei puntatori a funzione, tuttavia, i delegati sono orientati agli oggetti e indipendenti dai tipi.
- [Attributi](attributes.md)
  - Gli ***attributi*** consentono ai programmi di specificare informazioni dichiarative aggiuntive sui tipi, i membri e altre entità.
  
> [!NOTE]
> Questi articoli si applicano a C# 7,0 e versioni successive. Alcune funzionalità potrebbero non essere disponibili nelle versioni precedenti.

> [!div class="step-by-step"]
> [avanti](program-structure.md)

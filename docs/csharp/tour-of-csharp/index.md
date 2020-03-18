---
title: Panoramica di C# | Guida a C#
description: Introduzione a C# Informazioni di base sul linguaggio.
ms.date: 02/26/2020
ms.openlocfilehash: bf5a200f2ee777698ae8564f348ffc117d9abab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79156844"
---
# <a name="a-tour-of-the-c-language"></a>Presentazione del linguaggio C

Il linguaggio di programmazione c'è (pronunciato "See Sharp") è un linguaggio di programmazione moderno, orientato agli oggetti e indipendente dai tipi. C# ha le sue radici nella famiglia di linguaggi C e risulterà immediatamente familiare ai programmatori di C, C++, Java e JavaScript.

In questa presentazione viene fornita una panoramica dei componenti principali del linguaggio in C . Se si vuole esplorare il linguaggio tramite esempi interattivi, provare a [eseguire l'introduzione alle](../tutorials/intro-to-csharp/index.md) esercitazioni di C.

C# è un linguaggio orientato a oggetti, ma include anche il supporto per la programmazione ***orientata ai componenti***. La progettazione software contemporanea è basata in misura sempre maggiore su componenti software costituiti da pacchetti di funzionalità autonomi e autodescrittivi. La chiave per tali componenti è che presentano un modello di programmazione con proprietà, metodi ed eventi. Hanno attributi che forniscono informazioni dichiarative sul componente. Essi incorporano la propria documentazione. In Cè sono disponibili costrutti di linguaggio per supportare direttamente questi concetti, rendendo C ' un linguaggio naturale in cui creare e utilizzare i componenti software.

Diverse funzionalità di C, facilitano la costruzione di applicazioni robuste e durevoli. ***Garbage Collection*** recupera automaticamente la memoria occupata da oggetti inutilizzati non raggiungibili. ***La gestione delle eccezioni*** fornisce un approccio strutturato ed estensibile per il rilevamento e il ripristino degli errori. La progettazione ***indipendente*** dai tipi del linguaggio rende impossibile la lettura da variabili non inizializzate, per indicizzare matrici oltre i relativi limiti o per eseguire cast di tipo non controllati.

C# presenta un ***sistema di tipi unificato***. Tutti i tipi C#, inclusi i tipi di primitiva quali `int` e `double`, ereditano da un unico tipo `object` radice. Di conseguenza, tutti i tipi condividono un set di operazioni comuni e i valori dei diversi tipi possono essere archiviati, trasportati e gestiti in modo coerente. C#, inoltre, supporta sia i tipi riferimento sia i tipi valore definiti dall'utente, consentendo l'allocazione dinamica di oggetti e l'archiviazione inline di strutture leggere.

Per garantire che i programmi e le librerie di C' possano evolvere nel tempo in modo compatibile, è stata posta molta enfasi sul ***controllo delle versioni*** nella progettazione di C. Molti linguaggi di programmazione prestano poca attenzione a questo problema. Di conseguenza, i programmi scritti in altre lingue si interrompono più spesso del necessario quando vengono introdotte versioni più recenti delle librerie dipendenti. Gli aspetti della progettazione di C, che sono stati `virtual` direttamente `override` influenzati da considerazioni sul controllo delle versioni, includono i modificatori e separati, le regole per la risoluzione dell'overload del metodo e il supporto per le dichiarazioni esplicite dei membri di interfaccia.

Nelle versioni più recenti, il linguaggio Cè ha adottato altri paradigmi di programmazione. In Cè sono incluse funzionalità che supportano tecniche di programmazione funzionale come le espressioni lambda. Altre nuove funzionalità supportano la separazione di dati e algoritmi, ad esempio pattern matching.

## <a name="hello-world"></a>Hello World

Il programma "Hello World" viene tradizionalmente usato per presentare un linguaggio di programmazione. Di seguito è riportato il programma Hello, World in C#:

[!code-csharp[Hello World](~/samples/snippets/csharp/tour/hello/Program.cs)]

I file di origine C# hanno in genere l'estensione `.cs`. Per creare questo programma, scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download). Quindi, eseguire `dotnet new console -o hello` il comando per creare un nuovo programma e uno script di compilazione. Il programma e lo script `Program.cs` `hello.csproj`di compilazione si trovano rispettivamente nei file e , . Compilare ed eseguire l'applicazione con i comandi seguenti:Build and run the application with the `run` commands:

```dotnetcli
cd hello
dotnet run
```

Il programma produce l'output seguente:

```console
Hello, World!
```

Il programma "Hello World" inizia con una direttiva `using` che fa riferimento allo spazio dei nomi `System`. Gli spazi dei nomi consentono di organizzare i programmi e le librerie C# in modo gerarchico. Gli spazi dei nomi contengono tipi e altri spazi dei nomi. Lo stazio dei nomi `System`, ad esempio, contiene diversi tipi, come la classe `Console` a cui viene fatto riferimento nel programma, e altri spazi dei nomi, come `IO` e `Collections`. Una direttiva `using` che fa riferimento a un determinato spazio dei nomi consente l'uso non qualificato dei tipi che sono membri di tale spazio dei nomi. Grazie alla direttiva `using`, il programma può usare `Console.WriteLine` come sintassi abbreviata per `System.Console.WriteLine`.

La classe `Hello` dichiarata dal programma "Hello World" ha un solo membro, ovvero il metodo denominato `Main`. Il metodo `Main` viene dichiarato con il modificatore static. Mentre i metodi di istanza possono fare riferimento a una particolare istanza dell'oggetto contenitore usando la parola chiave `this`, i metodi statici operano senza riferimento a un determinato oggetto. Per convenzione, un metodo statico denominato `Main` funge da punto di ingresso di un programma.

L'output del programma viene prodotto dal metodo `WriteLine` della classe `Console` nello spazio dei nomi `System`. Questa classe viene fornita da librerie di classi standard a cui, per impostazione predefinita, fa automaticamente riferimento il compilatore.

## <a name="elements-of-the-c-language"></a>Elementi del linguaggio C

Oltre quelli sopra riportati, rimangono da discutere altri numerosi aspetti del linguaggio C#. Gli argomenti seguenti offrono una panoramica degli elementi del linguaggio C#. Queste panoramiche forniscono informazioni di base su tutti gli elementi del linguaggio e forniscono le informazioni necessarie per immergersi più a fondo:

- [Struttura del programma](program-structure.md)
  - Vengono descritti i concetti organizzativi chiave di C#: ***programmi***, ***spazi dei nomi***, ***tipi***, ***membri*** e ***assembly***.
- [Tipi e variabili](types-and-variables.md)
  - Vengono offerte informazioni sui ***tipi valore***, i ***tipi riferimento*** e le ***variabili*** del linguaggio C#.
- [Espressioni](expressions.md)
  - Le ***espressioni*** sono costituite da ***operandi*** e ***operatori***. e producono un valore.
- [Istruzioni](statements.md)
  - Le ***istruzioni*** consentono di esprimere le azioni di un programma.
- [Classi e oggetti](classes-and-objects.md)
  - ***Le classi*** sono la più fondamentale dei tipi di C. Gli ***oggetti*** sono istanze di una classe. Le classi vengono create usando ***membri***, descritti più avanti in questo argomento.
- [Matrici](arrays.md)
  - Una ***matrice*** è una struttura di dati contenente una serie di variabili accessibili tramite indici calcolati.
- [Interfacce](interfaces.md)
  - Un'***interfaccia*** definisce un contratto che può essere implementato da classi e struct. Può contenere metodi, proprietà, eventi e indicizzatori. Un'interfaccia non fornisce implementazioni dei membri che definisce, ma specifica semplicemente i membri che devono essere forniti da classi o struct che implementano l'interfaccia.
- [Delegati](delegates.md)
  - Un ***tipo delegato*** rappresenta riferimenti ai metodi con un elenco di parametri e un tipo restituito particolari. I delegati consentono di trattare i metodi come entità che è possibile assegnare a variabili e passare come parametri. I delegati sono simili al concetto di puntatori a funzione disponibili in altri linguaggi. A differenza dei puntatori a funzione, tuttavia, i delegati sono orientati agli oggetti e indipendenti dai tipi.
- [Attributi](attributes.md)
  - Gli ***attributi*** consentono ai programmi di specificare informazioni dichiarative aggiuntive sui tipi, i membri e altre entità.
  
> [!NOTE]
> Questi articoli si applicano a C .NET 7.0 e versioni successive. Alcune funzioni potrebbero non essere disponibili nelle versioni precedenti.

> [!div class="step-by-step"]
> [Avanti](program-structure.md)

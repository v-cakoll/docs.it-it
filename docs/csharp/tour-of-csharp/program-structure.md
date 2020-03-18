---
title: Struttura del programma C# - Panoramica del linguaggio C#
description: Informazioni sui blocchi predefiniti di un programma C#
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c09c11a4dd957b29b2adb7aaa8d68a50f30620b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156831"
---
# <a name="program-structure"></a>Struttura del programma

I concetti organizzativi chiave di C# sono i ***programmi***, gli ***spazi dei nomi***, i ***tipi***, i ***membri*** e gli ***assembly***. I programmi C# sono costituiti da uno o più file di origine. I programmi dichiarano i tipi, che contengono i membri e possono essere organizzati in spazi dei nomi. Le classi e le interfacce sono esempi di tipi. I campi, i metodi, le proprietà e gli eventi sono esempi di membri. Quando vengono compilati i programmi di C, vengono fisicamente inclusi nel pacchetto in assembly. Gli assembly in genere hanno l'estensione `.exe` o `.dll`, a seconda che implementino rispettivamente ***applicazioni*** o ***librerie***.

È possibile creare un progetto di `dotnet new` libreria denominato *acme* utilizzando il comando:

```console
dotnet new classlib -o acme
```

In tale progetto dichiarare `Stack` una classe `Acme.Collections`denominata in uno spazio dei nomi denominato :

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

Il nome completo di questa classe è `Acme.Collections.Stack`. La classe contiene vari membri: un campo `top`, due metodi `Push` e `Pop` e una classe annidata `Entry`. La classe `Entry` contiene altri tre membri: un campo `next`, un campo `data` e un costruttore. Il comando:

```console
dotnet build
```

compila l'esempio come libreria (codice senza un punto di ingresso `Main`) e genera un assembly denominato `acme.dll`.

Gli assembly contengono codice eseguibile sotto forma di istruzioni di linguaggio intermedio (Intermediate Language, IL) e informazioni simboliche sotto forma di metadati. Prima dell'esecuzione, il compilatore JIT (Just-In-Time) di .NET Common Language Runtime converte il codice IL in un assembly in codice specifico del processore.

Poiché un assembly è un'unità di funzionalità autodescrittiva che `#include` contiene sia codice che metadati, non è necessario che le direttive e i file di intestazione siano presenti in C. I membri e i tipi pubblici contenuti in un determinato assembly vengono resi disponibili in un programma C# semplicemente facendo riferimento a tale assembly durante la compilazione del programma. Questo programma usa ad esempio la classe `Acme.Collections.Stack` dell'assembly `acme.dll`:

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

Il file *csproj* per il progetto del programma precedente deve includere un nodo di riferimento `acme.dll` per il compilatore C , per risolvere i riferimenti alle classi nell'assembly:

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

Dopo tale `dotnet build` addizione, `example.exe`viene creato un assembly eseguibile denominato , che, quando eseguito, produce l'output:

```console
100
10
1
```

C# consente di archiviare il testo di origine di un programma in vari file di origine. Quando viene compilato un programma C# costituito da più file, tutti i file di origine vengono elaborati insieme e possono fare riferimento l'uno all'altro. A livello concettuale è come se tutti i file di origine fossero concatenati in un unico grande file prima di essere elaborati. Le dichiarazioni con prototipo non sono mai necessarie in C, perché, con poche eccezioni, l'ordine di dichiarazione è insignificante. C# non limita un file di origine alla dichiarazione di un solo tipo pubblico e non richiede che il nome del file di origine corrisponda a un tipo dichiarato nel file di origine.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](types-and-variables.md)

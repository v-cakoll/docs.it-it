---
title: Introduzione a .NET Core con l'interfaccia della riga di comando-interfaccia della riga di comando di .NET Core
description: Esercitazione dettagliata che illustra come iniziare a usare .NET Core in Windows, Linux o macOS con l'interfaccia della riga di comando (CLI) di .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: seodec18,updateeachrelease
ms.openlocfilehash: 4c6a8e495d8532a0ab2e90368663a287731a9af0
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884277"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Introduzione all'uso di .NET Core su Windows/Linux/macOS dalla riga di comando

Questo articolo illustra come iniziare a sviluppare app multipiattaforma nel computer usando gli strumenti interfaccia della riga di comando di .NET Core.

Se non si ha familiarità con il set di strumenti dell'interfaccia della riga di comando di .NET Core, leggere [Panoramica di .NET Core SDK](../tools/index.md).

## <a name="prerequisites"></a>Prerequisites

- [.NET Core SDK 3,1](https://dotnet.microsoft.com/download) o versioni successive.
- Editor di testo o editor di codice a scelta.

## <a name="hello-console-app"></a>Creazione di un'applicazione console

È possibile [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) dal repository GitHub dotnet/samples. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Aprire un prompt dei comandi e creare una cartella denominata *Hello*. Passare alla cartella creata e digitare:

```dotnetcli
dotnet new console
dotnet run
```

Ecco una descrizione rapida dei comandi digitati:

01. `dotnet new console`

    [DotNet New](../tools/dotnet-new.md) crea un file di progetto *Hello. csproj* aggiornato con le dipendenze necessarie per compilare un'app console. Viene inoltre creato un *Program.cs*, un file di base contenente il punto di ingresso per l'applicazione.
    
    *Hello. csproj*:
    
    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]
    
    Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.
    
    - L'elemento `<OutputType>` specifica che si sta compilando un eseguibile, in altre parole un'applicazione console.
    - L'elemento `<TargetFramework>` specifica l'implementazione di .NET di destinazione. In uno scenario avanzato è possibile specificare più framework di destinazione ed eseguire la compilazione per ognuno di essi in un'unica operazione. In questa esercitazione verrà illustrata la compilazione solo per .NET Core 3,1.
    
    *Program.cs*:
    
    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]
    
    Il programma inizia con `using System`, che significa "porta tutti gli elementi presenti nello spazio dei nomi `System` nell'ambito relativo a questo file". Lo spazio dei nomi `System` include la classe `Console`.
    
    Viene quindi definito uno spazio dei nomi denominato `Hello`. È comunque possibile modificare il nome secondo le proprie esigenze. Una classe denominata `Program` viene definita all'interno di tale spazio dei nomi, con un `Main` metodo che accetta una matrice di stringhe denominate `args`. Questa matrice contiene l'elenco degli argomenti passati durante l'esecuzione del programma. Così com'è, questa matrice non viene utilizzata e il programma scrive semplicemente il testo "Hello World!" nella console. Successivamente saranno apportate modifiche al codice che userà tale argomento.
    
    `dotnet new` chiama [DotNet Restore](../tools/dotnet-restore.md) in modo implicito. `dotnet restore` chiama [NuGet](https://www.nuget.org/) (gestione dei pacchetti per .NET) per ripristinare l'albero delle dipendenze. NuGet analizza il file *Hello.csproj*, scarica le dipendenze definite nel file (o le recupera da una cache nel computer) e scrive il file *obj/project.assets.json*, che è necessario compilare ed eseguire l'esempio.

02. `dotnet run`

    [DotNet Run](../tools/dotnet-run.md) chiama [DotNet Build](../tools/dotnet-build.md) per assicurarsi che le destinazioni di compilazione siano state compilate e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione di destinazione.
    
    ```console
    dotnet run

    Hello World!
    ```
    
    In alternativa, è anche possibile eseguire `dotnet build` per compilare il codice senza eseguire le applicazioni della console di compilazione. In questo modo si ottiene un'applicazione compilata, come file DLL, in base al nome del progetto. In questo caso, il file creato viene denominato *Hello. dll*. Questa app può essere eseguita con `dotnet bin\Debug\netcoreapp3.1\Hello.dll` in Windows (usare `/` per i sistemi non Windows).
    
    ```console
    dotnet bin\Debug\netcoreapp3.1\Hello.dll

    Hello World!
    ```
    
    Quando l'app viene compilata, viene creato un file eseguibile specifico del sistema operativo insieme al `Hello.dll`. In Windows, questo sarebbe `Hello.exe`; in Linux o macOS questo `hello`. Con l'esempio precedente, il nome del file è `Hello.exe` o `Hello`. È possibile eseguire direttamente l'eseguibile.

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a>Modificare il programma

Modificare la logica di programma. I numeri di Fibonacci sono divertenti, quindi è possibile aggiungerli e usare l'argomento per accogliere la persona che esegue l'app.

01. Sostituire il contenuto del file *Program.cs* con il codice seguente:

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. Eseguire [DotNet Build](../tools/dotnet-build.md) per compilare le modifiche.

03. Eseguire il programma passando un parametro all'app. Quando si usa il comando `dotnet` per eseguire un'app, aggiungere `--` alla fine. Qualsiasi elemento a destra di `--` verrà passato come parametro all'app. Nell'esempio seguente il valore `John` viene passato all'app.

    ```console
    $ dotnet run -- John
    Hello John!
    Fibonacci Numbers 1-15:
    1: 0
    2: 1
    3: 1
    4: 2
    5: 3
    6: 5
    7: 8
    8: 13
    9: 21
    10: 34
    11: 55
    12: 89
    13: 144
    14: 233
    15: 377
    ```

L'operazione è ora completata. È possibile modificare *Program.cs* in qualsiasi modo.

## <a name="working-with-multiple-files"></a>Uso di più file

I singoli file sono buoni per i semplici programmi One-off, ma se si crea un'app più complessa, probabilmente si avranno più file di codice nel progetto. Verrà ora sviluppato il precedente esempio di Fibonacci memorizzando nella cache alcuni valori di Fibonacci e verranno aggiunte alcune funzionalità ricorsive.

01. Aggiungere un nuovo file nella directory *Hello* denominato *FibonacciGenerator.cs* con il codice seguente:

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. Modificare il metodo `Main` del file *Program.cs* per creare un'istanza della nuova classe e chiamare il metodo come illustrato nell'esempio seguente :

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. Eseguire [DotNet Build](../tools/dotnet-build.md) per compilare le modifiche.

04. Eseguire l'app eseguendo [DotNet Run](../tools/dotnet-run.md). Di seguito viene illustrato l'output del programma:

    ```console
    $ dotnet run
    0
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55
    89
    144
    233
    377
    ```

## <a name="publish-your-app"></a>Pubblicare l'app

Quando si è pronti per distribuire l'applicazione, usare il comando [DotNet Publish](../tools/dotnet-publish.md) per generare la cartella di _pubblicazione_ in _bin\\debug\\netcoreapp 3.1\\Publish\\_ (usare `/` per i sistemi non Windows). È possibile distribuire il contenuto della cartella _publish_ su altre piattaforme purché sia già stato installato il runtime dotnet.

```console
dotnet publish
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

L'output precedente può variare in base alla cartella corrente e al sistema operativo, ma l'output dovrebbe essere simile.

È possibile eseguire l'app pubblicata con il comando [dotnet](../tools/dotnet.md):

```console
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll

Hello World!
```

Come indicato all'inizio di questo articolo, è stato creato un file eseguibile specifico del sistema operativo insieme al `Hello.dll`. In Windows, questo sarebbe `Hello.exe`; in Linux o macOS questo `hello`. Con l'esempio precedente, il nome del file è `Hello.exe` o `Hello`. È possibile eseguire direttamente questo eseguibile pubblicato.

```console
.\bin\Debug\netcoreapp3.1\Hello.exe

Hello World!
```

## <a name="conclusion"></a>Conclusione

L'operazione è ora completata. A questo punto, è possibile usare i concetti di base per creare programmi personalizzati.

## <a name="see-also"></a>Vedere anche

- [Organizing and testing projects with the .NET Core CLI tools](testing-with-cli.md) (Organizzazione e test di progetti con gli strumenti dell'interfaccia della riga di comando di .NET Core)
- [Pubblicare le app .NET Core con l'interfaccia della riga di comando](../deploying/deploy-with-cli.md)
- [Altre informazioni sulla distribuzione delle app](../deploying/index.md)

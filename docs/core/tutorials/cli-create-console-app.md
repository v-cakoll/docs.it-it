---
title: Introduzione all'uso di .NET Core con l'interfaccia della riga di comando
description: A step-by-step tutorial showing how to get started with .NET Core on Windows, Linux, or macOS using the .NET Core CLI.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: fe69521a6ac88055e3e8c8502a7e19a72667dbef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240857"
---
# <a name="get-started-with-net-core-using-the-net-core-cli"></a>Introduzione a .NET Core con l'interfaccia della riga di comando di .NET Core

Questo articolo illustra come iniziare a sviluppare app .NET Core che funzionano in Windows, Linux e macOS usando l'interfaccia della riga di comando di .NET Core.

Se non si ha familiarità con l'interfaccia della riga di comando di .NET Core, vedere [panoramica dell'interfaccia](../tools/index.md)della riga di comando di .NET Core .

## <a name="prerequisites"></a>Prerequisites

- [.NET Core SDK 3.1](https://dotnet.microsoft.com/download) o versioni successive.
- Un editor di testo o editor di codice di propria scelta.

## <a name="hello-console-app"></a>Creazione di un'applicazione console

È possibile [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) dal repository GitHub dotnet/samples. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Aprire un prompt dei comandi e creare una cartella denominata *Hello*. Passare alla cartella creata e digitare quanto segue.

```dotnetcli
dotnet new console
dotnet run
```

Ecco una descrizione rapida dei comandi digitati:

01. `dotnet new console`

    [dotnet new](../tools/dotnet-new.md) crea un file di progetto *Hello.csproj* aggiornato con le dipendenze necessarie per compilare un'app console. Crea inoltre un *Program.cs,* un file di base contenente il punto di ingresso per l'applicazione.

    *Hello.csproj*:

    [!code-xml[Hello.csproj](~/samples/snippets/core/tutorials/cli-create-console-app/HelloMsBuild/csharp/Hello.csproj)]

    Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.

    - L'elemento `<OutputType>` specifica che stiamo compilando un eseguibile, in altre parole un'applicazione console.
    - L'elemento `<TargetFramework>` specifica l'implementazione di .NET di destinazione. In uno scenario avanzato è possibile specificare più framework di destinazione ed eseguire la compilazione per ognuno di essi in un'unica operazione. In questa esercitazione verrà esibiscere la compilazione solo per .NET Core 3.1.In this tutorial, we'll stick to building only for .NET Core 3.1.

    *Program.cs*:

    [!code-csharp[Program.cs](~/samples/snippets/core/tutorials/cli-create-console-app/HelloMsBuild/csharp/Program.cs)]

    Il programma inizia con `using System`, che significa "porta tutti gli elementi presenti nello spazio dei nomi `System` nell'ambito relativo a questo file". Lo `System` spazio `Console` dei nomi include la classe .

    Viene quindi definito uno spazio dei nomi denominato `Hello`. È comunque possibile modificare il nome secondo le proprie esigenze. Una classe `Program` denominata viene definita `Main` all'interno di tale `args`spazio dei nomi, con un metodo che accetta una matrice di stringhe denominata . Questa matrice contiene l'elenco di argomenti passati quando viene eseguito il programma. Così com'è, questa matrice non viene utilizzata e il programma scrive semplicemente il testo "Hello World!" nella console. Successivamente saranno apportate modifiche al codice che userà tale argomento.

    `dotnet new`chiamate [dotnet ripristinare](../tools/dotnet-restore.md) in modo implicito. `dotnet restore` chiama [NuGet](https://www.nuget.org/) (gestione dei pacchetti per .NET) per ripristinare l'albero delle dipendenze. NuGet analizza il file *Hello.csproj*, scarica le dipendenze definite nel file (o le recupera da una cache nel computer) e scrive il file *obj/project.assets.json*, che è necessario compilare ed eseguire l'esempio.

02. `dotnet run`

    [dotnet esegue](../tools/dotnet-run.md) chiamate [dotnet build](../tools/dotnet-build.md) per assicurarsi che le `dotnet <assembly.dll>` destinazioni di compilazione siano state compilate e quindi chiamate per eseguire l'applicazione di destinazione.

    ```dotnetcli
    dotnet run
    ```

    Viene visualizzato il seguente output.

    ```console
    Hello World!
    ```

    In alternativa, è `dotnet build` anche possibile eseguire per compilare il codice senza eseguire le applicazioni console di compilazione. Il risultato è un'applicazione compilata, come file DLL, in base al nome del progetto. In questo caso, il file creato è denominato *Hello.dll*. Questa applicazione può `dotnet bin\Debug\netcoreapp3.1\Hello.dll` essere eseguita `/` con su Windows (utilizzare per i sistemi non Windows).

    ```dotnetcli
    dotnet bin\Debug\netcoreapp3.1\Hello.dll
    ```

    Viene visualizzato il seguente output.

    ```console
    Hello World!
    ```

    Quando l'app viene compilata, è stato creato `Hello.dll`un eseguibile specifico del sistema operativo insieme al file . Su Windows, questo `Hello.exe`sarebbe ; su Linux o macOS, `hello`questo sarebbe . Con l'esempio precedente, il `Hello.exe` `Hello`file viene denominato con o . È possibile eseguire direttamente l'eseguibile.

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a>Modificare il programma

Modificare la logica di programma. I numeri di Fibonacci sono divertenti, quindi aggiungiamolo e anche di usare l'argomento per salutare la persona che esegue l'app.

01. Sostituire il contenuto del file *Program.cs* con il codice seguente:

    [!code-csharp[Fibonacci](~/samples/snippets/core/tutorials/cli-create-console-app/fibonacci-msbuild/csharp/Program.cs)]

02. Eseguire [dotnet build](../tools/dotnet-build.md) per compilare le modifiche.

03. Eseguire il programma passando un parametro all'app. Quando si `dotnet` utilizza il comando per `--` eseguire un'app, aggiungerla alla fine. Qualsiasi elemento a `--` destra di verrà passato come parametro all'app. Nell'esempio seguente, `John` il valore viene passato all'app.

    ```dotnetcli
    dotnet run -- John
    ```

    Viene visualizzato il seguente output.

    ```console
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

L'attività è terminata. È possibile modificare *Program.cs* in qualsiasi modo desiderato.

## <a name="working-with-multiple-files"></a>Uso di più file

I singoli file vanno bene per semplici programmi una tantum, ma se stai creando un'app più complessa, probabilmente avrai più file di codice sul tuo progetto. Verrà ora sviluppato il precedente esempio di Fibonacci memorizzando nella cache alcuni valori di Fibonacci e verranno aggiunte alcune funzionalità ricorsive.

01. Aggiungere un nuovo file nella directory *Hello* denominato *FibonacciGenerator.cs* con il codice seguente:

    [!code-csharp[Fibonacci Generator](~/samples/snippets/core/tutorials/cli-create-console-app/FibonacciBetterMsBuild/csharp/FibonacciGenerator.cs)]

02. Modificare il metodo `Main` del file *Program.cs* per creare un'istanza della nuova classe e chiamare il metodo come illustrato nell'esempio seguente :

    [!code-csharp[New Program.cs](~/samples/snippets/core/tutorials/cli-create-console-app/FibonacciBetterMsBuild/csharp/Program.cs)]

03. Eseguire [dotnet build](../tools/dotnet-build.md) per compilare le modifiche.

04. Eseguire l'app eseguendo [dotnet run](../tools/dotnet-run.md).

    ```dotnetcli
    dotnet run
    ```

    Viene visualizzato il seguente output.

    ```console
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

Quando sei pronto a distribuire l'app, usa il comando [dotnet publish](../tools/dotnet-publish.md) per generare la `/` cartella di _pubblicazione_ in _bin\\debug\\netcoreapp3.1\\publish\\ _ (usare per sistemi non Windows). È possibile distribuire il contenuto della cartella _publish_ su altre piattaforme purché sia già stato installato il runtime dotnet.

```dotnetcli
dotnet publish
```

Si ottiene un output simile al seguente.

```console
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

L'output precedente può variare in base alla cartella corrente e al sistema operativo, ma l'output dovrebbe essere simile.

È possibile eseguire l'app pubblicata con il comando [dotnet](../tools/dotnet.md):

```dotnetcli
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll
```

Viene visualizzato il seguente output.

```console
Hello World!
```

Come accennato all'inizio di questo articolo, è stato `Hello.dll`creato un eseguibile specifico del sistema operativo insieme al file . Su Windows, questo `Hello.exe`sarebbe ; su Linux o macOS, `hello`questo sarebbe . Con l'esempio precedente, il `Hello.exe` `Hello`file viene denominato con o . È possibile eseguire direttamente questo eseguibile pubblicato.

```console
.\bin\Debug\netcoreapp3.1\publish\Hello.exe

Hello World!
```

## <a name="conclusion"></a>Conclusioni

L'attività è terminata. A questo punto, è possibile usare i concetti di base per creare programmi personalizzati.

## <a name="see-also"></a>Vedere anche

- [Organizzazione e test di progetti con l'interfaccia della riga di comando di .NET Core](testing-with-cli.md)
- [Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET CorePublish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md)
- [Distribuzione di applicazioni .NET Core](../deploying/index.md)

---
title: Introduzione all'uso di .NET Core con l'interfaccia della riga di comando
description: Esercitazione dettagliata che illustra come iniziare a usare .NET Core in Windows, Linux o macOS con l'interfaccia della riga di comando (CLI) di .NET Core.
author: cartermp
ms.date: 09/10/2018
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: 92ca5149ad5f0e4a50c809a316123fbf77d4152d
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545364"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Introduzione all'uso di .NET Core su Windows/Linux/macOS dalla riga di comando

Questo argomento illustra come iniziare a sviluppare app multipiattaforma nel computer usando gli strumenti dell'interfaccia della riga di comando di .NET Core.

Se non si ha familiarità con il set di strumenti dell'interfaccia della riga di comando di .NET Core, leggere [Panoramica di .NET Core SDK](../tools/index.md).

## <a name="prerequisites"></a>Prerequisiti

- [.NET Core SDK 2.1](https://www.microsoft.com/net/download/core).
- Editor di testo o editor di codice a scelta.

## <a name="hello-console-app"></a>Creazione di un'applicazione console

È possibile [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) dal repository GitHub dotnet/samples. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Aprire un prompt dei comandi e creare una cartella denominata *Hello*. Passare alla cartella creata e digitare:

```console
dotnet new console
dotnet run
```

Ecco una descrizione rapida dei comandi digitati:

1. `dotnet new console`

   [`dotnet new`](../tools/dotnet-new.md) crea un file di progetto `Hello.csproj` aggiornato con le dipendenze necessarie per compilare un'applicazione console.  Crea inoltre un file `Program.cs` di base contenente il punto di ingresso per l'applicazione.

   `Hello.csproj`:

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.

   * Il tag `OutputType` specifica che si sta compilando un file eseguibile, ovvero un'applicazione console.
   * Il tag `TargetFramework` specifica l'implementazione di .NET di destinazione. In uno scenario avanzato è possibile specificare più framework di destinazione ed eseguire la compilazione per ognuno di essi in un'unica operazione. In questa esercitazione verrà illustrata la procedura di compilazione solo per .NET Core 2.1.

   `Program.cs`:

   [!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]

   Il programma inizia con `using System`, che significa "porta tutti gli elementi presenti nello spazio dei nomi `System` nell'ambito relativo a questo file". Lo spazio dei nomi `System` include costrutti di base come `string` o tipi numerici.

   Viene quindi definito uno spazio dei nomi denominato `Hello`. È comunque possibile modificare il nome secondo le proprie esigenze. All'interno dello spazio dei nomi viene definita una classe denominata `Program` con un metodo `Main` che accetta come argomento una matrice di stringhe. Tale matrice contiene l'elenco degli argomenti passati nel momento in cui viene chiamato il programma compilato. Così com'è, questa matrice non viene usata: il programma, infatti, si limita a scrivere "Hello World!" nella console. Successivamente saranno apportate modifiche al codice che userà tale argomento.

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   `dotnet new` chiama [`dotnet restore`](../tools/dotnet-restore.md) in modo implicito. `dotnet restore` chiama [NuGet](https://www.nuget.org/) (gestione dei pacchetti per .NET) per ripristinare l'albero delle dipendenze. NuGet analizza il file *Hello.csproj*, scarica le dipendenze definite nel file (o le recupera da una cache nel computer) e scrive il file *obj/project.assets.json*, che è necessario compilare ed eseguire l'esempio.

   > [!IMPORTANT]
   > Se si usa una versione .NET Core 1.x dell'SDK, è possibile chiamare `dotnet restore` autonomamente dopo la chiamata di `dotnet new`.

2. `dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) chiama [`dotnet build`](../tools/dotnet-build.md) per assicurarsi che le destinazioni siano state compilate e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione di destinazione.

    ```console
    $ dotnet run
    Hello World!
    ```

    In alternativa, è possibile eseguire [`dotnet build`](../tools/dotnet-build.md) per compilare il codice senza eseguire la compilazione di applicazioni console. In questo modo si ottiene un'applicazione compilata come file DLL che può essere eseguita con `dotnet bin\Debug\netcoreapp2.1\Hello.dll` in Windows (usare `/` per sistemi diversi da Windows). È anche possibile specificare argomenti per l'applicazione come verrà illustrato più avanti nell'argomento.

    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    Come scenario avanzato, è possibile compilare l'applicazione come un set indipendente di file specifici della piattaforma che può essere distribuito ed eseguito anche in computer in cui non è installato .NET Core. Per informazioni dettagliate, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).

### <a name="augmenting-the-program"></a>Possibilità di espansione del programma

Modificare la logica di programma. I numeri di Fibonacci sono molto divertenti e possono essere aggiunti insieme all'argomento per dare il benvenuto all'utente che esegue l'app.

1. Sostituire il contenuto del file *Program.cs* con il codice seguente:

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. Eseguire [`dotnet build`](../tools/dotnet-build.md) per compilare le modifiche.

3. Eseguire il programma passando un parametro all'app:

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

L'operazione è ora completata.  `Program.cs` offre innumerevoli possibilità di espansione.

## <a name="working-with-multiple-files"></a>Uso di più file

Per singoli programmi basilari è possibile usare un singolo file, ma se si sta compilando un'app più complessa, il progetto conterrà probabilmente più file di origine.
Verrà ora sviluppato il precedente esempio di Fibonacci memorizzando nella cache alcuni valori di Fibonacci e verranno aggiunte alcune funzionalità ricorsive.

1. Aggiungere un nuovo file nella directory *Hello* denominato *FibonacciGenerator.cs* con il codice seguente:

   [!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. Modificare il metodo `Main` del file *Program.cs* per creare un'istanza della nuova classe e chiamare il metodo come illustrato nell'esempio seguente :

   [!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. Eseguire [`dotnet build`](../tools/dotnet-build.md) per compilare le modifiche.

4. Avviare l'app eseguendo [`dotnet run`](../tools/dotnet-run.md). Di seguito viene illustrato l'output del programma:

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

L'operazione è ora completata. A questo punto, è possibile usare i concetti di base per creare programmi personalizzati.

Si noti che i comandi e i passaggi illustrati in questa esercitazione per eseguire l'applicazione vengono usati solo durante la fase di sviluppo. Quando si è pronti a distribuire l'app, è opportuno esaminare le diverse [strategie di distribuzione](../deploying/index.md) per le app .NET Core e il comando [`dotnet publish`](../tools/dotnet-publish.md).

## <a name="see-also"></a>Vedere anche

- [Organizing and testing projects with the .NET Core CLI tools](testing-with-cli.md) (Organizzazione e test di progetti con gli strumenti dell'interfaccia della riga di comando di .NET Core)

---
title: Creare una libreria di classi .NET Standard usando Visual Studio Code
description: Informazioni su come creare una libreria di classi .NET Standard usando Visual Studio Code.
ms.date: 06/08/2020
ms.openlocfilehash: 714b5cf2125f1d296adc4a4dc7d1b6c9420417ed
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308884"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-code"></a>Esercitazione: creare una libreria di .NET Standard usando Visual Studio Code

In questa esercitazione si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe. Viene implementato come metodo di [estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md) in modo che sia possibile chiamarlo come se fosse un membro della <xref:System.String> classe.

La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione. Una libreria di classi destinata a .NET Standard 2,0 consente la chiamata della libreria da qualsiasi implementazione di .NET che supporti tale versione di .NET Standard. Una volta completata la libreria di classi, è possibile distribuirla come componente di terze parti o come componente in bundle con una o più applicazioni.

## <a name="prerequisites"></a>Prerequisiti

1. [Visual Studio Code](https://code.visualstudio.com/) con l' [estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installata. Per informazioni su come installare le estensioni in Visual Studio Code, vedere [vs code Marketplace di estensione](https://code.visualstudio.com/docs/editor/extension-gallery).
2. [.NET Core 3,1 SDK o versione successiva](https://dotnet.microsoft.com/download)

## <a name="create-a-solution"></a>Creare una soluzione

Iniziare creando una soluzione vuota in cui inserire il progetto libreria di classi. Una soluzione funge da contenitore per uno o più progetti. Verranno aggiunti altri progetti correlati alla stessa soluzione.

1. Avviare Visual Studio Code.

1. Selezionare **file**  >  **Apri cartella** (**Apri...** in MacOS) dal menu principale

1. Nella finestra di dialogo **Apri cartella** creare una cartella *ClassLibraryProjects* e fare clic su **Seleziona cartella** (**Apri** in MacOS).

1. Aprire il **terminale** in Visual Studio Code selezionando **Visualizza**  >  **terminale** dal menu principale.

   Il **terminale** verrà aperto con il prompt dei comandi nella cartella *ClassLibraryProjects* .

1. Nel **terminale**immettere il comando seguente:

   ```dotnetcli
   dotnet new sln
   ```

   L'output del terminale è simile all'esempio seguente:

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a>Creare un progetto di libreria di classi

Aggiungere un nuovo progetto di libreria di classi .NET Standard denominato "StringLibrary" alla soluzione.

1. Nel terminale eseguire il comando seguente per creare il progetto di libreria:

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   L'output del terminale è simile all'esempio seguente:

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. Eseguire il comando seguente per aggiungere il progetto di libreria alla soluzione:

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   L'output del terminale è simile all'esempio seguente:

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. Verificare che la libreria sia destinata alla versione corretta di .NET Standard. In **Esplora risorse**aprire *StringLibrary/StringLibrary. csproj*.

   L' `TargetFramework` elemento indica che il progetto ha come destinazione .NET Standard 2,0.

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. Aprire *Class1.cs* e sostituire il codice con il codice seguente.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   La libreria di classi, `UtilityLibraries.StringLibrary` , contiene un metodo denominato `StartsWithUpper` . Questo metodo restituisce un <xref:System.Boolean> valore che indica se l'istanza di stringa corrente inizia con un carattere maiuscolo. Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli. Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.

1. Salvare il file.

1. Eseguire il comando seguente per compilare la soluzione e verificare che il progetto venga compilato senza errori.

   ```dotnetcli
   dotnet build
   ```

   L'output del terminale è simile all'esempio seguente:

   ```
   Microsoft (R) Build Engine version 16.6.0 for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     You are using a preview version of .NET Core. See: https://aka.ms/dotnet-core-preview
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a>Aggiungere un'app console alla soluzione

Aggiungere un'applicazione console che usa la libreria di classi. L'app chiede all'utente di immettere una stringa e segnala se la stringa inizia con un carattere maiuscolo.

1. Nel terminale eseguire il comando seguente per creare il progetto di app console:

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   L'output del terminale è simile all'esempio seguente:

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. Eseguire il comando seguente per aggiungere il progetto di app console alla soluzione:

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   L'output del terminale è simile all'esempio seguente:

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. Aprire *Showcase/Program. cs* e sostituire tutto il codice con il codice seguente.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console. Ogni volta che è maggiore o uguale a 25, il codice Cancella la finestra della console e visualizza un messaggio all'utente.

   Il programma richiede all'utente di immettere una stringa. Indica se la stringa inizia con un carattere maiuscolo. Se l'utente preme il tasto <kbd>invio</kbd> senza immettere una stringa, l'applicazione termina e la finestra della console si chiude.

1. Salvare le modifiche.

## <a name="add-a-project-reference"></a>Aggiungere un riferimento al progetto

Inizialmente, il nuovo progetto di app console non ha accesso alla libreria di classi. Per consentire la chiamata di metodi nella libreria di classi, creare un riferimento di progetto al progetto libreria di classi.

1. Eseguire il comando seguente:

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   L'output del terminale è simile all'esempio seguente:

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a>Eseguire l'app

1. Eseguire il comando seguente nel terminale:

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. Per provare il programma, immettere le stringhe e premere <kbd>invio</kbd>, quindi premere <kbd>invio</kbd> per uscire.

   L'output del terminale è simile all'esempio seguente:

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a>Risorse aggiuntive

* [Sviluppare librerie con la interfaccia della riga di comando di .NET Core](libraries.md)
* [.NET standard le versioni e le piattaforme supportate](../../standard/net-standard.md).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata creata una soluzione, è stato aggiunto un progetto di libreria e è stato aggiunto un progetto di app console che usa la libreria. Nell'esercitazione successiva si aggiunge un progetto di unit test alla soluzione.

> [!div class="nextstepaction"]
> [Testare una libreria di .NET Standard con .NET Core usando Visual Studio Code](testing-library-with-visual-studio-code.md)

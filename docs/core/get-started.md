---
title: Introduzione a .NET Core
description: Risorse per imparare a creare applicazioni .NET Core in Windows, Linux e macOS.
author: thraka
ms.author: adegeo
ms.date: 09/19/2019
ms.openlocfilehash: 89db6d79336c01315983133d9041904d88cba301
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884254"
---
# <a name="get-started-with-net-core"></a>Introduzione a .NET Core

Questo articolo fornisce informazioni sui concetti introduttivi di .NET Core. .NET core può essere installato in Windows, Linux e macOS. È possibile scrivere il codice nell'editor di testo preferito e produrre applicazioni e librerie multipiattaforma. 

Se non si conosce .NET Core o la sua relazione con altre tecnologie .NET, iniziare con la panoramica [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) (Descrizione di .NET). In poche parole, .NET Core è un'implementazione open source multipiattaforma di .NET.

## <a name="create-an-application"></a>Creare un'applicazione

Per prima cosa scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download) sul computer.

Aprire quindi un terminale, ad esempio **PowerShell**, **prompt dei comandi**, o **bash**. Digitare i seguenti comandi di `dotnet` per creare ed eseguire C# un'applicazione:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

È necessario visualizzare il seguente output:

```console
Hello World!
```

La procedura è stata completata. È stata creata una semplice applicazione .NET Core. Per creare un'applicazione .NET Core, è anche possibile usare [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (solo Windows) oppure [Visual Studio per Mac](tutorials/using-on-mac-vs.md) (solo macOS).

## <a name="tutorials"></a>Esercitazioni

È possibile iniziare lo sviluppo di applicazioni .NET Core seguendo queste esercitazioni dettagliate.

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

- [Compilare un'applicazione Hello World usando C# con .NET Core in Visual Studio 2017.](./tutorials/with-visual-studio.md)
- [Creazione di una libreria di classi con C# con .NET Core in Visual Studio 2017](./tutorials/library-with-visual-studio.md)
- [Creazione di un'applicazione Hello World in Visual Basic con .NET Core in Visual Studio 2017](./tutorials/vb-with-visual-studio.md)
- [Creazione di una libreria di classi con Visual Basic e .NET Core in Visual Studio 2017](./tutorials/vb-library-with-visual-studio.md)  
- Guardare un video su [come installare e usare Visual Studio Code e .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).
- Guardare un video su [come installare e usare Visual Studio 2017 e .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).
- [Introduzione all'uso di .NET Core usando la riga di comando](tutorials/cli-create-console-app.md)

Per un elenco delle versioni supportate di Windows, vedere l'articolo relativo alle [dipendenze e ai requisiti di .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-windows) .

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

È possibile iniziare a sviluppare un'applicazione .NET Core seguendo queste esercitazioni dettagliate:

- [Introduzione all'uso di .NET Core usando la riga di comando](tutorials/cli-create-console-app.md)
- Guardare un video sull'[Introduzione a Visual Studio Code con C# e .NET Core in Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).

Per un elenco delle distribuzioni e delle versioni di Linux supportate, vedere l'articolo relativo alle [dipendenze e ai requisiti di .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-linux) .

# <a name="macostabmacos"></a>[macOS](#tab/macos)

È possibile iniziare a sviluppare un'applicazione .NET Core seguendo queste esercitazioni dettagliate:

- Guardare un video sull'[Introduzione a Visual Studio Code con C# e .NET Core in macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).
- [Introduzione all'uso di .NET Core su macOS con Visual Studio Code.](tutorials/using-on-macos.md)
- [Introduzione all'uso di .NET Core usando la riga di comando](tutorials/cli-create-console-app.md)
- [Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac](tutorials/using-on-mac-vs.md)
- [Creazione di una soluzione .NET Core completa in macOS con Visual Studio per Mac](tutorials/using-on-mac-vs-full-solution.md)

Per un elenco delle versioni supportate di OS X/macOS, vedere l'articolo relativo alle [dipendenze e ai requisiti di .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-macos) .

---

---
title: Introduzione a .NET Core
description: Trova risorse per imparare a creare applicazioni .NET Core su Windows, Linux e macOS.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 0968d9db1dbfbdc8c586328ee8e02315f17950b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714387"
---
# <a name="get-started-with-net-core"></a>Introduzione a .NET Core

Questo articolo fornisce informazioni sui concetti introduttivi di .NET Core. .NET core può essere installato in Windows, Linux e macOS. È possibile scrivere il codice nell'editor di testo preferito e produrre applicazioni e librerie multipiattaforma.

Se non si conosce .NET Core o la sua relazione con altre tecnologie .NET, iniziare con la panoramica [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) (Descrizione di .NET). In poche parole, .NET Core è un'implementazione open source multipiattaforma di .NET.

## <a name="create-an-application"></a>Creare un'applicazione

Per prima cosa scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download) sul computer.

Aprire quindi un terminale, ad esempio **PowerShell**, **prompt dei comandi**, o **bash**. Digitare `dotnet` i comandi seguenti per creare ed eseguire un'applicazione in C:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Dovrebbe venire visualizzato l'output seguente.

```console
Hello World!
```

Congratulazioni! È stata creata una semplice applicazione .NET Core. Per creare un'applicazione .NET Core, è anche possibile usare [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (solo Windows) oppure [Visual Studio per Mac](./tutorials/using-on-mac-vs.md) (solo macOS).

## <a name="tutorials"></a>Esercitazioni

Iniziare a sviluppare applicazioni .NET Core seguendo queste esercitazioni dettagliate:Get started developing .NET Core applications by following these step-by-step tutorials:

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

- [Creare la prima applicazione console .NET Core in Visual Studio 2019](./tutorials/with-visual-studio.md)
- [Creare una libreria di classi con .NET Standard in Visual StudioBuild a class library with .NET Standard in Visual Studio](./tutorials/library-with-visual-studio.md)
- [Introduzione a .NET Core con l'interfaccia della riga di comando di .NET Core](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| ![icona della telecamera per un video](./media/video-icon.png "Guardare un video") | Guarda il video [su come installare e usare Visual Studio Code e .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) su Channel 9. |
| ![icona della telecamera per un video](./media/video-icon.png "Guardare un video") | Guarda i video di [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) su YouTube. |

Vedere l'articolo [Dependencies and requirements](install/dependencies.md?pivots=os-windows) di .NET Core per un elenco delle versioni di Windows supportate.

# <a name="linux"></a>[Linux](#tab/linux)

Iniziare a sviluppare applicazioni .NET Core seguendo queste esercitazioni dettagliate:Get started developing .NET Core applications by following these step-by-step tutorials:

- [Introduzione a .NET Core tramite la riga di comando](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| ![icona della telecamera per un video](./media/video-icon.png "Guardare un video") | Guardare un video sull'[Introduzione a Visual Studio Code con C# e .NET Core in Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu). |

Vedere l'articolo [Dipendenze e requisiti](install/dependencies.md?pivots=os-linux) di .NET Core per un elenco delle distribuzioni e delle versioni di Linux supportate.

# <a name="macos"></a>[Macos](#tab/macos)

Iniziare a sviluppare applicazioni .NET Core seguendo queste esercitazioni dettagliate:Get started developing .NET Core applications by following these step-by-step tutorials:

- [Introduzione all'uso di .NET Core su macOS con Visual Studio Code](./tutorials/using-on-macos.md)
- [Introduzione a .NET Core tramite la riga di comando](./tutorials/cli-create-console-app.md)
- [Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac](./tutorials/using-on-mac-vs.md)
- [Creare una soluzione .NET Core completa in macOS usando Visual Studio per Mac](./tutorials/using-on-mac-vs-full-solution.md)

|   |   |
|---|---|
| ![icona della telecamera per un video](media/video-icon.png "Guardare un video") | Guardare un video su come iniziare a usare il codice di [Visual Studio usando C .NET Core in macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac). |

Vedere l'articolo [Dipendenze e requisiti](install/dependencies.md?pivots=os-macos) di .NET Core per un elenco delle versioni di OS X / macOS supportate.

---

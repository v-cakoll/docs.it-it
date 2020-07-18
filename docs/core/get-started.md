---
title: Introduzione a .NET Core
description: Risorse per imparare a creare applicazioni .NET Core in Windows, Linux e macOS.
author: adegeo
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ddbee0764897b511cac0c4142354ba995d94a2b6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416058"
---
# <a name="get-started-with-net-core"></a>Introduzione a .NET Core

Questo articolo fornisce informazioni sui concetti introduttivi di .NET Core. .NET core può essere installato in Windows, Linux e macOS. È possibile scrivere il codice nell'editor di testo preferito e produrre applicazioni e librerie multipiattaforma.

Se non si conosce .NET Core o la sua relazione con altre tecnologie .NET, iniziare con la panoramica [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) (Descrizione di .NET). In poche parole, .NET Core è un'implementazione open source multipiattaforma di .NET.

## <a name="create-an-application"></a>Creare un'applicazione

Per prima cosa scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download) sul computer.

Aprire quindi un terminale, ad esempio **PowerShell**, **prompt dei comandi**, o **bash**. Digitare i `dotnet` comandi seguenti per creare ed eseguire un'applicazione C#:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Dovrebbe venire visualizzato l'output seguente:

```console
Hello World!
```

Congratulazioni. È stata creata una semplice applicazione .NET Core. Per creare un'applicazione .NET Core, è anche possibile usare [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (solo Windows) oppure [Visual Studio per Mac](./tutorials/using-on-mac-vs.md) (solo macOS).

## <a name="tutorials"></a>Esercitazioni

Per iniziare a sviluppare applicazioni .NET Core, seguire queste esercitazioni dettagliate:

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

- [Creare la prima applicazione console .NET Core in Visual Studio 2019](./tutorials/with-visual-studio.md)
- [Creare una libreria di classi con .NET Standard in Visual Studio](./tutorials/library-with-visual-studio.md)
- [Introduzione a .NET Core con la interfaccia della riga di comando di .NET Core](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| ![icona della telecamera per un video](./media/video-icon.png "Guardare un video") | Vedere le [procedure per installare e usare Visual Studio Code e](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) il video di .NET Core su Channel 9. |
| ![icona della telecamera per un video](./media/video-icon.png "Guardare un video") | Guarda i video su [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) su YouTube. |

Per un elenco delle versioni supportate di Windows, vedere l'articolo relativo alle [dipendenze e ai requisiti di .NET Core](install/dependencies.md?pivots=os-windows) .

# <a name="linux"></a>[Linux](#tab/linux)

Per iniziare a sviluppare applicazioni .NET Core, seguire queste esercitazioni dettagliate:

- [Introduzione a .NET Core tramite la riga di comando](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| ![icona della telecamera per un video](./media/video-icon.png "Guardare un video") | Guardare un video sull'[Introduzione a Visual Studio Code con C# e .NET Core in Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu). |

Per un elenco delle distribuzioni e delle versioni di Linux supportate, vedere l'articolo relativo alle [dipendenze e ai requisiti di .NET Core](install/dependencies.md?pivots=os-linux) .

# <a name="macos"></a>[macOS](#tab/macos)

Per iniziare a sviluppare applicazioni .NET Core, seguire queste esercitazioni dettagliate:

- [Introduzione all'uso di .NET Core su macOS con Visual Studio Code](./tutorials/using-on-macos.md)
- [Introduzione a .NET Core tramite la riga di comando](./tutorials/cli-create-console-app.md)
- [Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac](./tutorials/using-on-mac-vs.md)
- [Creare una libreria di .NET Standard in macOS con Visual Studio per Mac](tutorials/library-with-visual-studio-mac.md)

|   |   |
|---|---|
| ![icona della telecamera per un video](media/video-icon.png "Guardare un video") | Guarda un video su [come iniziare a usare Visual Studio Code con C# e .NET Core in MacOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac). |

Per un elenco delle versioni supportate di OS X/macOS, vedere l'articolo relativo alle [dipendenze e ai requisiti di .NET Core](install/dependencies.md?pivots=os-macos) .

---

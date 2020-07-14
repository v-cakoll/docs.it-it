---
title: Introduzione e Panoramica di .NET Core
description: .NET Core è un'implementazione modulare e a elevate prestazioni di .NET per la creazione di app Windows, Linux e macOS. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: b28ad965e54680e2e1134c389266741ade28084f
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226582"
---
# <a name="introduction-to-net-core"></a>Introduzione a .NET Core

[.NET Core](about.md) è una piattaforma di sviluppo [Open Source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)per utilizzo generico. È possibile creare app .NET Core per Windows, macOS e Linux per processori x64, x86, ARM32 e ARM64 usando più linguaggi di programmazione. I Framework e le API sono forniti [cloud](/aspnet/core/)per cloud [, Internet delle cose,](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0) [interfaccia utente client](../desktop-wpf/overview/index.md)e [Machine Learning](/dotnet/machine-learning/).

[Scaricare il .NET Core SDK](https://dotnet.microsoft.com/download) per provare .NET Core nel computer. La versione più recente è [.NET Core 3,1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).

## <a name="download-net-core"></a>Download di .NET Core

È possibile ottenere .NET Core nei modi seguenti:

* [Programmi di installazione per Windows e macOS](https://dotnet.microsoft.com/download)
* [Pacchetti Linux](https://docs.microsoft.com/dotnet/core/install/linux-package-managers)
* [Contenitori Docker](https://hub.docker.com/_/microsoft-dotnet-core/)
* [Zip e tarball](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [Script di installazione](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [Note sulla versione](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a>Creare la prima applicazione

Dopo aver installato .NET Core SDK, aprire un prompt dei comandi. Usare i comandi seguenti per creare ed eseguire un'applicazione:

```dotnetcli
dotnet new console
dotnet run
```

Dovrebbe venire visualizzato l'output seguente:

```output
Hello World!
```

## <a name="contribute"></a>Collabora

.NET Core è una piattaforma aperta. Tutti gli utenti sono invitati a partecipare.

* Problemi relativi ai prodotti e alle domande [della community degli sviluppatori](https://developercommunity.visualstudio.com/spaces/61/index.html).
* I contributi ai prodotti devono essere effettuati in uno dei repository del progetto, ad esempio [DotNet/Runtime](https://github.com/dotnet/runtime), [DotNet/SDK](https://github.com/dotnet/sdk), [DotNet/Rosyln](https://github.com/dotnet/roslyn)o [aspnetcore](https://github.com/dotnet/aspnetcore). Per altre informazioni, vedere [repository di .NET Core](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).

## <a name="support"></a>Supporto tecnico

.NET Core è supportato da Microsoft in Windows, macOS e Linux e da Red Hat su Red Hat Enterprise Linux.

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Esercitazioni su .NET Core](tutorials/index.md)

> [!div class="nextstepaction"]
> [Prova .NET Core nel browser](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)

---
title: Introduzione e panoramica di .NET Core
description: .NET Core è un'implementazione modulare e ad alte prestazioni di .NET per la creazione di app Windows, Linux e macOS. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.date: 03/25/2020
ms.custom: updateeachrelease
ms.openlocfilehash: edd3864d3c3c5c0e9fd8c26ee806ffc9e100423d
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80351701"
---
# <a name="introduction-to-net-core"></a>Introduzione a .NET CoreIntroduction to .NET Core

[.NET Core](about.md) è una piattaforma di sviluppo [open source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) per utilizzo generico gestita da Microsoft e dalla community .NET su [GitHub](https://github.com/dotnet/core). È multipiattaforma, supporta Windows, macOS e Linux e può essere usata per creare applicazioni per dispositivi, cloud e IoT.

## <a name="download-net-core"></a>Download di .NET Core

Scarica [.NET Core SDK](https://dotnet.microsoft.com/download) per provare .NET Core nel computer Windows, macOS o Linux. Se si preferisce utilizzare i contenitori Docker, visitare [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).

## <a name="net-core-31"></a>.NET Core 3.1

La versione più recente è .NET Core 3.1. 3.1 include miglioramenti minori rispetto a .NET Core 3.0, tuttavia, .NET Core 3.1 è una [versione supportata a lungo termine.](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) Per ulteriori informazioni sulla versione .NET Core 3.1, vedere [Novità di .NET Core 3.1.](./whats-new/dotnet-core-3-1.md)

Se stai cercando un'altra versione di .NET Core, tutte le versioni sono disponibili in [download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="create-your-first-application"></a>Creare la prima applicazione

Dopo aver installato .NET Core SDK, aprire un prompt dei comandi. Immettere `dotnet` i comandi seguenti per creare ed eseguire un'applicazione in C:

```dotnetcli
dotnet new console
dotnet run
```

Dovrebbe venire visualizzato l'output seguente.

```output
Hello World!
```

## <a name="support"></a>Supporto

.NET Core è [supportato da Microsoft](https://dotnet.microsoft.com/platform/support/policy) su Windows, macOS e Linux. Viene aggiornato per sicurezza e qualità diverse volte l'anno, in genere ogni mese.

Le distribuzioni binarie di .NET Core sono compilate e testate in server gestiti da Microsoft in Azure e sono supportate come qualsiasi prodotto Microsoft.

[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL). Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Esercitazioni di .NET Core](tutorials/index.md)

> [!div class="nextstepaction"]
> [Prova .NET Core nel tuo browser](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)

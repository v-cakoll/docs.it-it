---
title: Guida a .NET Core
description: .NET core è un'implementazione modulare ad alte prestazioni di .NET per la creazione di app di Windows, Mac e Linux. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 0007c1c6a9939c46f123535f9053ac1d4ced7266
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848936"
---
# <a name="net-core-guide"></a>Guida a .NET Core

[.NET Core](about.md) è una piattaforma di sviluppo [open source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) per utilizzo generico gestita da Microsoft e dalla community .NET su [GitHub](https://github.com/dotnet/core). È multipiattaforma, supporta Windows, macOS e Linux e può essere usata per creare applicazioni per dispositivi, cloud e IoT.

Vedere [Informazioni su .NET Core](about.md) per altre informazioni su .NET Core, inclusi le caratteristiche, i linguaggi e i framework supportati e le principali API.

Per imparare a creare una semplice applicazione .NET Core, vedere le [Esercitazioni di .NET Core](tutorials/index.md). Sono necessari pochi minuti per realizzare ed eseguire la prima app. Se si vuole provare .NET Core nel browser, vedere l'esercitazione online [Numeri in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).

## <a name="download-net-core-22"></a>Scaricare .NET Core 2.2

Scaricare [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) per provare .NET Core nel computer Windows, macOS o Linux. Visitare [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) se si preferisce usare i contenitori Docker.

Tutte le versioni di .NET Core sono disponibili nella pagina [Download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core) se si sta cercando un'altra versione di .NET Core.

## <a name="net-core-22"></a>.NET Core 2.2

La versione più recente è [.NET Core 2.2](whats-new/dotnet-core-2-2.md). Le nuove funzionalità includono: distribuzioni dipendenti dal framework, hook di avvio, autenticazione AAD con SQL di Azure e il supporto per Windows ARM32.

## <a name="create-your-first-application"></a>Creare la prima applicazione

Dopo aver installato .NET Core SDK, aprire un prompt dei comandi. Digitare i seguenti comandi `dotnet` per creare ed eseguire un'applicazione C#.

```console
dotnet new console
dotnet run
```

È necessario visualizzare il seguente output:

```output
Hello World!
```

## <a name="support"></a>Supporto

.NET Core è [supportato da Microsoft](https://dotnet.microsoft.com/platform/support/policy) in Windows, macOS e Linux. Viene aggiornato per sicurezza e qualità diverse volte l'anno, in genere ogni mese.

Le distribuzioni binarie di .NET Core sono compilate e testate in server gestiti da Microsoft in Azure e sono supportate come qualsiasi prodotto Microsoft.

[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL). Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.

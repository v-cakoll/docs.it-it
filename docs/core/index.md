---
title: Guida a .NET Core
description: .NET Core è un'implementazione modulare e ad alte prestazioni di .NET per la creazione di app Windows, Linux e macOS. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: 3db98d21a7cdc80d8a98b23782a81ffa37520937
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75740753"
---
# <a name="net-core-guide"></a>Guida a .NET Core

[.NET Core](about.md) è una piattaforma di sviluppo [open source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) per utilizzo generico gestita da Microsoft e dalla community .NET su [GitHub](https://github.com/dotnet/core). È multipiattaforma, supporta Windows, macOS e Linux e può essere usata per creare applicazioni per dispositivi, cloud e IoT.

Vedere [Informazioni su .NET Core](about.md) per altre informazioni su .NET Core, inclusi le caratteristiche, i linguaggi e i framework supportati e le principali API.

Per imparare a creare una semplice applicazione .NET Core, vedere le [Esercitazioni di .NET Core](tutorials/index.md). Sono necessari pochi minuti per realizzare ed eseguire la prima app. Se si vuole provare .NET Core nel browser, vedere l'esercitazione online [Numeri in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).

## <a name="download-net-core"></a>Download di .NET Core

Scarica [.NET Core SDK](https://www.microsoft.com/net/download) per provare .NET Core nel computer Windows, macOS o Linux. E se si preferisce utilizzare i contenitori Docker, visitare [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).

Tutte le versioni di .NET Core sono disponibili nella pagina [Download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core) se si sta cercando un'altra versione di .NET Core.

## <a name="net-core-31"></a>.NET Core 3.1

La versione più recente è .NET Core 3.1. 3.1 include miglioramenti minori rispetto a .NET Core 3.0, tuttavia, .NET Core 3.1 è una [versione supportata a lungo termine.](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) Per ulteriori informazioni sulla versione .NET Core 3.1, vedere [Novità di .NET Core 3.1.](./whats-new/dotnet-core-3-1.md)

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

.NET Core è [supportato da Microsoft](https://dotnet.microsoft.com/platform/support/policy), in Windows, macOS e Linux. Viene aggiornato per sicurezza e qualità diverse volte l'anno, in genere ogni mese.

Le distribuzioni binarie di .NET Core sono compilate e testate in server gestiti da Microsoft in Azure e sono supportate come qualsiasi prodotto Microsoft.

[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL). Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.

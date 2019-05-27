---
title: Panoramica di .NET Core SDK
description: Informazioni su .NET Core SDK, ovvero un set di librerie e strumenti usati per creare progetti .NET Core.
ms.date: 05/13/2019
ms.technology: dotnet-cli
ms.openlocfilehash: ed9d51b337af8edc251a4f3b02c31b72b76ba33d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877981"
---
# <a name="net-core-sdk-overview"></a>Panoramica di .NET Core SDK

.NET Core SDK è un set di librerie e strumenti che consente agli sviluppatori di creare applicazioni e librerie .NET Core. Contiene i componenti seguenti che consentono di compilare ed eseguire applicazioni:

- Strumenti dell'interfaccia della riga di comando di .NET Core.
- Librerie e runtime di .NET Core.
- [Driver](/tools/index.md#driver) `dotnet`.

## <a name="acquiring-the-net-core-sdk"></a>Acquisizione di .NET Core SDK

Come per qualsiasi strumento, è innanzitutto necessario eseguire l'installazione nel computer. A seconda dello scenario, è possibile installare il SDK usando uno dei metodi seguenti:

- Usare i programmi nativi.
- Usare lo script della shell di installazione.

I programmi di installazione nativi sono principalmente destinati ai computer degli sviluppatori. Il SDK viene distribuito tramite il meccanismo di installazione nativo di ogni piattaforma supportata, ad esempio i pacchetti DEB in Ubuntu o i bundle MSI in Windows. Questi programmi di installazione installano e configurano l'ambiente in modo da consentire all'utente di usare il SDK immediatamente dopo l'installazione. Tuttavia, richiedono anche privilegi amministrativi sul computer. È possibile trovare il SDK da installare nella pagina [.NET downloads](https://dotnet.microsoft.com/download).

Gli script di installazione invece non richiedono privilegi di amministratore. Tuttavia gli script non installano i prerequisiti nel computer: è necessario installare tutti i prerequisiti manualmente. Gli script sono progettati principalmente per configurare i server di compilazione o possono essere usati quando si vuole installare gli strumenti senza privilegi amministrativi (tenendo conto della precedente precisazione relativa ai prerequisiti). Per altre informazioni, vedere l'articolo [Riferimento agli script dotnet-install](tools/dotnet-install-script.md). Per informazioni sulla procedura di configurazione del SDK nel server di compilazione CI, vedere [Uso di .NET Core SDK e dei relativi strumenti in integrazione continua](tools/using-ci-with-cli.md).

Per impostazione predefinita il SDK viene installato in modalità "side-by-side" (SxS). Ciò significa che possono coesistere più versioni degli strumenti CLI in un singolo computer. La modalità di selezione della versione quando si eseguono comandi CLI è illustrata in dettaglio nell'articolo [Selezionare la versione di .NET Core da usare](/versions/selection.md).

## <a name="see-also"></a>Vedere anche

- [Interfaccia della riga di comando di .NET Core](tools/index.md)
- [Panoramica delle versioni di .NET Core](/versions/index.md)
- [Come rimuovere il runtime e il SDK di .NET Core](versions/remove-runtime-sdk-versions.md)
- [Selezionare la versione di .NET Core da usare](/versions/selection.md)
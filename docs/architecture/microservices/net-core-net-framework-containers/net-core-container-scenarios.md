---
title: Quando scegliere .NET Core per i contenitori Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Quando scegliere .NET Core per i contenitori Docker
ms.date: 01/30/2020
ms.openlocfilehash: 8d25cf58c48aac137ba91300515bdb72a7eb648d
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507273"
---
# <a name="when-to-choose-net-core-for-docker-containers"></a>Quando scegliere .NET Core per i contenitori Docker

La modularità e la natura leggera di .NET Core lo rende la scelta ideale per i contenitori. Quando si distribuisce e si avvia un contenitore, la sua immagine risulta notevolmente più piccola con .NET Core rispetto a .NET Framework. Al contrario, per usare .NET Framework per un contenitore, è necessario basare l'immagine su un'immagine di Windows Server Core che risulta molto più pesante rispetto alle immagini di Windows Nano Server o Linux usate per .NET Core.

Inoltre, .NET Core è multipiattaforma e consente quindi di distribuire app server con immagini del contenitore Linux o Windows. Tuttavia, se si usa .NET Framework tradizionale, è solo possibile distribuire immagini basate su Windows Server Core.

Di seguito è fornita una spiegazione dettagliata sui motivi per cui è opportuno scegliere .NET Core.

## <a name="developing-and-deploying-cross-platform"></a>Sviluppo e distribuzione per più piattaforme

Chiaramente, se l'obiettivo è creare un'applicazione (app Web o servizio) che può essere eseguita su più piattaforme supportate da Docker (Linux e Windows), la scelta corretta è .NET Core, in quanto .NET Framework supporta solo Windows.

.NET Core supporta anche macOS come piattaforma di sviluppo. Tuttavia, quando i contenitori vengono distribuiti in un host Docker, l'host deve (attualmente) essere basato su Linux o Windows. In un ambiente di sviluppo, ad esempio, si potrebbe usare una macchina virtuale Linux in esecuzione in un Mac.

[Visual Studio](https://www.visualstudio.com/vs/) fornisce un ambiente di sviluppo integrato (IDE) per Windows e supporta lo sviluppo per Docker.

[Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/) è un ambiente IDE, evoluzione di Xamarin Studio, che viene eseguito su macOS e supporta lo sviluppo di applicazioni basate su Docker. È la scelta più indicata per gli sviluppatori che lavorano in computer Mac che vogliono anche usare un potente IDE.

È anche possibile usare [Visual Studio Code](https://code.visualstudio.com/) in MacOS, Linux e Windows. Visual Studio Code supporta completamente .NET Core, inclusi IntelliSense e debug. Poiché VS Code è un editor leggero, è possibile usarlo per sviluppare app in contenitori nel computer insieme all'interfaccia della riga di comando di Docker e al [interfaccia della riga di comando di .NET Core](../../../core/tools/index.md). È anche possibile usare .NET Core con la maggior parte degli editor di terze parti, come Sublime, Emacs, vi e il progetto OmniSharp open source che fornisce anche il supporto di IntelliSense.

Oltre agli IDE ed editor, è possibile usare la [interfaccia della riga di comando di .NET Core](../../../core/tools/index.md) per tutte le piattaforme supportate.

## <a name="using-containers-for-new-green-field-projects"></a>Uso dei contenitori per i nuovi progetti (green field)

I contenitori vengono comunemente usati in combinazione con un'architettura di microservizi, sebbene possano essere impiegati anche per creare contenitori di servizi o app Web basati su qualsiasi schema architetturale. È possibile usare .NET Framework in Contenitori Windows, ma le caratteristiche di modularità e leggerezza rendono .NET Core la scelta ideale per i contenitori e le architetture di microservizi. Quando si crea e si distribuisce un contenitore, la sua immagine risulta notevolmente più piccola con .NET Core rispetto a .NET Framework.

## <a name="create-and-deploy-microservices-on-containers"></a>Creare e distribuire microservizi nei contenitori

Per creare applicazioni basate su microservizi (senza contenitori) è possibile usare .NET Framework tradizionale e processi normali. In questo modo, poiché .NET Framework è già installato e condiviso tra i processi, i processi sono leggeri e si avviano velocemente. Tuttavia, se si usano i contenitori, l'immagine per .NET Framework tradizionale è basata su Windows Server Core e diventa troppo pesante per un approccio per microservizi basati su contenitori. Tuttavia, i team hanno cercato opportunità per migliorare l'esperienza anche per gli utenti .NET Framework. Di recente, le dimensioni delle [Immagini del contenitore di Windows Server Core sono state ridotte a >40% più piccole](https://devblogs.microsoft.com/dotnet/we-made-windows-server-core-container-images-40-smaller).

D'altra parte, .NET Core è il candidato migliore se si sta adottando un sistema orientato ai microservizi basato sui contenitori, perché .NET Core è leggero. Inoltre, le immagini del contenitore correlate, per Linux o Windows nano server, sono magre e piccole, rendendo i contenitori chiaro e rapido per l'avvio.

Un microservizio deve essere più piccolo possibile: deve essere leggero quando accelera, avere un footprint ridotto e un contesto delimitato di piccole dimensioni (vedere DDD, [Domain-driven design](https://en.wikipedia.org/wiki/Domain-driven_design)), non deve generare un eccesso di preoccupazioni e deve poter essere avviato e arrestato velocemente. Con questi requisiti, sarà opportuno usare immagini del contenitore di piccole dimensioni e che garantiscono la creazione di istanze veloce, come l'immagine del contenitore .NET Core.

Un'architettura di microservizi consente di usare una combinazione di tecnologie in un'area di servizi confinata. Questo permette una migrazione graduale a .NET Core per i nuovi microservizi che funzionano in combinazione con altri microservizi o con servizi sviluppati con Node.js, Python, Java, GoLang o altre tecnologie.

## <a name="deploying-high-density-in-scalable-systems"></a>Distribuzione dell'alta densità nei sistemi scalabili

Se il sistema basato su contenitori richiede i massimi livelli di densità, granularità e prestazioni, le opzioni ottimali sono rappresentate da .NET Core e ASP.NET Core. ASP.NET Core è 10 volte più veloce rispetto ad ASP.NET in .NET Framework tradizionale Core è in testa alla classifica delle più diffuse tecnologie di settore per microservizi, come servlet Java, Go e Node.js.

Questo aspetto riguarda in particolare le architetture con centinaia di microservizi (contenitori) in esecuzione. Con le immagini di ASP.NET Core, basate sul runtime di .NET Core, in Linux o Windows Nano, è possibile eseguire il sistema con un minor numero di server o macchine virtuali, risparmiando così sui costi di infrastruttura e di hosting.

>[!div class="step-by-step"]
>[Precedente](general-guidance.md)
>[successivo](net-framework-container-scenarios.md)

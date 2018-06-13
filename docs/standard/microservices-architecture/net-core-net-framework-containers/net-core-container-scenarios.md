---
title: Quando scegliere .NET Core per i contenitori Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Quando scegliere .NET Core per i contenitori Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 4e2585d7fdeb89e7267f2615113f819d71236dc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580172"
---
# <a name="when-to-choose-net-core-for-docker-containers"></a>Quando scegliere .NET Core per i contenitori Docker

La modularità e la natura leggera di .NET Core lo rende la scelta ideale per i contenitori. Quando si distribuisce e si avvia un contenitore, la sua immagine risulta notevolmente più piccola con .NET Core rispetto a .NET Framework. Al contrario, per usare .NET Framework per un contenitore, è necessario basare l'immagine su un'immagine di Windows Server Core che risulta molto più pesante rispetto alle immagini di Windows Nano Server o Linux usate per .NET Core.

Inoltre, .NET Core è multipiattaforma e consente quindi di distribuire app server con immagini del contenitore Linux o Windows. Tuttavia, se si usa .NET Framework tradizionale, è solo possibile distribuire immagini basate su Windows Server Core.

Di seguito è fornita una spiegazione dettagliata sui motivi per cui è opportuno scegliere .NET Core.

## <a name="developing-and-deploying-cross-platform"></a>Sviluppo e distribuzione per più piattaforme

Chiaramente, se l'obiettivo è creare un'applicazione (applicazione Web o servizio) che può essere eseguita su più piattaforme supportate da Docker (Linux e Windows), la scelta corretta è .NET Core, in quanto .NET Framework supporta solo Windows.

.NET Core supporta anche macOS come piattaforma di sviluppo. Tuttavia, quando i contenitori vengono distribuiti in un host Docker, l'host deve (attualmente) essere basato su Linux o Windows. In un ambiente di sviluppo, ad esempio, si potrebbe usare una macchina virtuale Linux in esecuzione in un Mac.

[Visual Studio](https://www.visualstudio.com/) fornisce un ambiente di sviluppo integrato (IDE) per Windows e supporta lo sviluppo per Docker. 

[Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/) è un ambiente di sviluppo integrato, un'evoluzione di Xamarin Studio, in esecuzione in macOS e in grado di supportare Docker dalla metà del 2017.

È anche possibile usare [Visual Studio Code](https://code.visualstudio.com/) in macOS, Linux e Windows. Visual Studio Code supporta infatti .NET Core, incluse le funzionalità IntelliSense e di debug. Poiché Visual Studio Code è un editor leggero, è possibile usarlo per sviluppare app in contenitori in Mac in combinazione con l'interfaccia della riga di comando di Docker e gli strumenti dell'interfaccia della riga di comando di [.NET Core](../../../core/tools/index.md). È anche possibile usare .NET Core con la maggior parte degli editor di terze parti, come Sublime Text, Emacs, vi e il progetto OmniSharp open source che fornisce il supporto di IntelliSense per i linguaggi .NET. Oltre agli ambienti di sviluppo integrato e agli editor, è possibile usare l'interfaccia della riga di comando di .NET Core per tutte le piattaforme supportate.

## <a name="using-containers-for-new-green-field-projects"></a>Uso dei contenitori per i nuovi progetti (green field)

I contenitori vengono comunemente usati in combinazione con un'architettura di microservizi, sebbene possano essere impiegati anche per creare contenitori di servizi o app Web basati su qualsiasi schema architetturale. È possibile usare .NET Framework in Contenitori Windows, ma le caratteristiche di modularità e leggerezza rendono .NET Core la scelta ideale per i contenitori e le architetture di microservizi. Quando si crea e si distribuisce un contenitore, la sua immagine risulta notevolmente più piccola con .NET Core rispetto a .NET Framework.

## <a name="creating-and-deploying-microservices-on-containers"></a>Creazione e distribuzione di microservizi in contenitori

Per creare applicazioni basate su microservizi (senza contenitori) è possibile usare .NET Framework tradizionale e processi normali. In questo modo, poiché .NET Framework è già installato e condiviso tra i processi, i processi sono leggeri e si avviano velocemente. Tuttavia, se si usano i contenitori, l'immagine per .NET Framework tradizionale è basata su Windows Server Core e diventa troppo pesante per un approccio per microservizi basati su contenitori.

Al contrario, .NET Core è il miglior candidato per un sistema orientato ai microservizi basato su contenitori, perché è molto più leggero. Inoltre, le immagini dei contenitori correlate, l'immagine Linux o l'immagine Windows Nano, sono snelle e di piccole dimensioni per garantire la leggerezza dei contenitori e aumentarne la velocità di avvio.

Un microservizio deve essere più piccolo possibile: deve essere leggero quando accelera, avere un footprint ridotto e un contesto delimitato di piccole dimensioni, non deve generare un eccesso di preoccupazioni e deve poter essere avviato e arrestato velocemente. Con questi requisiti, sarà opportuno usare immagini del contenitore di piccole dimensioni e che garantiscono la creazione di istanze veloce, come l'immagine del contenitore .NET Core.

Un'architettura di microservizi consente di usare una combinazione di tecnologie in un'area di servizi confinata. Questo permette una migrazione graduale a .NET Core per i nuovi microservizi che funzionano in combinazione con altri microservizi o con servizi sviluppati con Node.js, Python, Java, GoLang o altre tecnologie.

## <a name="deploying-high-density-in-scalable-systems"></a>Distribuzione dell'alta densità nei sistemi scalabili

Se il sistema basato su contenitori richiede i massimi livelli di densità, granularità e prestazioni, le opzioni ottimali sono rappresentate da .NET Core e ASP.NET Core. ASP.NET Core è 10 volte più veloce rispetto ad ASP.NET in .NET Framework tradizionale Core è in testa alla classifica delle più diffuse tecnologie di settore per microservizi, come servlet Java, Go e Node.js.

Questo aspetto riguarda in particolare le architetture con centinaia di microservizi (contenitori) in esecuzione. Con le immagini di ASP.NET Core, basate sul runtime di .NET Core, in Linux o Windows Nano, è possibile eseguire il sistema con un minor numero di server o macchine virtuali, risparmiando così sui costi di infrastruttura e di hosting.


>[!div class="step-by-step"]
[Indietro] (general-guidance.md) [Avanti] (net-framework-container-scenarios.md)

---
title: Quando scegliere .NET Core per i contenitori di Docker
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Quando scegliere .NET Core per i contenitori di Docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7e2322bab7937c41d4659fefef11c8937d5eae7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-core-for-docker-containers"></a>Quando scegliere .NET Core per i contenitori di Docker

La natura di modularità e lightweight di .NET Core rende ideale per i contenitori. Quando si distribuisce e avvia un contenitore, l'immagine è molto più piccolo e .NET Core rispetto a .NET Framework. Al contrario, per utilizzare .NET Framework per un contenitore, è necessario basare l'immagine sull'immagine di Windows Server Core, è molto maggiore Windows Nano Server o le immagini Linux che utilizzano per .NET Core.

Inoltre, .NET Core è multipiattaforma, pertanto è possibile distribuire applicazioni server Linux o Windows immagini contenitore. Tuttavia, se si utilizza .NET Framework tradizionale, è possibile distribuire solo le immagini basate su Windows Server Core.

Di seguito viene fornita una spiegazione più dettagliata del motivo scegliere .NET Core.

## <a name="developing-and-deploying-cross-platform"></a>Sviluppo e distribuzione su più piattaforme

Se l'obiettivo consiste nell'ottenere un'applicazione (applicazione web o servizio) che è possibile eseguire su più piattaforme supportate da Docker Linux e Windows, la scelta giusta è chiaramente, .NET Core, perché .NET Framework supporta solo Windows.

.NET core supporta inoltre macOS come piattaforma di sviluppo. Tuttavia, quando si distribuiscono i contenitori in un host Docker, tale host deve essere (attualmente) basata su Linux o Windows. In un ambiente di sviluppo, ad esempio, è possibile utilizzare una VM Linux in esecuzione su Mac.

[Visual Studio](https://www.visualstudio.com/) fornisce un ambiente di sviluppo integrato (IDE) per Windows e supporta lo sviluppo di Docker. 

[Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/) è un ambiente IDE evoluzione di Xamarin Studio, in esecuzione in macOS e supporta Docker dal mid 2017.

È inoltre possibile utilizzare [codice di Visual Studio](https://code.visualstudio.com/) (codice di Visual Studio) in Windows, Linux e macOS. Codice di Visual Studio supporta .NET Core, tra cui IntelliSense e il debug. Poiché Visual Studio Code è un semplice editor, è possibile utilizzare per sviluppare applicazioni nei contenitori su Mac in combinazione con l'interfaccia CLI di Docker e [gli strumenti di interfaccia della riga di comando (CLI) di .NET Core](https://docs.microsoft.com/dotnet/core/tools/?tabs=netcore2x). È inoltre possibile scegliere .NET Core con l'editor più terze parti come testo Sublime, Emacs, vi e il progetto OmniSharp open source che fornisce il supporto IntelliSense per i linguaggi .NET. Oltre a editor e IDE, è possibile utilizzare l'interfaccia CLI di .NET Core per tutte le piattaforme supportate.

## <a name="using-containers-for-new-green-field-projects"></a>Utilizzo di contenitori per i nuovi progetti ("verde-field")

Contenitori vengono comunemente utilizzati in combinazione con un'architettura di microservizi, sebbene sia possibile utilizzarli anche per le app web o servizi che seguono un modello architettonico inserita in un contenitore. È possibile utilizzare .NET Framework per contenitori di Windows, ma la modularità e semplicità di .NET Core rende ideale per le architetture di contenitori e microservizi. Quando si creano e distribuisce un contenitore, l'immagine è molto più piccolo e .NET Core rispetto a .NET Framework.

## <a name="creating-and-deploying-microservices-on-containers"></a>Creazione e distribuzione di microservizi sui contenitori

È possibile utilizzare .NET Framework tradizionale per la compilazione di applicazioni basate su microservizi (senza contenitori) usando processi normali. In questo modo, poiché .NET Framework è già installato e condivisi tra processi, processi chiaro e veloci per l'avvio. Tuttavia, se si usano i contenitori, per .NET Framework tradizionale si basa l'immagine anche in Windows Server Core e che lo rende eccessivo per un approccio in contenitori di microservizi.

Al contrario, .NET Core è la migliore se si è adottando un sistema orientato ai microservizi basato su contenitori, in quanto .NET Core è semplice. Immagini relativi contenitori correlati, l'immagine di Linux o l'immagine Nano Windows, sono inoltre snella e piccole effettua luce contenitori e veloce per iniziare.

Deve essere ridotte al massimo un microservizio: sia chiaro quando spin-up, per avere un footprint ridotto, per ottenere un piccolo limitato il contesto, per rappresentare una piccola area delle problematiche e ed essere in grado di avviare e arrestare fast. Per tali requisiti, è consigliabile utilizzare le immagini contenitore di piccola e veloce per creare ad esempio l'immagine di contenitore di .NET Core.

Un'architettura di microservizi consente anche di combinare le tecnologie attraverso un limite di servizio. In questo modo una migrazione graduale a .NET Core per la nuova microservizi che funzionano in combinazione con altri microservizi o con i servizi sviluppati con Node.js, Python, Java, GoLang o altre tecnologie.

## <a name="deploying-high-density-in-scalable-systems"></a>Distribuzione di ad alta densità in sistemi scalabili

Quando i sistemi basati su contenitore deve migliore densità possibile, la granularità e delle prestazioni, .NET Core e ASP.NET Core sono le opzioni migliori. ASP.NET Core è dieci volte più veloce di ASP.NET in .NET Framework tradizionale e tale operazione comporta altre tecnologie di settore diffuso per microservizi, ad esempio servlet Java, Go e Node.js.

Ciò è particolarmente rilevante per le architetture di microservizi, in cui si potrebbe avere centinaia di microservizi (contenitori) in esecuzione. Con ASP.NET Core immagini (basate su runtime .NET Core) in Linux o Windows Nano, è possibile eseguire il sistema con un numero molto inferiore di server o le macchine virtuali, infine salvataggio i costi di infrastruttura che ospita.


>[!div class="step-by-step"]
[Precedente] (guidance.md generale) [Avanti] (net framework-contenitore scenarios.md)

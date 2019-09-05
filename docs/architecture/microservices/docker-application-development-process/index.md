---
title: Processo di sviluppo per le applicazioni basate su Docker
description: Ottenere una panoramica generale delle opzioni per lo sviluppo di applicazioni basate su Docker. Uso a scelta di Visual Studio per Windows, Visual Studio per Mac o Visual Studio Code per il supporto multipiattaforma (Windows, Mac e Linux).
ms.date: 09/27/2018
ms.openlocfilehash: a32b27f3d98ed7ebf63b637ec0c979c22ee8e1e8
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "70296134"
---
# <a name="development-process-for-docker-based-applications"></a>Processo di sviluppo per le applicazioni basate su Docker

*È possibile sviluppare applicazioni .NET incluse in contenitori come si preferisce, sia basandosi su IDE con Visual Studio e Visual Studio Tools per Docker oppure su editor/CLI con CLI di Docker e Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Ambiente di sviluppo per le app di Docker

### <a name="development-tool-choices-ide-or-editor"></a>Scelte per gli strumenti di sviluppo: IDE o editor

Microsoft include strumenti che è possibile usare per lo sviluppo di applicazioni di Docker, sia se si sceglie un IDE potente e completo che con un editor semplice e agile.

**Visual Studio (per Windows).** Quando si sviluppano applicazioni basate su Docker con Visual Studio, è consigliabile usare Visual Studio 2017 versione 15.7 o successiva, che include gli strumenti per Docker già incorporati. Gli strumenti per Docker consentono di sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente di Docker di destinazione. È possibile premere F5 per eseguire l'applicazione ed eseguirne il debug (con contenitore singolo o più contenitori) direttamente in un host Docker oppure premere CTRL + F5 per modificare e aggiornare l'applicazione senza dovere ricompilare il contenitore. Questa è la scelta di sviluppo più potente per le app basate su Docker.

**Visual Studio per Mac.** È un ambiente di sviluppo integrato (IDE), un'evoluzione di Xamarin Studio, in esecuzione in macOS e in grado di supportare Docker dalla metà del 2017. È la scelta più indicata per gli sviluppatori che lavorano in computer Mac che vogliono anche usare un potente IDE.

**Visual Studio Code e CLI di Docker**. Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Microsoft Visual Studio Code (codice Visual Studio) e l'interfaccia CLI di Docker. Questo approccio di sviluppo multipiattaforma è adatto per Mac, Linux e Windows. Inoltre, Visual Studio Code supporta le estensioni per Docker, quali IntelliSense per Dockerfile e le attività collegamento per eseguire i comandi di Docker dall'editor.

Installando [Docker Desktop Community Edition (CE)](https://hub.docker.com/search/?type=edition&offering=community), è possibile usare una singola interfaccia della riga di comando di Docker per creare app per Windows e Linux.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Visual Studio**. Sito ufficiale. \
  [https://visualstudio.microsoft.com/vs/](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

- **Visual Studio Code**. Sito ufficiale. \
  <https://code.visualstudio.com/download>

- **Docker Desktop per Windows Community Edition (CE)**  \
  [https://hub.docker.com/editions/community/docker-ce-desktop-windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
  
- **Docker Desktop per Mac Community Edition (CE)**  \
  [https://hub.docker.com/editions/community/docker-ce-desktop-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Linguaggi e framework .NET per contenitori di Docker

Come indicato nelle sezioni precedenti di questa guida, è possibile usare .NET Framework, .NET Core o il progetto Mono open source per lo sviluppo di applicazioni .NET incluse in contenitori di Docker. È possibile sviluppare in C\#, F\# o Visual Basic quando si usano contenitori di Linux o Windows, a seconda del framework .NET in uso. Per altri dettagli sui linguaggi .NET, vedere il post di blog [The .NET Language Strategy (La strategia dei linguaggi .NET)](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/).

>[!div class="step-by-step"]
>[Precedente](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
>[Successivo](docker-app-development-workflow.md)

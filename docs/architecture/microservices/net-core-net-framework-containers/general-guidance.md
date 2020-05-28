---
title: Indicazioni generali
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Indicazioni generali
ms.date: 09/11/2018
ms.openlocfilehash: e3bb4b8cf3e371c31d783fe4cfafeac282fb72b8
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144565"
---
# <a name="general-guidance"></a>Indicazioni generali

Questa sezione contiene un riepilogo dei casi in cui è consigliabile scegliere .NET Core o .NET Framework. Altri dettagli su questo tipo di scelta sono disponibili nelle sezioni successive.

È consigliabile usare .NET Core, con contenitori Linux o Windows, per l'applicazione server Docker in contenitori nei casi seguenti:

- Si hanno esigenze multipiattaforma. Ad esempio, si vogliono usare sia contenitori Windows sia contenitori Linux.

- L'architettura dell'applicazione si basa su microservizi.

- I contenitori devono essere avviati in modo rapido e il footprint per ogni contenitore deve essere ridotto al fine di garantire una migliore densità o più contenitori per unità hardware e ridurre al tempo stesso i costi.

In breve, quando si creano nuove applicazioni .NET in contenitori, considerare .NET Core come scelta predefinita. Offre più vantaggi e si adatta meglio alla filosofia dei contenitori e allo stile di lavoro.

Un altro vantaggio dato dall'uso di .NET Core consiste nel fatto che è possibile eseguire in modo affiancato le versioni .NET delle applicazioni che si trovano all'interno dello stesso computer. Questo vantaggio è più importante per i server o le macchine virtuali che non usano i contenitori, in quanto i contenitori isolano le versioni di .NET necessarie all'app. È tuttavia necessario che siano compatibili con il sistema operativo sottostante.

È consigliabile usare .NET Framework per l'applicazione server Docker in contenitori nei casi seguenti:

- L'applicazione attualmente usa .NET Framework ed è fortemente dipendente da Windows.

- È necessario usare API Windows che non sono supportate da .NET Core.

- È necessario usare librerie .NET di terze parti o pacchetti NuGet che non sono disponibili per .NET Core.

L'uso di .NET Framework in Docker può migliorare le esperienze di distribuzione e ridurne al minimo i problemi. Questo [scenario di trasferimento in modalità lift-and-shift](https://aka.ms/liftandshiftwithcontainersebook) è importante per l'inserimento in contenitori di applicazioni legacy che sono state originariamente sviluppate con .NET Framework tradizionale, ad esempio Web Form ASP.NET, app Web MVC o servizi WCF (Windows Communication Foundation).

### <a name="additional-resources"></a>Risorse aggiuntive

- **E-book: modernizzare le applicazioni .NET Framework esistenti con i contenitori di Azure e Windows**  
    <https://aka.ms/liftandshiftwithcontainersebook>

- **Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers** (App di esempio: modernizzazione delle app Web ASP.NET legacy usando contenitori Windows)  
    <https://aka.ms/eshopmodernizing>

>[!div class="step-by-step"]
>[Precedente](index.md) 
> [Avanti](net-core-container-scenarios.md)

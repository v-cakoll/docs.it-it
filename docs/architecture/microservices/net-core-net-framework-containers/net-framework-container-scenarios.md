---
title: Quando scegliere .NET Framework per i contenitori Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Quando scegliere .NET Framework per i contenitori Docker
ms.date: 01/07/2019
ms.openlocfilehash: e60572f33bda93663080b9d2e3504f0987b8483e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899709"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Quando scegliere .NET Framework per i contenitori Docker

Sebbene .NET Core offra vantaggi significativi per le nuove applicazioni e i nuovi schemi di applicazioni, .NET Framework continua a rappresentare la scelta naturale per molti scenari esistenti.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Migrazione delle applicazioni esistenti direttamente in un contenitore Windows Server

È possibile usare i contenitori Docker anche solo per semplificare la distribuzione, pur non creando microservizi. Ad esempio, se si vuole migliorare il flusso DevOps con Docker, i contenitori possono offrire ambienti di test con un isolamento migliore ed eliminare i problemi di distribuzione causati da dipendenze mancanti al momento dello spostamento in un ambiente di produzione. In questi casi, anche se si distribuisce un'applicazione monolitica, è consigliabile usare Docker e i contenitori Windows per le applicazioni .NET Framework correnti.

Nella maggior parte dei casi per questo scenario, non sarà necessario eseguire la migrazione delle applicazioni esistenti a .NET Core. È possibile usare contenitori Docker che includono .NET Framework tradizionale. Tuttavia, un approccio consigliato prevede di usare .NET Core per estendere un'applicazione esistente, ad esempio con la scrittura di un nuovo servizio in ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Utilizzo di pacchetti NuGet o di librerie .NET di terze parti non disponibili per .NET Core

Le librerie di terze parti stanno rapidamente adottando [.NET Standard](../../../standard/net-standard.md), che consente la condivisione di codice tra tutte le versioni di .NET incluso .NET Core. Con la libreria .NET Standard 2.0 e versioni successive la compatibilità della superficie dell'API tra framework diversi è aumentata in modo significativo e in .NET Core 2.x le applicazioni possono anche fare riferimento direttamente alle librerie .NET Framework esistenti. Vedere [.NET Framework 4.6.1 supporting .NET Standard 2.0](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#net-framework-461-supporting-net-standard-20) (Supporto di .NET Standard 2.0 in .NET Framework 4.6.1).

A novembre 2017 è stato anche rilasciato [Windows Compatibility Pack](../../../core/porting/windows-compat-pack.md) che consente di estendere la superficie dell'API disponibile per .NET Standard 2.0 in Windows. Questo pacchetto consente di ricompilare la maggior parte del codice esistente per .NET Standard 2.x con modifiche minime o nulle, da eseguire in Windows.

Tuttavia, nonostante questo avanzamento eccezionale a partire da .NET Standard 2.0 e .NET Core 2.1, in determinati casi per eseguire alcuni pacchetti NuGet potrebbe essere necessario usare Windows perché questi non supportano .NET Core. Se questi pacchetti sono vitali per l'applicazione, sarà necessario usare .NET Framework in contenitori Windows.

## <a name="using-net-technologies-not-available-for-net-core"></a>Utilizzo di tecnologie .NET non disponibili per .NET Core

Alcune tecnologie .NET Framework non sono disponibili nella versione corrente di .NET Core, ovvero la versione 2.2 al momento della stesura del presente documento. Alcune saranno disponibili in versioni future di .NET Core (.NET Core 2.x), ma altre non si applicano ai nuovi schemi di applicazioni basati su .NET Core ed è possibile che non vengano mai rese disponibili.

L'elenco seguente illustra la maggior parte delle tecnologie non disponibili in .NET Core 2.x:

- Web Form ASP.NET. Questa tecnologia è disponibile solo in .NET Framework. Attualmente non è previsto il trasferimento di Web Form ASP.NET in .NET Core.

- Servizi WCF. Anche se, dalla metà del 2017, è disponibile una [libreria WCF client](https://github.com/dotnet/wcf) per l'utilizzo di servizi WCF da .NET Core, l'implementazione di server WCF è disponibile solo in .NET Framework. Questo scenario potrebbe essere considerato per le versioni future di .NET Core. Anche alcune API sono considerate per l'inclusione in [Windows Compatibility Pack](../../../core/porting/windows-compat-pack.md).

- Servizi correlati ai flussi di lavoro. Windows Workflow Foundation (WF), Servizi flusso di lavoro (WCF e WF in un unico servizio) e WCF Data Services (in precedenza "ADO.NET Data Services") sono disponibili solo in .NET Framework. Al momento non è prevista l'introduzione in .NET Core.

Oltre alle tecnologie elencate nella [roadmap per .NET Core](https://github.com/dotnet/aspnetcore/wiki/Roadmap) ufficiale, è possibile che in .NET Core vengano rese disponibili altre funzionalità. Per un elenco completo, osservare gli elementi contrassegnati come [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) nella pagina CoreFX del sito GitHub. Si noti che questo elenco non rappresenta un impegno da parte di Microsoft per rendere disponibili tali componenti in .NET Core, ma mostra solo il desiderio della community di procedere in tal senso. Se si è interessati a uno dei componenti elencati in precedenza, è consigliabile partecipare alle discussioni su GitHub per far valere la propria opinione. Se si ritiene che qualcosa non sia presente, inserire [un nuovo problema nel repository di runtime](https://github.com/dotnet/runtime/issues/new).

Anche se .NET Core 3 (in corso di sviluppo al momento della stesura di questo articolo) includerà il supporto per molte delle API di .NET Framework esistenti, queste API sono progettate per il desktop e quindi non sono attualmente utili per i contenitori.

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>Utilizzo di una piattaforma o di un'API che non supporta .NET Core

Alcune piattaforme Microsoft o di terze parti non supportano .NET Core. Ad esempio, alcuni servizi di Azure forniscono un SDK non ancora disponibile per l'utilizzo in .NET Core. Si tratta di un problema temporaneo, perché alla fine tutti i servizi di Azure useranno .NET Core. Ad esempio, [Azure DocumentDB SDK per .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core) è stato rilasciato in anteprima il 16 novembre 2016 e ora è disponibile a livello generale come versione stabile.

Nel frattempo, se una piattaforma o un servizio in Azure ancora non supporta .NET Core tramite l'API client, è possibile usare l'API REST equivalente del servizio di Azure o l'SDK client in .NET Framework.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Guida a .NET Core** \
  [https://docs.microsoft.com/dotnet/core/index](../../../core/index.md)

- **Porting from .NET Framework to .NET Core** \ (Portabilità da .NET Framework a .NET Core)
  [https://docs.microsoft.com/dotnet/core/porting/index](../../../core/porting/index.md)

- **Guida a .NET Core in docker** \
  [https://docs.microsoft.com/dotnet/core/docker/introduction](../../../core/docker/introduction.md)

- **Componenti dell'architettura .NET** \
  [https://docs.microsoft.com/dotnet/standard/components](../../../standard/components.md)

>[!div class="step-by-step"]
>[Precedente](net-core-container-scenarios.md)
>[Successivo](container-framework-choice-factors.md)

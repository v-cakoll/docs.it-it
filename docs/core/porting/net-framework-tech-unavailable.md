---
title: Tecnologie di .NET Framework non disponibili in .NET Core
description: Informazioni sulle tecnologie di .NET Framework che non sono disponibili in .NET Core
author: cartermp
ms.author: mairaw
ms.date: 12/7/2018
ms.openlocfilehash: 8b43c15a942e0effab486e5399325bec746484a2
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904876"
---
# <a name="net-framework-technologies-unavailable-on-net-core"></a>Tecnologie di .NET Framework non disponibili in .NET Core

Varie tecnologie disponibili per le librerie .NET Framework non sono disponibili per l'uso con .NET Core, ad esempio AppDomain, servizi remoti, sicurezza dall'accesso di codice e trasparenza della sicurezza. Se le librerie si basano su una o più di queste tecnologie, prendere in considerazione gli approcci alternativi descritti di seguito. Per altre informazioni sulla compatibilità delle API, il team CoreFX gestisce un [elenco aggiornato delle modifiche di comportamento, dei problemi di compatibilità e delle API deprecate/legacy](https://github.com/dotnet/corefx/wiki/ApiCompat) su GitHub.

Il fatto che un'API o una tecnologia non sia attualmente implementata non implica che sia intenzionalmente non supportata. È consigliabile cercare prima di tutto .NET Core nei repository di GitHub per vedere se un particolare problema rilevato è correlato alla progettazione. Se non si trova questo indicatore, segnalare il problema nella sezione dei [problemi del repository dotnet/corefx](https://github.com/dotnet/corefx/issues) su GitHub per richiedere API e tecnologie specifiche. [Le richieste relative alla portabilità nei problemi](https://github.com/dotnet/corefx/labels/port-to-core) sono contrassegnate con l'etichetta `port-to-core`.

## <a name="appdomains"></a>AppDomain

I domini applicazione (AppDomain) consentono di isolare le app l'una dall'altra. Per gli AppDomain è richiesto il supporto di runtime e sono in genere alquanto costosi. La creazione di domini applicazione aggiuntivi non è supportata. Non è prevista l'aggiunta di questa funzionalità in futuro. Per l'isolamento del codice, è consigliabile separare i processi o usare i contenitori in alternativa. Per il caricamento dinamico di assembly è consigliabile usare la nuova classe <xref:System.Runtime.Loader.AssemblyLoadContext>.

Per semplificare la migrazione di codice da .NET Framework, .NET Core espone parte della superficie dell'API <xref:System.AppDomain>. Alcune delle API funzionano normalmente, (ad esempio <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), alcuni membri non eseguono alcuna operazione (ad esempio, <xref:System.AppDomain.SetCachePath%2A>) e alcuni generano <xref:System.PlatformNotSupportedException> (ad esempio, <xref:System.AppDomain.CreateDomain%2A>). Controllare i tipi usati in base al [`System.AppDomain`codice sorgente di riferimento](https://github.com/dotnet/corefx/blob/master/src/System.Runtime.Extensions/src/System/AppDomain.cs) nel [repository GitHub dotnet/corefx](https://github.com/dotnet/corefx) assicurandosi di selezionare il ramo corrispondente alla versione implementata.

## <a name="remoting"></a>Servizi remoti

L'architettura dei servizi remoti di .NET è stata identificata come problematica. Questi servizi vengono usati per le comunicazioni tra AppDomain, non più supportate. Per i servizi remoti è richiesto anche il supporto del runtime, costoso da gestire. Per questi motivi, i servizi remoti di .NET non sono supportati in .NET Core e non è prevista l'aggiunta del supporto in futuro.

Per le comunicazioni tra processi, è possibile usare i meccanismi di comunicazione interprocesso (IPC, Inter-Process Communication) in alternativa ai servizi remoti, come la classe <xref:System.IO.Pipes> o <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>.

Per le comunicazioni tra computer, usare una soluzione basata su rete in alternativa. Preferibilmente, usare un protocollo di testo normale con basso overhead, come HTTP. Il [server Web Kestrel](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), ovvero il server Web usato da ASP.NET Core, rappresenta un'opzione praticabile in questo caso. Valutare anche l'uso di <xref:System.Net.Sockets> per gli scenari basati sulla rete per le comunicazioni tra computer. Per informazioni su altre opzioni, vedere [.NET Open Source Developer Projects: Messaging](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging) (Progetti di sviluppo open source .NET: Messaggistica).

## <a name="code-access-security-cas"></a>Sicurezza per l'accesso al codice (CAS, Code Access Security)

Il sandboxing, che si basa sul runtime o sul framework per vincolare le risorse usate o eseguite da un'applicazione gestita o una libreria, [non è supportato in .NET Framework](~/docs/framework/misc/code-access-security.md) e pertanto non è supportato neanche in .NET Core. Esistono troppi casi in .NET Framework e nel runtime in cui si verifica un'elevazione dei privilegi per continuare a considerare la sicurezza dall'accesso di codice come limite di sicurezza. La sicurezza dall'accesso di codice, inoltre, rende l'implementazione più complicata e spesso ha implicazioni a livello di prestazioni della correttezza per le applicazioni che non intendono usare questo meccanismo di sicurezza.

Usare i limiti di sicurezza forniti dal sistema operativo, ad esempio la virtualizzazione, i contenitori o gli account utente, per eseguire i processi con il set di privilegi minimo.

## <a name="security-transparency"></a>Trasparenza della sicurezza

Analogamente alla sicurezza dall'accesso di codice, la trasparenza della sicurezza separa il codice in modalità sandbox dal codice critico per la sicurezza in modalità dichiarativa, ma [non è più supportata come limite di sicurezza](~/docs/framework/misc/security-transparent-code.md). Questa funzionalità è ampiamente usata da Silverlight. 

Usare i limiti di sicurezza forniti dal sistema operativo, ad esempio la virtualizzazione, i contenitori o gli account utente, per eseguire i processi con il set di privilegi più ridotto.

>[!div class="step-by-step"]
>[avanti](third-party-deps.md)

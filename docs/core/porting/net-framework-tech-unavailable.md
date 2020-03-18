---
title: Tecnologie di .NET Framework non disponibili in .NET Core
titleSuffix: ''
description: Informazioni sulle tecnologie di .NET Framework che non sono disponibili in .NET Core
author: cartermp
ms.date: 04/30/2019
ms.openlocfilehash: bd2488de653ecdfed261100b4c9019bea58fcab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77092941"
---
# <a name="net-framework-technologies-unavailable-on-net-core"></a>Tecnologie di .NET Framework non disponibili in .NET Core

Diverse tecnologie disponibili per le librerie .NET Framework non sono disponibili per l'utilizzo con .NET Core, ad esempio AppDomains, Remoting, Code Access Security (CAS), Security Transparency e System.EnterpriseServices. Se le librerie si basano su una o più di queste tecnologie, prendere in considerazione gli approcci alternativi descritti di seguito. Per ulteriori informazioni sulla compatibilità delle API, vedere Modifiche di rilievo di [.NET Core .NET Core](../compatibility/breaking-changes.md).

Il fatto che un'API o una tecnologia non sia attualmente implementata non implica che sia intenzionalmente non supportata. Cercare nei repository GitHub per .NET Core per vedere se un particolare problema che si verifica è in base alla progettazione. Se non si trova un indicatore di questo tipo, presentare un problema nel [repository dotnet/runtime](https://github.com/dotnet/runtime/issues) per richiedere API e tecnologie specifiche. I problemi relativi alla conversione delle richieste sono contrassegnati con l'etichetta [da porta a core.](https://github.com/dotnet/runtime/labels/port-to-core)

## <a name="appdomains"></a>AppDomain

I domini applicazione (AppDomain) consentono di isolare le app l'una dall'altra. Per gli AppDomain è richiesto il supporto di runtime e sono in genere alquanto costosi. La creazione di domini app aggiuntivi non è supportata e non è prevista l'aggiunta di questa funzionalità in futuro. Per l'isolamento del codice, usare processi o contenitori separati come alternativa. Per caricare dinamicamente <xref:System.Runtime.Loader.AssemblyLoadContext> gli assembly, utilizzare la classe .

Per semplificare la migrazione di codice da .NET Framework, .NET Core espone parte della superficie dell'API <xref:System.AppDomain>. Alcune delle API funzionano normalmente, (ad esempio <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), alcuni membri non eseguono alcuna operazione (ad esempio, <xref:System.AppDomain.SetCachePath%2A>) e alcuni generano <xref:System.PlatformNotSupportedException> (ad esempio, <xref:System.AppDomain.CreateDomain%2A>). Controllare i tipi utilizzati rispetto [ `System.AppDomain` all'origine](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Private.CoreLib/src/System/AppDomain.cs) di riferimento nel [repository GitHub dotnet/runtime](https://github.com/dotnet/runtime). Assicurarsi di selezionare il ramo che corrisponde alla versione implementata.

## <a name="remoting"></a>Comunicazione remota

L'architettura dei servizi remoti di .NET è stata identificata come problematica. Questi servizi vengono usati per le comunicazioni tra AppDomain, non più supportate. Per i servizi remoti è richiesto anche il supporto del runtime, costoso da gestire. Per questi motivi, i servizi remoti di .NET non sono supportati in .NET Core e non è prevista l'aggiunta del supporto in futuro.

Per la comunicazione tra i processi, considerare i meccanismi di comunicazione tra processi <xref:System.IO.Pipes> (IPC) come alternativa ai servizi remoti, ad esempio la classe o la <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> classe.

Per le comunicazioni tra computer, usare una soluzione basata su rete in alternativa. Preferibilmente, usare un protocollo di testo normale con basso overhead, come HTTP. Il [server Web Kestrel](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), ovvero il server Web usato da ASP.NET Core, rappresenta un'opzione praticabile in questo caso. Considerare inoltre <xref:System.Net.Sockets> l'utilizzo per scenari tra computer basati sulla rete. Per informazioni su altre opzioni, vedere [.NET Open Source Developer Projects: Messaging](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging) (Progetti di sviluppo open source .NET: Messaggistica).

## <a name="code-access-security-cas"></a>Sicurezza dall'accesso di codice (CAS, Code Access Security)

Il sandboxing, che si basa sul runtime o sul framework per vincolare le risorse usate o eseguite da un'applicazione gestita o una libreria, [non è supportato in .NET Framework](../../framework/misc/code-access-security.md) e pertanto non è supportato neanche in .NET Core. Esistono troppi casi in .NET Framework e nel runtime in cui si verifica un'elevazione dei privilegi per continuare a considerare la sicurezza dall'accesso di codice come limite di sicurezza. La sicurezza dall'accesso di codice, inoltre, rende l'implementazione più complicata e spesso ha implicazioni a livello di prestazioni della correttezza per le applicazioni che non intendono usare questo meccanismo di sicurezza.

Utilizzare i limiti di sicurezza forniti dal sistema operativo, ad esempio virtualizzazione, contenitori o account utente, per l'esecuzione di processi con il set minimo di privilegi.

## <a name="security-transparency"></a>Trasparenza della sicurezza

Analogamente alla sicurezza dall'accesso di codice, la trasparenza della sicurezza separa il codice in modalità sandbox dal codice critico per la sicurezza in modalità dichiarativa, ma [non è più supportata come limite di sicurezza](../../framework/misc/security-transparent-code.md). Questa funzionalità è ampiamente usata da Silverlight.

Utilizzare i limiti di sicurezza forniti dal sistema operativo, ad esempio la virtualizzazione, i contenitori o gli account utente, per l'esecuzione di processi con il set minimo di privilegi.

## <a name="systementerpriseservices"></a>System.EnterpriseServices

System.EnterpriseServices (COM+) non è supportato da .NET Core.

## <a name="see-also"></a>Vedere anche

- [Panoramica del porting da .NET Framework a .NET Core](../porting/index.md)

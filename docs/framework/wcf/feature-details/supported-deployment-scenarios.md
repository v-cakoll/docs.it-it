---
title: Scenari di distribuzione supportati
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 5be9ab3d300da2095a45846d334512382b4067f6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743457"
---
# <a name="supported-deployment-scenarios"></a>Scenari di distribuzione supportati

Il subset di funzionalità di Windows Communication Foundation (WCF) supportate per l'utilizzo in applicazioni parzialmente attendibili è progettato per soddisfare i requisiti di alcuni scenari, ma non di tutti, per l'utilizzo di WCF. Sul server, WCF soddisfa i requisiti dei provider di hosting condiviso a livello di Internet che eseguono applicazioni di terze parti nel set di autorizzazioni di attendibilità media ASP.NET 2,0 per motivi di sicurezza. Sul client, il supporto per l'attendibilità parziale WCF è progettato per soddisfare i requisiti delle tecnologie di distribuzione, ad esempio la [distribuzione ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) o la tecnologia applicazione browser XAML di WPF, che consente la distribuzione semplice e sicura di applicazioni desktop da siti non attendibili.

## <a name="minimum-permission-requirements"></a>Requisiti minimi per le autorizzazioni

WCF supporta un sottoinsieme di funzionalità in applicazioni in esecuzione con uno dei set di autorizzazioni denominati standard seguenti:

- Autorizzazioni Attendibilità media

- Autorizzazioni Area Internet

Il tentativo di utilizzare WCF in applicazioni parzialmente attendibili con autorizzazioni più restrittive può generare eccezioni di sicurezza in fase di esecuzione.

Per altre informazioni sulle funzionalità supportate in questi set di autorizzazioni, vedere [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).

## <a name="partial-trust-on-the-server"></a>Attendibilità parziale nel server

Molti provider commerciali di servizi di hosting di applicazioni Web ASP.NET richiedono che le applicazioni in esecuzione nei server vengano eseguite nel set di autorizzazioni di attendibilità media ASP.NET 2,0. I servizi WCF possono essere eseguiti in questi ambienti purché usino il <xref:System.ServiceModel.BasicHttpBinding>, il <xref:System.ServiceModel.WebHttpBinding>o il <xref:System.ServiceModel.WSHttpBinding> con sicurezza a livello di trasporto.

I servizi WCF in esecuzione in ambienti di hosting con attendibilità media possono fungere anche da servizi di livello intermedio inviando messaggi ad altri server in risposta alle richieste dei client. Gli scenari di livello medio nel server sono supportati se l'ambiente host ha concesso all'applicazione la <xref:System.Net.WebPermission> appropriata per effettuare richieste in uscita al server desiderato.

Oltre alla messaggistica SOAP che utilizza una delle associazioni SOAP supportate, WCF supporta il <xref:System.ServiceModel.WebHttpBinding> per la creazione di servizi di tipo Web in applicazioni parzialmente attendibili. Le funzionalità [modello di programmazione HTTP Web WCF](wcf-web-http-programming-model.md), [diffusione WCF](wcf-syndication.md)e [Integrazione AJAX e supporto JSON](ajax-integration-and-json-support.md) di WCF sono tutte supportate in attendibilità parziale.

I servizi flussi di lavoro richiedono autorizzazioni di attendibilità totale e non possono essere utilizzati in applicazioni parzialmente attendibili.

Per altre informazioni, vedere [procedura: usare l'attendibilità media in ASP.NET 2,0](https://docs.microsoft.com/previous-versions/msp-n-p/ff648344(v=pandp.10)).

## <a name="partial-trust-on-the-client"></a>Attendibilità parziale nel client

Quando si scarica ed esegue codice dai siti Internet non attendibili, è necessario adottare determinate precauzioni di sicurezza. La [distribuzione ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) e la tecnologia applicazione browser XAML (XBAP) di WPF usano l'attendibilità parziale per concedere autorizzazioni limitate (area Internet) a codice non attendibile.

È possibile utilizzare WCF per comunicare con server remoti da applicazioni parzialmente attendibili distribuite tramite la [distribuzione ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) o XBAP. Il set di autorizzazioni dell'area Internet include <xref:System.Net.WebPermission> per l'host di origine, che consente a queste applicazioni di comunicare con il server di origine utilizzando una qualsiasi delle associazioni WCF supportate descritte in [compatibilità delle funzionalità con attendibilità parziale](partial-trust-feature-compatibility.md).

## <a name="see-also"></a>Vedere anche

- [Sicurezza dall'accesso di codice](../../misc/code-access-security.md)
- [Panoramica delle applicazioni Windows Presentation Foundation ospitate da browser](../../wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [Attendibilità parziale](partial-trust.md)
- [Livelli di attendibilità ASP.NET e file di criteri](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))

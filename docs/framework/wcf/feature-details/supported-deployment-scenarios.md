---
title: Scenari di distribuzione supportati - WCF
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 2da55176cbfe618b332f2df210e3e1c0516b17ae
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170048"
---
# <a name="supported-deployment-scenarios"></a>Scenari di distribuzione supportati

Il sottoinsieme delle funzionalità di Windows Communication Foundation (WCF) supportati per l'uso in applicazioni parzialmente attendibili è progettato per soddisfare i requisiti degli scenari di alcuni, ma non tutti, per l'utilizzo di WCF. Nel server, WCF soddisfi i requisiti del provider di hosting condiviso che eseguono le applicazioni di terze parti nell'autorizzazione di attendibilità media ASP.NET 2.0 è impostato per motivi di sicurezza basata su Internet. Sul client, supporto con attendibilità parziale WCF è progettato per soddisfare i requisiti di tecnologie di distribuzione, ad esempio [distribuzione ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) o la tecnologia applicazione Browser XAML di WPF, che consentono la distribuzione sicura e uniforme di applicazioni desktop da siti non attendibili.

## <a name="minimum-permission-requirements"></a>Requisiti minimi di autorizzazione

WCF supporta un subset di funzionalità nelle applicazioni in esecuzione in uno dei set di autorizzazioni denominati standard seguenti:

- Autorizzazioni Attendibilità media

- Autorizzazioni Area Internet

Tentativo di utilizzare WCF in applicazioni parzialmente attendibili con autorizzazioni più restrittive può generare eccezioni di sicurezza in fase di esecuzione.

Per altre informazioni sulle funzionalità supportate in questi set di autorizzazioni, vedere [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).

## <a name="partial-trust-on-the-server"></a>Attendibilità parziale nel server

Numerosi provider commerciali di applicazione Web ASP.NET che ospita i servizi obbliga a usare le applicazioni in esecuzione nei loro server vengano eseguite nel set di autorizzazioni attendibilità media ASP.NET 2.0. Servizi WCF possono essere eseguiti in questi ambienti condizione che utilizzino il <xref:System.ServiceModel.BasicHttpBinding>, il <xref:System.ServiceModel.WebHttpBinding>, o <xref:System.ServiceModel.WSHttpBinding> con sicurezza a livello di trasporto.

Servizi WCF in esecuzione in ambienti host ad attendibilità media possono fungere anche servizi di livello intermedio inviando messaggi ad altri server in risposta alle richieste dei client. Gli scenari di livello medio nel server sono supportati se l'ambiente host ha concesso all'applicazione la <xref:System.Net.WebPermission> appropriata per effettuare richieste in uscita al server desiderato.

Oltre alla messaggistica SOAP tramite una delle associazioni SOAP supportate, WCF supporta i <xref:System.ServiceModel.WebHttpBinding> per la creazione di servizi Web in applicazioni parzialmente attendibili. Il [modello di programmazione HTTP Web WCF](wcf-web-http-programming-model.md), [diffusione WCF](wcf-syndication.md), e [integrazione AJAX e supporto JSON](ajax-integration-and-json-support.md) tutte le funzionalità di WCF sono supportate in ambiente parzialmente attendibile.

I servizi flussi di lavoro richiedono autorizzazioni di attendibilità totale e non possono essere utilizzati in applicazioni parzialmente attendibili.

Per altre informazioni, vedere [Procedura: Usare l'attendibilità media in ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=84603).

## <a name="partial-trust-on-the-client"></a>Attendibilità parziale nel client

Quando si scarica ed esegue codice dai siti Internet non attendibili, è necessario adottare determinate precauzioni di sicurezza. Entrambe [distribuzione ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) allo stesso modo XAML Browser Application tecnologia (XBAP di WPF) di attendibilità parziale per concedere autorizzazioni limitate (area Internet) al codice non attendibile.

WCF può essere utilizzato per comunicare con server remoti da applicazioni parzialmente attendibili distribuite tramite [distribuzione ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) o XBAP. Il set di autorizzazioni area Internet include <xref:System.Net.WebPermission> per l'host di origine, in modo da comunicare con il proprio server di origine usando uno dei binding WCF supportate descritte in queste applicazioni [Partial Trust Feature Compatibility ](partial-trust-feature-compatibility.md).

## <a name="see-also"></a>Vedere anche

- [Sicurezza dall'accesso di codice](../../misc/code-access-security.md)
- [Panoramica di Windows Presentation Foundation ospitate da Browser](../../wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [Attendibilità parziale](partial-trust.md)
- [I livelli di attendibilità di ASP.NET e i file dei criteri](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))

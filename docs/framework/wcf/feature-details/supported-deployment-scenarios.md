---
title: Scenari di distribuzione supportati
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: a86fd9d50b2bdfa2daafa3bec98802d10a1efef5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421073"
---
# <a name="supported-deployment-scenarios"></a>Scenari di distribuzione supportati
Il sottoinsieme delle funzionalità di Windows Communication Foundation (WCF) supportati per l'uso in applicazioni parzialmente attendibili è progettato per soddisfare i requisiti degli scenari di alcuni, ma non tutti, per l'utilizzo di WCF. Nel server, WCF in uso soddisfi i requisiti a livello di Internet condiviso ai provider di hosting che eseguono le applicazioni di terze parti nel [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] Medium Trust set di autorizzazioni per motivi di sicurezza. Sul client, supporto con attendibilità parziale WCF è progettato per soddisfare i requisiti di tecnologie di distribuzione, ad esempio [distribuzione ClickOnce](https://go.microsoft.com/fwlink/?LinkId=83712) o [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]della tecnologia applicazione Browser XAML, che consente facile e sicuro distribuzione di applicazioni desktop da siti non attendibili.  
  
## <a name="minimum-permission-requirements"></a>Requisiti di autorizzazione minimi  
 WCF supporta un subset di funzionalità nelle applicazioni in esecuzione in uno dei set di autorizzazioni denominati standard seguenti:  
  
-   Autorizzazioni Attendibilità media  
  
-   Autorizzazioni Area Internet  
  
 Tentativo di utilizzare WCF in applicazioni parzialmente attendibili con autorizzazioni più restrittive può generare eccezioni di sicurezza in fase di esecuzione.  
  
 Per altre informazioni sulle funzionalità supportate in questi set di autorizzazioni, vedere [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="partial-trust-on-the-server"></a>Attendibilità parziale nel server  
 Numerosi provider commerciali di servizi host di applicazioni Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] richiedono che le applicazioni che sono in esecuzione nei loro server vengano eseguite nel set di autorizzazioni di Attendibilità media [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] . Servizi WCF possono essere eseguiti in questi ambienti condizione che utilizzino il <xref:System.ServiceModel.BasicHttpBinding>, il <xref:System.ServiceModel.WebHttpBinding>, o il <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> con la sicurezza a livello di trasporto.  
  
 Servizi WCF in esecuzione in ambienti host ad attendibilità media possono fungere anche servizi di livello intermedio inviando messaggi ad altri server in risposta alle richieste dei client. Gli scenari di livello medio nel server sono supportati se l'ambiente host ha concesso all'applicazione la <xref:System.Net.WebPermission> appropriata per effettuare richieste in uscita al server desiderato.  
  
 Oltre alla messaggistica SOAP tramite una delle associazioni SOAP supportate, WCF supporta i <xref:System.ServiceModel.WebHttpBinding> per la creazione di servizi Web in applicazioni parzialmente attendibili. Il [modello di programmazione HTTP Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [diffusione WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), e [integrazione AJAX e supporto JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) tutte le funzionalità di WCF sono supportate in ambiente parzialmente attendibile.  
  
 I servizi flussi di lavoro richiedono autorizzazioni di attendibilità totale e non possono essere utilizzati in applicazioni parzialmente attendibili.  
  
 Per altre informazioni, vedere [procedura: usare attendibilità media in ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=84603).  
  
## <a name="partial-trust-on-the-client"></a>Attendibilità parziale nel client  
 Quando si scarica ed esegue codice dai siti Internet non attendibili, è necessario adottare determinate precauzioni di sicurezza. Entrambe [distribuzione ClickOnce](https://go.microsoft.com/fwlink/?LinkId=83712) e [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]dell'applicazione Browser XAML (XBAP) tecnologia avvalgono dell'attendibilità parziale per concedere autorizzazioni limitate (area Internet) al codice non attendibile.  
  
 WCF può essere utilizzato per comunicare con server remoti da applicazioni parzialmente attendibili distribuite tramite [distribuzione ClickOnce](https://go.microsoft.com/fwlink/?LinkId=83712) o XBAP. Il set di autorizzazioni area Internet include <xref:System.Net.WebPermission> per l'host di origine, in modo da comunicare con il proprio server di origine usando uno dei binding WCF supportate descritte in queste applicazioni [Partial Trust Feature Compatibility ](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza dall'accesso di codice](https://go.microsoft.com/fwlink/?LinkId=83717)  
 [Panoramica di Windows Presentation Foundation ospitate da Browser](https://go.microsoft.com/fwlink/?LinkId=98397)  
 [Attendibilità parziale](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 [Attendibilità media ASP.Net](https://go.microsoft.com/fwlink/?LinkId=69328)

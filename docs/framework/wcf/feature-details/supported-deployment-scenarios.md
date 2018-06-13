---
title: Scenari di distribuzione supportati
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: d0afd12b1c17f9356146aa13c90f8db65ed9ec0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498062"
---
# <a name="supported-deployment-scenarios"></a>Scenari di distribuzione supportati
Il sottoinsieme delle funzionalità di Windows Communication Foundation (WCF) supportate per l'utilizzo in applicazioni parzialmente attendibili è progettato per soddisfare i requisiti di alcuni scenari, ma non tutti, per l'utilizzo di WCF. Nel server, WCF soddisfa i requisiti a livello di Internet condiviso ai provider di hosting che eseguono applicazioni di terze parti nel [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] autorizzazione di attendibilità media impostata per ragioni di sicurezza. Nel client, il supporto di attendibilità parziale di WCF è progettato per soddisfare i requisiti di tecnologie di distribuzione, ad esempio [distribuzione ClickOnce](http://go.microsoft.com/fwlink/?LinkId=83712) o [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]della tecnologia applicazione Browser XAML, che consentono di semplici e sicure distribuzione di applicazioni desktop da siti non attendibili.  
  
## <a name="minimum-permission-requirements"></a>Requisiti di autorizzazione minimi  
 WCF supporta un sottoinsieme di funzionalità nelle applicazioni eseguite con uno dei set di autorizzazioni denominati standard seguenti:  
  
-   Autorizzazioni Attendibilità media  
  
-   Autorizzazioni Area Internet  
  
 Tentativo di utilizzare WCF in applicazioni parzialmente attendibili con le autorizzazioni più restrittive può generare eccezioni di sicurezza in fase di esecuzione.  
  
 Per altre informazioni sulle funzionalità supportate in questi set di autorizzazioni, vedere [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="partial-trust-on-the-server"></a>Attendibilità parziale nel server  
 Numerosi provider commerciali di servizi host di applicazioni Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] richiedono che le applicazioni che sono in esecuzione nei loro server vengano eseguite nel set di autorizzazioni di Attendibilità media [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] . Servizi WCF possono essere eseguiti in questi ambienti condizione che utilizzino il <xref:System.ServiceModel.BasicHttpBinding>, il <xref:System.ServiceModel.WebHttpBinding>, o il <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> con la sicurezza a livello di trasporto.  
  
 Servizi WCF in esecuzione in ambienti host ad attendibilità media possono fungere anche da servizi di livello intermedio inviando messaggi ad altri server in risposta alle richieste del client. Gli scenari di livello medio nel server sono supportati se l'ambiente host ha concesso all'applicazione la <xref:System.Net.WebPermission> appropriata per effettuare richieste in uscita al server desiderato.  
  
 Oltre alla messaggistica SOAP tramite una delle associazioni SOAP supportate, WCF supporta la <xref:System.ServiceModel.WebHttpBinding> per la compilazione di servizi in stile Web in applicazioni parzialmente attendibili. Il [modello di programmazione HTTP Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [diffusione WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), e [integrazione AJAX e supporto JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) funzionalità di WCF sono supportate nell'attendibilità parziale.  
  
 I servizi flussi di lavoro richiedono autorizzazioni di attendibilità totale e non possono essere utilizzati in applicazioni parzialmente attendibili.  
  
 Per altre informazioni, vedere [procedura: utilizzare ad attendibilità media in ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=84603).  
  
## <a name="partial-trust-on-the-client"></a>Attendibilità parziale nel client  
 Quando si scarica ed esegue codice dai siti Internet non attendibili, è necessario adottare determinate precauzioni di sicurezza. La [distribuzione ClickOnce](http://go.microsoft.com/fwlink/?LinkId=83712) e la tecnologia Applicazione browser XAML (XBAP) di [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]usano entrambe l'attendibilità parziale per concedere autorizzazioni limitate (area Internet) al codice non attendibile.  
  
 WCF può essere utilizzato per comunicare con server remoti da applicazioni parzialmente attendibili distribuite tramite la [distribuzione ClickOnce](http://go.microsoft.com/fwlink/?LinkId=83712) o XBAP. Set di autorizzazioni area Internet include <xref:System.Net.WebPermission> per l'host di origine, in modo da comunicare con il proprio server di origine usando una qualsiasi delle associazioni WCF supportate descritte in queste applicazioni [compatibilità di funzionalità di attendibilità parziale ](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza dall'accesso di codice](http://go.microsoft.com/fwlink/?LinkId=83717)  
 [Panoramica di Windows Presentation Foundation ospitate da Browser](http://go.microsoft.com/fwlink/?LinkId=98397)  
 [Attendibilità parziale](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 [Attendibilità media ASP.Net](http://go.microsoft.com/fwlink/?LinkId=69328)

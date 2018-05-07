---
title: Servizi WCF e ASP.NET
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: 6cfd4f8a5dc2a7835cba409a37b09166e49e8df3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-services-and-aspnet"></a>Servizi WCF e ASP.NET
Questo argomento viene illustrato l'hosting Windows Communication Foundation (WCF) services side-by-side con ASP.NET e in modalità di compatibilità ASP.NET.  
  
## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Hosting di WCF affiancato ad ASP.NET  
 Servizi WCF ospitati in Internet Information Services (IIS) possono trovarsi con. Le pagine ASPX e servizi Web ASMX all'interno di un solo dominio applicazione comune. ASP.NET fornisce servizi di infrastruttura comuni quali la gestione di AppDomain e compilazione dinamica per WCF e il runtime HTTP ASP.NET. La configurazione predefinita per WCF è side-by-side con ASP.NET.  
  
 ![Servizi WCF e ASP .NET: condivisione dello stato](../../../../docs/framework/wcf/feature-details/media/hostingwcfwithaspnet.gif "HostingWCFwithASPNET")  
  
 Il runtime HTTP ASP.NET gestisce richieste ASP.NET ma non partecipa all'elaborazione delle richieste destinate a servizi WCF, anche se questi servizi sono ospitati nello stesso AppDomain è contenuto ASP.NET. Al contrario, il modello di servizio WCF consente di intercettare i messaggi indirizzati ai servizi WCF e li instrada tramite lo stack di trasporto/canale WCF.  
  
 I risultati del modello affiancato sono i seguenti:  
  
-   Servizi WCF e ASP.NET possono condividere lo stato dell'AppDomain. Poiché i due Framework possono coesistere nello stesso AppDomain, WCF possono inoltre condividere lo stato dell'AppDomain con ASP.NET (inclusi variabili statiche, eventi e così via).  
  
-   Servizi WCF si comportano in modo coerente, indipendentemente dall'ambiente host e dal trasporto. Il runtime HTTP ASP.NET è intenzionalmente accoppiato all'ambiente host IIS/ASP.NET e alla comunicazione HTTP. Al contrario, WCF è progettato per comportarsi coerentemente in diversi ambienti host (WCF si comporta coerentemente all'interno e all'esterno di IIS) e trasporti (un servizio ospitato in IIS 7.0 e versioni successivo ha un comportamento coerente in tutti gli endpoint che espone, anche se alcuni di questi usano protocolli diversi da HTTP).  
  
-   All'interno di un AppDomain, le funzionalità implementate dal runtime HTTP si applicano al contenuto ASP.NET ma non a WCF. Molte funzionalità specifiche di HTTP della piattaforma dell'applicazione ASP.NET non si applicano ai servizi WCF ospitati in un AppDomain con contenuto ASP.NET. Ne sono esempi le seguenti:  
  
    -   HttpContext: <xref:System.Web.HttpContext.Current%2A> è sempre `null` quando si accede da un servizio WCF. Utilizzare <!--zz <xref:System.ServiceModel.OperationContext.Current.RequestContext>--> `RequestContext` invece.  
  
    -   Autorizzazione basata su file: modello di sicurezza di WCF non consente l'elenco di controllo di accesso (ACL) applicato al file con estensione svc del servizio quando si decide se una richiesta di servizio è autorizzata.  
  
    -   Autorizzazione URL basata sulla configurazione: Allo stesso modo, il modello di sicurezza WCF non segue alcuna regola di autorizzazione basata su URL specificato in System. Web \<autorizzazione > elemento di configurazione. Queste impostazioni vengono ignorate per le richieste WCF se un servizio si trova in un spazio URL protetto da ASP. Regole di autorizzazione URL della rete.  
  
    -   Estensibilità di HttpModule: infrastruttura di hosting di WCF intercetta WCF richieste quando la <xref:System.Web.HttpApplication.PostAuthenticateRequest> evento viene generato e non restituisce elaborazione alla pipeline HTTP ASP.NET. I moduli codificati per intercettare le richieste in fasi successive della pipeline non intercettano richieste WCF.  
  
    -   Rappresentazione ASP.NET: per impostazione predefinita, WCF richiede sempre viene eseguito come identità, del processo IIS anche se ASP.NET è impostato per consentire la rappresentazione mediante System. Web \<identity impersonate = "true" / > opzione di configurazione.  
  
 Queste restrizioni si applicano solo ai servizi WCF ospitati nell'applicazione IIS. Il comportamento del contenuto ASP.NET non è interessato dalla presenza di WCF.  
  
 Le applicazioni WCF che richiedono funzionalità tradizionalmente fornite dalla pipeline HTTP dovrebbero utilizzando gli equivalenti WCF, che sono host indipendenti e dal trasporto:  
  
-   <xref:System.ServiceModel.OperationContext> anziché <xref:System.Web.HttpContext>.  
  
-   <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> invece dell'autorizzazione file/URL ASP.NET.  
  
-   <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> o canali su più livelli personalizzati invece di moduli HTTP.  
  
-   Rappresentazione per ogni operazione utilizzando WCF anziché la rappresentazione di System. Web.  
  
 In alternativa, è possibile considerare i servizi in esecuzione in modalità di compatibilità ASP.NET di WCF.  
  
## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Hosting dei servizi WCF in modalità di compatibilità ASP.NET  
 Sebbene il modello di WCF è progettato per comportarsi coerentemente in diversi ambienti host e trasporti, sono spesso scenari in cui un'applicazione non richiede tale grado di flessibilità. Modalità di compatibilità ASP.NET di WCF è adatta agli scenari che non richiedono la possibilità di host all'esterno di IIS o di comunicazione su protocolli diversi da HTTP, ma che vengono usate tutte le funzionalità della piattaforma dell'applicazione Web ASP.NET.  
  
 A differenza della configurazione side-by-side di impostazione predefinita, in cui l'infrastruttura di hosting di WCF consente di intercettare i messaggi WCF e li instrada fuori dalla pipeline HTTP, servizi WCF in esecuzione in modalità di compatibilità ASP.NET partecipano completamente al ciclo di vita di richiesta HTTP ASP.NET. In modalità di compatibilità, servizi WCF utilizzano la pipeline HTTP tramite un <xref:System.Web.IHttpHandler> implementazione, simili alle richieste di modalità per le pagine ASPX e servizi Web ASMX vengono gestiti. Di conseguenza, WCF si comporta in modo identico ad ASMX in relazione alla funzionalità ASP.NET seguenti:  
  
-   <xref:System.Web.HttpContext>: Servizi WCF in esecuzione in modalità di compatibilità ASP.NET possono accedere <xref:System.Web.HttpContext.Current%2A> e il relativo stato associato.  
  
-   Autorizzazione basata su file: i servizi WCF in esecuzione in modalità di compatibilità ASP.NET possono essere protetti mediante l'aggiunta di elenchi di controllo file system accesso (ACL) al file con estensione svc del servizio.  
  
-   Autorizzazione URL configurabile: ASP. Regole di autorizzazione URL della rete vengono applicate per le richieste WCF quando il servizio WCF è in esecuzione in modalità di compatibilità ASP.NET.  
  
-   <xref:System.Web.HttpModuleCollection> estendibilità: servizi WCF perché in esecuzione in modalità di compatibilità ASP.NET partecipano completamente al ciclo di vita di richiesta HTTP ASP.NET, qualsiasi modulo HTTP configurato nella pipeline HTTP è in grado di operare su richieste WCF prima e dopo la chiamata del servizio.  
  
-   Rappresentazione ASP.NET: I servizi WCF eseguiti utilizzando l'identità corrente di ASP.NET rappresentata thread, che potrebbero essere diversi dall'identità del processo IIS se la rappresentazione ASP.NET è stata abilitata per l'applicazione. Se la rappresentazione ASP.NET e la rappresentazione di WCF sono entrambe abilitate per una particolare operazione del servizio, l'implementazione del servizio verrà eseguita usando l'identità ottenuta da WCF.  
  
 Modalità di compatibilità ASP.NET di WCF è abilitata a livello di applicazione tramite la configurazione seguente (che si trova nel file Web. config dell'applicazione):  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />  
</system.serviceModel>  
```  
  
 Il valore predefinito "`true`" Se non specificato. Impostando questo valore su "`false`" indica che tutti i servizi WCF in esecuzione nell'applicazione non verranno eseguita in modalità di compatibilità ASP.NET.  
  
 Dato che la modalità di compatibilità ASP.NET implica una semantica di elaborazione richiesta che sono fondamentalmente diversa da quello predefinito WCF, singole implementazione del servizio hanno la possibilità di controllare se vengono eseguite all'interno di un'applicazione per ASP.NET Modalità di compatibilità è stata abilitata. I servizi possono usare <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> per indicare se supportano la modalità di compatibilità ASP.NET. Il valore predefinito di questo attributo è <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.  
  
 `[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]`  
  
 `public class CalculatorService : ICalculatorSession`  
  
 `{//Implement calculator service methods.}`  
  
 Nella tabella seguente viene illustrato in che modo l'impostazione della modalità di compatibilità a livello di applicazione interagisce con il livello di supporto dichiarato del singolo servizio:  
  
|Impostazione della modalità di compatibilità a livello di applicazione|[AspNetCompatibilityRequirementsMode]<br /><br /> Impostazione|Risultato osservato|  
|--------------------------------------------------|---------------------------------------------------------|---------------------|  
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Servizio correttamente attivato.|  
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Servizio correttamente attivato.|  
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Errore di attivazione durante la ricezione di un messaggio da parte del servizio.|  
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Errore di attivazione durante la ricezione di un messaggio da parte del servizio.|  
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Servizio correttamente attivato.|  
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Servizio correttamente attivato.|  
  
> [!NOTE]
>  IIS 7.0 e WAS consente ai servizi WCF comunicare su protocolli diversi da HTTP. Tuttavia, servizi WCF in esecuzione nelle applicazioni che è sono attivata la modalità di compatibilità ASP.NET non sono consentiti per esporre endpoint non HTTP. Tale configurazione genera un'eccezione di attivazione quando il servizio riceve il primo messaggio.  
  
 Per ulteriori informazioni sull'abilitazione della modalità di compatibilità ASP.NET per i servizi WCF, vedere <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> e il [compatibilità ASP.NET](../../../../docs/framework/wcf/samples/aspnet-compatibility.md) esempio.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>  
 [Windows Server AppFabric con funzionalità di Hosting](http://go.microsoft.com/fwlink/?LinkId=201276)

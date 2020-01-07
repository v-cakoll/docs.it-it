---
title: Servizi WCF e ASP.NET
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: 0a64e277d3465b77a2553d6b9c3901f09a6e1a52
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544743"
---
# <a name="wcf-services-and-aspnet"></a>Servizi WCF e ASP.NET

In questo argomento viene illustrato l'hosting di servizi di Windows Communication Foundation (WCF) affiancati con ASP.NET e l'hosting in modalità di compatibilità ASP.NET.

## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Hosting di WCF side-by-side con ASP.NET

I servizi WCF ospitati in Internet Information Services (IIS) possono essere individuati con. Pagine ASPX e servizi Web ASMX all'interno di un singolo dominio applicazione comune. ASP.NET fornisce servizi di infrastruttura comuni, ad esempio la gestione di AppDomain e la compilazione dinamica per WCF e il runtime HTTP di ASP.NET. La configurazione predefinita per WCF è affiancata a ASP.NET.

![Screenshot che mostra i servizi WCF e ASP .NET: condivisione dello stato.](./media/wcf-services-and-aspnet/windows-communication-foundation-services-asp-dotnet-configuration.gif)

Il runtime HTTP di ASP.NET gestisce le richieste ASP.NET ma non partecipa all'elaborazione delle richieste destinate ai servizi WCF, anche se questi servizi sono ospitati nello stesso AppDomain del contenuto di ASP.NET. Al contrario, il modello del servizio WCF intercetta i messaggi indirizzati ai servizi WCF e li instrada tramite lo stack del canale/trasporto WCF.

I risultati del modello affiancato sono i seguenti:

- I servizi ASP.NET e WCF possono condividere lo stato AppDomain. Poiché i due Framework possono coesistere nello stesso AppDomain, WCF può condividere anche lo stato AppDomain con ASP.NET (incluse variabili statiche, eventi e così via).

- I servizi WCF si comportano in modo coerente indipendentemente dall'ambiente host e dal trasporto. Il runtime HTTP ASP.NET è intenzionalmente accoppiato all'ambiente host IIS/ASP.NET e alla comunicazione HTTP. Al contrario, WCF è progettato per comportarsi in modo coerente negli ambienti host (WCF si comporta in modo coerente all'interno e all'esterno di IIS) e tra i trasporti (un servizio ospitato in IIS 7,0 e versioni successive presenta un comportamento coerente in tutti gli endpoint che espone, anche se alcuni di questi endpoint usano protocolli diversi da HTTP.

- All'interno di un AppDomain, le funzionalità implementate dal runtime HTTP si applicano al contenuto ASP.NET ma non a WCF. Molte funzionalità specifiche di HTTP della piattaforma applicativa ASP.NET non si applicano ai servizi WCF ospitati all'interno di un AppDomain che contiene contenuto ASP.NET. Ne sono esempi le seguenti:

  - HttpContext: <xref:System.Web.HttpContext.Current%2A> è sempre `null` quando si accede dall'interno di un servizio WCF. In alternativa, usare <xref:System.ServiceModel.Channels.RequestContext> .

  - Autorizzazione basata su file: il modello di sicurezza WCF non consente l'elenco di controllo di accesso (ACL) applicato al file con estensione svc del servizio per decidere se una richiesta di servizio è autorizzata.

  - Autorizzazione URL basata sulla configurazione: Analogamente, il modello di sicurezza WCF non rispetta alcuna regola di autorizzazione basata su URL specificata nell'elemento di configurazione \<autorizzazione > di System. Web. Queste impostazioni vengono ignorate per le richieste WCF se un servizio risiede in uno spazio URL protetto da ASP. Regole di autorizzazione dell'URL di NET.

  - Estensibilità HttpModule: l'infrastruttura di hosting WCF intercetta le richieste WCF quando viene generato l'evento <xref:System.Web.HttpApplication.PostAuthenticateRequest> e non restituisce l'elaborazione alla pipeline HTTP ASP.NET. I moduli codificati per intercettare le richieste nelle fasi successive della pipeline non intercettano le richieste WCF.

  - Rappresentazione ASP.NET: per impostazione predefinita, le richieste WCF vengono sempre eseguite come identità del processo IIS, anche se ASP.NET è impostato in modo da consentire la rappresentazione mediante l'opzione di configurazione \<Identity impersonate = "true"/> di System. Web.

Queste restrizioni si applicano solo ai servizi WCF ospitati nell'applicazione IIS. Il comportamento del contenuto di ASP.NET non è influenzato dalla presenza di WCF.

Le applicazioni WCF che richiedono funzionalità tradizionalmente fornite dalla pipeline HTTP devono considerare l'utilizzo degli equivalenti WCF, che sono indipendenti dall'host e dal trasporto:

- <xref:System.ServiceModel.OperationContext> anziché <xref:System.Web.HttpContext>.

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> invece dell'autorizzazione file/URL ASP.NET.

- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> o canali su più livelli personalizzati invece di moduli HTTP.

- Rappresentazione per ogni operazione mediante WCF anziché la rappresentazione System. Web.

In alternativa, è possibile provare a eseguire i servizi in modalità di compatibilità ASP.NET di WCF.

## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Hosting di servizi WCF in modalità di compatibilità ASP.NET

Sebbene il modello WCF sia progettato per comportarsi in modo coerente negli ambienti di hosting e nei trasporti, spesso esistono scenari in cui un'applicazione non richiede questo livello di flessibilità. La modalità di compatibilità ASP.NET di WCF è adatta per gli scenari che non richiedono la possibilità di ospitare all'esterno di IIS o per la comunicazione tramite protocolli diversi da HTTP, ma che utilizzano tutte le funzionalità della piattaforma dell'applicazione Web ASP.NET.

A differenza della configurazione affiancata predefinita, in cui l'infrastruttura di hosting WCF intercetta i messaggi WCF e li instrada dalla pipeline HTTP, i servizi WCF in esecuzione in modalità di compatibilità ASP.NET partecipano completamente al ciclo di vita della richiesta HTTP ASP.NET. In modalità di compatibilità, i servizi WCF utilizzano la pipeline HTTP tramite un'implementazione di <xref:System.Web.IHttpHandler>, in modo analogo al modo in cui vengono gestite le richieste per le pagine ASPX e i servizi Web ASMX. Di conseguenza, WCF si comporta in modo identico a ASMX rispetto alle funzionalità ASP.NET seguenti:

- <xref:System.Web.HttpContext>: i servizi WCF in esecuzione in modalità di compatibilità ASP.NET possono accedere <xref:System.Web.HttpContext.Current%2A> e lo stato associato.

- Autorizzazione basata su file: i servizi WCF in esecuzione in modalità di compatibilità ASP.NET possono essere protetti connettendo file system elenchi di controllo di accesso (ACL) al file con estensione svc del servizio.

- Autorizzazione URL configurabile: ASP. Le regole di autorizzazione dell'URL di NET vengono applicate alle richieste WCF quando il servizio WCF viene eseguito in modalità di compatibilità ASP.NET.

- estensibilità <xref:System.Web.HttpModuleCollection>: poiché i servizi WCF in esecuzione in modalità di compatibilità ASP.NET partecipano completamente al ciclo di vita della richiesta HTTP ASP.NET, qualsiasi modulo HTTP configurato nella pipeline HTTP può operare sulle richieste WCF sia prima che dopo la chiamata al servizio.

- Rappresentazione ASP.NET: i servizi WCF vengono eseguiti utilizzando l'identità corrente del thread ASP.NET rappresentato, che può essere diverso dall'identità del processo IIS se è stata abilitata la rappresentazione ASP.NET per l'applicazione. Se la rappresentazione ASP.NET e la rappresentazione WCF sono entrambe abilitate per una particolare operazione del servizio, l'implementazione del servizio viene eseguita in ultima analisi utilizzando l'identità ottenuta da WCF.

La modalità di compatibilità ASP.NET di WCF è abilitata a livello di applicazione tramite la configurazione seguente (che si trova nel file Web. config dell'applicazione):

```xml
<system.serviceModel>
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```

Per impostazione predefinita, questo valore viene impostato su `false` se non è specificato. Il valore di `false` indica che tutti i servizi WCF in esecuzione nell'applicazione non vengono eseguiti in modalità di compatibilità ASP.NET.

Poiché la modalità di compatibilità ASP.NET implica la semantica di elaborazione delle richieste sostanzialmente diversa da quella predefinita di WCF, le singole implementazioni del servizio possono controllare se vengono eseguite all'interno di un'applicazione per la quale ASP.NET La modalità di compatibilità è stata abilitata. I servizi possono usare <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> per indicare se supportano la modalità di compatibilità ASP.NET. Il valore predefinito di questo attributo è <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.

```csharp
[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
public class CalculatorService : ICalculatorSession
{//Implement calculator service methods.}
```

Nella tabella seguente viene illustrato in che modo l'impostazione della modalità di compatibilità a livello di applicazione interagisce con il livello di supporto dichiarato del singolo servizio:

|Impostazione della modalità di compatibilità a livello di applicazione|[AspNetCompatibilityRequirementsMode]<br /><br /> Impostazione di|Risultato osservato|
|--------------------------------------------------|---------------------------------------------------------|---------------------|
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Servizio correttamente attivato.|
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Servizio correttamente attivato.|
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Errore di attivazione durante la ricezione di un messaggio da parte del servizio.|
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Errore di attivazione durante la ricezione di un messaggio da parte del servizio.|
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Servizio correttamente attivato.|
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Servizio correttamente attivato.|

> [!NOTE]
> IIS 7,0 e WAS consente ai servizi WCF di comunicare su protocolli diversi da HTTP. Tuttavia, i servizi WCF in esecuzione nelle applicazioni in cui è abilitata la modalità di compatibilità ASP.NET non possono esporre endpoint non HTTP. Tale configurazione genera un'eccezione di attivazione quando il servizio riceve il primo messaggio.

Per ulteriori informazioni sull'abilitazione della modalità di compatibilità ASP.NET per i servizi WCF, vedere <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> e l'esempio di [compatibilità ASP.NET](../samples/aspnet-compatibility.md) .

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))

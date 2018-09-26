---
title: Protezione di WCF Data Services
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- securing application [WCF Data Services]
- WCF Data Services, security
ms.assetid: 99fc2baa-a040-4549-bc4d-f683d60298af
ms.openlocfilehash: 56ece9c2c81f05047e85ab681e7cfe0da65f35b9
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47204099"
---
# <a name="securing-wcf-data-services"></a>Protezione di WCF Data Services
In questo argomento vengono illustrate alcune considerazioni sulla sicurezza che riguardano in modo particolare lo sviluppo, la distribuzione e l'esecuzione di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] e di applicazioni che accedono ai servizi che supportano [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]. È consigliabile inoltre seguire le raccomandazioni relative alla creazione di applicazioni [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] protette.  
  
 Quando si pianifica come proteggere un servizio [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] basato su [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], è necessario considerare l'autenticazione (il processo che consente di individuare e verificare l'identità di un'entità) e l'autorizzazione (il processo che consente di determinare se un'entità autenticata dispone dell'accesso alle risorse richieste). È necessario considerare anche se crittografare il messaggio tramite SSL.  
  
## <a name="authenticating-client-requests"></a>Autenticazione di richieste del client  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] non implementa alcun tipo di autenticazione propria, piuttosto si basa sul provisioning di autenticazione dell'host del servizio dati. Ciò vuole dire che il servizio presuppone che qualsiasi richiesta che riceve sia già stata autenticata dall'host di rete e che l'host abbia identificato correttamente il principio della richiesta tramite le interfacce fornite da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Le opzioni di autenticazione e gli approcci sono illustrati nella [serie di autenticazione e OData](https://go.microsoft.com/fwlink/?LinkId=200381).  
  
### <a name="authentication-options-for-a-wcf-data-service"></a>Opzioni di autenticazione per un servizio dati WCF  
 Nella tabella seguente vengono elencati alcuni dei meccanismi di autenticazione che sono disponibili per facilitare l'autenticazione delle richieste a un servizio dati WCF.  
  
|Opzioni di autenticazione|Descrizione|  
|----------------------------|-----------------|  
|Autenticazione anonima|Quando l'autenticazione anonima HTTP è abilitata, qualsiasi principio è in grado di connettersi al servizio dati. Le credenziali non sono richieste per l'accesso anonimo. Usare questa opzione solo quando si desidera consentire a chiunque l'accesso al servizio dati.|  
|Autenticazione di base e digest|Le credenziali composte da un nome utente e da una password sono richieste per l'autenticazione. Supporta l'autenticazione di client non Windows. **Nota sulla sicurezza:** le credenziali di autenticazione di base (nome utente e password) vengono inviate in chiaro e può essere intercettate. L'autenticazione digest invia un hash basato sulle credenziali fornite che la rende più sicura dell'autenticazione di base. Entrambe le autenticazioni sono vulnerabili agli attacchi man-in-the-middle. Quando si usano questi metodi di autenticazione, è necessario considerare di crittografare le comunicazione fra il client e il servizio dati tramite Secure Sockets Layer (SSL). <br /><br /> Microsoft Internet Information Services (IIS) fornisce un'implementazione dell'autenticazione digest e di base per le richieste HTTP in un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Questa implementazione del provider di Autenticazione di Windows consente a un'applicazione client .NET Framework di fornire le credenziali nell'intestazione HTTP della richiesta al servizio dati per negoziare con facilità l'autenticazione di un utente Windows. Per altre informazioni, vedere [riferimenti tecnici per l'autenticazione Digest](https://go.microsoft.com/fwlink/?LinkId=200408).<br /><br /> Quando si desidera che il servizio dati usi l'autenticazione di base secondo un servizio di autenticazione personalizzato e non con le credenziali di Windows, è necessario implementare un modulo HTTP [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] personalizzato per l'autenticazione.<br /><br /> Per un esempio di come usare uno schema di autenticazione di base personalizzato con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vedere il post sul [autenticazione di base personalizzata](https://go.microsoft.com/fwlink/?LinkID=200388) nel [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] e serie di autenticazione.|  
|Autenticazione di Windows|Le credenziali basate su Windows vengono scambiate tramite NTLM o Kerberos. Questo meccanismo è più sicuro rispetto all'autenticazione di base o digest, ma richiede che il client sia un'applicazione basata su Windows. IIS fornisce anche un'implementazione dell'autenticazione di Windows per le richieste HTTP in un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Per altre informazioni, vedere [panoramica dell'autenticazione form ASP.NET](https://msdn.microsoft.com/library/099c1587-6934-476e-ac95-28f534bc9708).<br /><br /> Per un esempio di come usare l'autenticazione di Windows con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vedere il post sul [l'autenticazione di Windows](https://go.microsoft.com/fwlink/?LinkID=200384) nel [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] e serie di autenticazione.|  
|Autenticazione basata su form [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]|L'autenticazione basata su form consente di autenticare gli utenti mediante un codice personalizzato e di gestire un token di autenticazione in un cookie o nell'URL di pagina. Viene eseguita l'autenticazione del nome utente e della password degli utenti usando un form di accesso creato dall'utente. Le richieste non autenticate vengono reindirizzate a una pagina di accesso, dove l'utente fornisce le credenziali e invia il form. Se l'applicazione autentica la richiesta, il sistema elabora un ticket contenente una chiave per la ridefinizione dell'identità per le richieste successive. Per altre informazioni, vedere [Provider di autenticazione form](https://msdn.microsoft.com/library/77e21ba2-bad1-4967-a8ec-74942dea7e47). **Nota sulla sicurezza:** per impostazione predefinita, il cookie contenente il ticket di autenticazione form non è protetto quando si usa l'autenticazione basata su form in un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] applicazione Web. È opportuno richiedere SSL per proteggere il ticket di autenticazione e le credenziali di accesso iniziale. <br /><br /> Per un esempio di come usare l'autenticazione con di form [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vedere il post sul [autenticazione basata su form](https://go.microsoft.com/fwlink/?LinkID=200389) nel [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] e serie di autenticazione.|  
|Autenticazione basata sulle attestazioni|L'autenticazione basata su attestazioni, il servizio dati si basa su un servizio del provider di identità di "terze parti" attendibile per autenticare l'utente. Il provider di identità autentica positivamente l'utente che sta richiedendo l'accesso alle risorse del servizio dati e rilascia un token che concede l'accesso alle risorse richieste. Questo token viene quindi presentato al servizio dati che concede l'accesso all'utente in base alla relazione di trust con il servizio di identità che ha rilasciato il token di accesso.<br /><br /> Il provider di autenticazione basato sulle attestazioni risulta conveniente perché può essere usato per autenticare vari tipi di client tra i vari domini trust. Usando un provider di terze parti di questo tipo, il servizio dati può scaricare i requisiti di gestione e autenticazione degli utenti. OAuth 2.0 è un protocollo di autenticazione basato sulle attestazioni supportato dal Controllo di accesso AppFabric di Microsoft Azure per l'autorizzazione federata come servizio. Questo protocollo supporta i servizi basati sul REST. Per un esempio di come usare OAuth 2.0 con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vedere il post sul [OData e OAuth](https://go.microsoft.com/fwlink/?LinkId=200514) nel [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] e serie di autenticazione.|  
  
<a name="clientAuthentication"></a>   
### <a name="authentication-in-the-client-library"></a>Autenticazione nella libreria client  
 Per impostazione predefinita, la libreria client [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] non fornisce le credenziali quando viene eseguita una richiesta a un servizio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Quando le credenziali di accesso sono richieste dal servizio dati per autenticare un utente, è possibile fornire queste credenziali in un elemento <xref:System.Net.NetworkCredential> a cui accede la proprietà <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> di <xref:System.Data.Services.Client.DataServiceContext>, come nell'esempio seguente:  
  
```csharp  
// Set the client authentication credentials.  
context.Credentials =  
    new NetworkCredential(userName, password, domain);  
```  
  
```vb  
' Set the client authentication credentials.  
context.Credentials = _  
    New NetworkCredential(userName, password, domain)  
```  
  
 Per altre informazioni, vedere [procedura: specificare le credenziali Client per una richiesta di servizio dati](../../../../docs/framework/data/wcf/specify-client-creds-for-a-data-service-request-wcf.md).  
  
 Quando il servizio dati richiede credenziali di accesso che non possono essere specificate tramite un oggetto <xref:System.Net.NetworkCredential>, ad esempio un cookie o un token basato sulle attestazioni, è necessario impostare manualmente le intestazioni nella richiesta HTTP, generalmente le intestazioni `Authorization` e `Cookie`. Per altre informazioni su questo tipo di scenario di autenticazione, vedere il post [OData e autenticazione: hook lato Client](https://go.microsoft.com/fwlink/?LinkID=200385). Per un esempio di come impostare le intestazioni HTTP in un messaggio di richiesta, vedere [procedura: impostare le intestazioni nella richiesta del Client](../../../../docs/framework/data/wcf/how-to-set-headers-in-the-client-request-wcf-data-services.md).  
  
## <a name="impersonation"></a>Rappresentazione  
 Generalmente il servizio dati accede alle risorse richieste, ad esempio i file sul server o un database, tramite le credenziali del processo di lavoro che ospita il servizio dati. Quando si usa la rappresentazione, è possibile eseguire le applicazioni [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] con l'identità Windows (account utente) dell'utente che effettua la richiesta. La rappresentazione è di utilizzo comune in applicazioni che si basano su IIS per autenticare l'utente e le credenziali di questo principio sono usate per accedere alle risorse richieste. Per altre informazioni, vedere [rappresentazione ASP.NET](https://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d).  
  
## <a name="configuring-data-service-authorization"></a>Configurazione dell'autorizzazione del servizio dati  
 L'autorizzazione è il conferimento dell'accesso alle risorse dell'applicazione concesso a un principio o un processo identificato in base a un'autenticazione precedentemente riuscita. Come regola generale, è opportuno concedere agli utenti del servizio dati solo i diritti sufficienti per eseguire le operazioni richieste dalle applicazioni client.  
  
### <a name="restrict-access-to-data-service-resources"></a>Restrizione dell'accesso alle risorse del servizio dati  
 Per impostazione predefinita, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] concede l'accesso in lettura e scrittura comune alle risorse del servizio dati (set di entità e operazioni del servizio) a qualsiasi utente in grado di accedere al servizio dati. Le regole che definiscono l'accesso in lettura e scrittura possono essere specificate separatamente per ogni set di entità esposto dal servizio dati così come per qualsiasi operazione del servizio. Si consiglia di limitare l'accesso in lettura e scrittura solo alle risorse richieste dall'applicazione client. Per altre informazioni, vedere [requisiti di accesso alle risorse minime](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md#accessRequirements).  
  
### <a name="implement-role-based-interceptors"></a>Intercettori basati sulla regola di implementazione  
 Gli intercettori consentono di intercettare le richieste delle risorse del servizio dati prima che vengano elaborate dal servizio dati. Per altre informazioni, vedere [intercettori](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md). Gli intercettori consentono di concedere l'autorizzazione in base all'utente autenticato che effettua la richiesta. Per un esempio di come limitare l'accesso alle risorse del servizio dati basate su un'identità utente autenticata, vedere [procedura: intercettare messaggi del servizio dati](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
### <a name="restrict-access-to-the-persisted-data-store-and-local-resources"></a>Restrizione dell'accesso all'archivio dati persistente e alle risorse locali  
 È opportuno concedere agli account usati per accedere all'archivio persistente solo i diritti in un database o nel file system sufficienti a supportare i requisiti del servizio dati. Quando viene usata l'autenticazione anonima, questo è l'account usato per eseguire l'applicazione hosting. Per altre informazioni, vedere [Procedura: sviluppare un servizio WCF in esecuzione in IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md). Quando viene usata la rappresentazione, agli utenti autenticati deve essere concesso l'accesso alle risorse, generalmente come parte di un gruppo di Windows.  
  
## <a name="other-security-considerations"></a>Altre considerazioni sulla sicurezza  
  
### <a name="secure-the-data-in-the-payload"></a>Protezione dei dati nel payload  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] si basa sul protocollo HTTP. In un messaggio HTTP, è possibile che l'intestazione contenga credenziali dell'utente rilevanti, a seconda dell'autenticazione implementata dal servizio dati. È possibile che anche il corpo del messaggio contenga dati del cliente rilevanti che devono essere protetti. In entrambi i casi, si consiglia di usare SSL per proteggere queste informazioni in rete.  
  
### <a name="ignored-message-headers-and-cookies"></a>Intestazioni dei messaggi e cookie ignorati  
 Le intestazioni delle richieste HTTP, diverse da quelle che dichiarano i tipi di contenuto e i percorsi delle risorse, vengono ignorate e non vengono mai impostate dal servizio dati.  
  
 I cookie possono essere usati come parte di uno schema di autenticazione, ad esempio con Autenticazione basata su form [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Tuttavia, qualsiasi cookie HTTP impostato su una richiesta in entrata viene ignorato da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. È possibile che l'host di un servizio dati elabori il cookie, ma il runtime di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] non analizza mai né restituisce cookie. Anche la libreria client [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] non elabora i cookie inviati nella risposta.  
  
### <a name="custom-hosting-requirements"></a>Requisiti dell'hosting personalizzato  
 Per impostazione predefinita, i servizi [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] vengono creati come un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ospitata in IIS. In tal modo il servizio dati potrà usare i comportamenti sicuri della piattaforma. È possibile definire i servizi [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ospitati da un host personalizzato. Per altre informazioni, vedere [che ospita il servizio dati](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md). I componenti e la piattaforma che ospitano un servizio dati devono assicurare i seguenti comportamenti di sicurezza per impedire attacchi sul servizio dati:  
  
-   Limitare la lunghezza dell'URI accettata in una richiesta del servizio dati per tutte le possibili operazioni.  
  
-   Limitare la dimensione dei messaggi HTTP in ingresso e in uscita.  
  
-   Limitare il numero totale di richieste in sospeso in qualsiasi momento.  
  
-   Limitare la dimensione delle intestazioni HTTP e relativi valori e fornire l'accesso [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ai dati dell'intestazione.  
  
-   Rilevare e contrastare gli attacchi noti, ad esempio attacchi di tipo riproduzione di messaggi e SYN TCP.  
  
### <a name="values-are-not-further-encoded"></a>Valori non ulteriormente codificati  
 I valori delle proprietà inviati al servizio dati non sono ulteriormente codificati dal runtime di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Ad esempio, quando una proprietà di stringa di un'entità contiene contenuto HTML formattato, i tag non vengono codificati nel formato HTML dal servizio dati. Il servizio dati non codifica ulteriormente neanche i valori di proprietà nella risposta. La libreria client inoltre non esegue nessuna codifica aggiuntiva.  
  
### <a name="considerations-for-client-applications"></a>Considerazioni per le applicazioni client  
 Le seguenti considerazioni sulla sicurezza si applicano a tutte le applicazioni che usano il client [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] per accedere ai servizi [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
-   La libreria client presuppone che i protocolli usati per accedere al servizio dati forniscano un livello di sicurezza appropriato.  
  
-   La libreria client usa tutti i valori predefiniti per i timeout e le opzioni di analisi degli stack di trasporto forniti dalla piattaforma sottostante.  
  
-   La libreria client non legge le impostazioni dai file di configurazione dell'applicazione.  
  
-   La libreria client non implementa alcun meccanismo di accesso tra domini. Al contrario, usa i meccanismi forniti dallo stack HTTP sottostante.  
  
-   La libreria client non dispone di elementi dell'interfaccia utente e non visualizza i dati né esegue il rendering dei dati che riceve o invia.  
  
-   È opportuno che le applicazioni client convalidino sempre l'input dell'utente e i dati accettati da servizi non attendibili.  
  
## <a name="see-also"></a>Vedere anche  
 [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

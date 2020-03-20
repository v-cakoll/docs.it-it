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
ms.openlocfilehash: e09007e786772e838a9aaa76eb8ef7a3fe2b7cca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174654"
---
# <a name="securing-wcf-data-services"></a>Protezione di WCF Data Services
In questo argomento vengono descritte le considerazioni sulla sicurezza specifiche per lo sviluppo, la distribuzione e l'esecuzione di WCF Data ServicesWCF Data Services e delle applicazioni che accedono ai servizi che supportano il protocollo OData (Open Data Protocol). È inoltre consigliabile seguire i suggerimenti per la creazione di applicazioni .NET Framework protette.  
  
Quando si pianifica come proteggere un servizio OData basato su WCF Data Services, è necessario affrontare sia l'autenticazione, il processo di individuazione e verifica dell'identità di un'entità e l'autorizzazione, il processo di determinazione se un'entità autenticata è accedere alle risorse richieste. È necessario considerare anche se crittografare il messaggio tramite SSL.  
  
## <a name="authenticating-client-requests"></a>Autenticazione di richieste del client  
WCF Data ServicesWCF Data Services non implementa alcun tipo di autenticazione propria, ma si basa sulle disposizioni di autenticazione dell'host del servizio dati. Ciò significa che il servizio presuppone che qualsiasi richiesta che riceve sia già stata autenticata dall'host di rete e che l'host abbia identificato correttamente il principio per la richiesta in modo appropriato tramite le interfacce fornite da WCF Data ServicesWCF Data Services. Queste opzioni e approcci di autenticazione sono descritti in dettaglio nella [serie OData e Authentication](https://devblogs.microsoft.com/odata/?s=%22OData+and+authentication%22)in più parti.  
  
### <a name="authentication-options-for-a-wcf-data-service"></a>Opzioni di autenticazione per un servizio dati WCF  
 Nella tabella seguente vengono elencati alcuni dei meccanismi di autenticazione che sono disponibili per facilitare l'autenticazione delle richieste a un servizio dati WCF.  
  
|Opzioni di autenticazione|Descrizione|  
|----------------------------|-----------------|  
|Autenticazione anonima|Quando l'autenticazione anonima HTTP è abilitata, qualsiasi principio è in grado di connettersi al servizio dati. Le credenziali non sono richieste per l'accesso anonimo. Usare questa opzione solo quando si desidera consentire a chiunque l'accesso al servizio dati.|  
|Autenticazione di base e digest|Le credenziali composte da un nome utente e da una password sono richieste per l'autenticazione. Supporta l'autenticazione di client non Windows. **Nota sulla sicurezza:**  Le credenziali di autenticazione di base (nome utente e password) vengono inviate in modalità non crittografata e possono essere intercettate. L'autenticazione digest invia un hash basato sulle credenziali fornite che la rende più sicura dell'autenticazione di base. Entrambe le autenticazioni sono vulnerabili agli attacchi man-in-the-middle. Quando si usano questi metodi di autenticazione, è necessario considerare di crittografare le comunicazione fra il client e il servizio dati tramite Secure Sockets Layer (SSL). <br /><br /> Microsoft Internet Information Services (IIS) fornisce un'implementazione dell'autenticazione di base e digest per le richieste HTTP in un'applicazione ASP.NET. Questa implementazione del provider di Autenticazione di Windows consente a un'applicazione client .NET Framework di fornire le credenziali nell'intestazione HTTP della richiesta al servizio dati per negoziare con facilità l'autenticazione di un utente Windows. Per ulteriori informazioni, vedere [Riferimento tecnico all'autenticazione del digest](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782794(v=ws.10)).<br /><br /> Quando si desidera che il servizio dati utilizzi l'autenticazione di base basata su un servizio di autenticazione personalizzato e non sulle credenziali di Windows, è necessario implementare un modulo HTTP ADP.NET personalizzato per l'autenticazione.<br /><br /> Per un esempio di come utilizzare uno schema di autenticazione di base personalizzato con WCF Data ServicesWCF Data Services, vedere il post di blog [OData and Authentication – Part 6 – Custom Basic Authentication](https://devblogs.microsoft.com/odata/odata-and-authentication-part-6-custom-basic-authentication/).|  
|Autenticazione di Windows|Le credenziali basate su Windows vengono scambiate tramite NTLM o Kerberos. Questo meccanismo è più sicuro rispetto all'autenticazione di base o digest, ma richiede che il client sia un'applicazione basata su Windows. IIS fornisce inoltre un'implementazione dell'autenticazione di Windows per le richieste HTTP in un'applicazione ASP.NET. Per ulteriori informazioni, vedere [Cenni ASP.NET panoramici dell'autenticazione basata su form](https://docs.microsoft.com/previous-versions/aspnet/7t6b43z4(v=vs.100)).<br /><br /> Per un esempio di come utilizzare l'autenticazione di Windows con WCF Data ServicesWCF Data Services, vedere il post di blog [OData and Authentication – Part 2 – Windows Authentication](https://devblogs.microsoft.com/odata/odata-and-authentication-part-2-windows-authentication/).|  
|ASP.NET l'autenticazione basata su form|L'autenticazione basata su form consente di autenticare gli utenti mediante un codice personalizzato e di gestire un token di autenticazione in un cookie o nell'URL di pagina. Viene eseguita l'autenticazione del nome utente e della password degli utenti usando un form di accesso creato dall'utente. Le richieste non autenticate vengono reindirizzate a una pagina di accesso, dove l'utente fornisce le credenziali e invia il form. Se l'applicazione autentica la richiesta, il sistema elabora un ticket contenente una chiave per la ridefinizione dell'identità per le richieste successive. Per ulteriori informazioni, vedere [Provider di autenticazione basata su form](https://docs.microsoft.com/previous-versions/aspnet/9wff0kyh(v=vs.100)). **Nota sulla sicurezza:**  Per impostazione predefinita, il cookie che contiene il ticket di autenticazione basata su form non è protetto quando si utilizza l'autenticazione basata su form in un'applicazione Web ASP.NET. È opportuno richiedere SSL per proteggere il ticket di autenticazione e le credenziali di accesso iniziale. <br /><br /> Per un esempio di come utilizzare l'autenticazione basata su form con WCF Data ServicesWCF Data Services, vedere il post di blog [OData and Authentication – Part 7 – Forms Authentication](https://devblogs.microsoft.com/odata/odata-and-authentication-part-7-forms-authentication/).|  
|Autenticazione basata sulle attestazioni|Nell'autenticazione basata sulle attestazioni, il servizio dati si basa su un servizio provider di identità di terze parti attendibile per autenticare l'utente. Il provider di identità autentica positivamente l'utente che sta richiedendo l'accesso alle risorse del servizio dati e rilascia un token che concede l'accesso alle risorse richieste. Questo token viene quindi presentato al servizio dati che concede l'accesso all'utente in base alla relazione di trust con il servizio di identità che ha rilasciato il token di accesso.<br /><br /> Il provider di autenticazione basato sulle attestazioni risulta conveniente perché può essere usato per autenticare vari tipi di client tra i vari domini trust. Usando un provider di terze parti di questo tipo, il servizio dati può scaricare i requisiti di gestione e autenticazione degli utenti. OAuth 2.0 è un protocollo di autenticazione basato sulle attestazioni supportato dal Controllo di accesso AppFabric di Microsoft Azure per l'autorizzazione federata come servizio. Questo protocollo supporta i servizi basati sul REST. Per un esempio di come utilizzare OAuth 2.0 con WCF Data Services, vedere il post di blog [OData and Authentication – Parte 8 – OAuth WRAP](https://devblogs.microsoft.com/odata/odata-and-authentication-part-8-oauth-wrap/).|  
  
<a name="clientAuthentication"></a>
### <a name="authentication-in-the-client-library"></a>Autenticazione nella libreria client  
 Per impostazione predefinita, la libreria client WCF Data ServicesWCF Data Services non fornisce le credenziali quando si effettua una richiesta a un servizio OData.By default, the WCF Data Services client library does not supply credentials when making a request to an OData service. Quando le credenziali di accesso sono richieste dal servizio dati per autenticare un utente, è possibile fornire queste credenziali in un elemento <xref:System.Net.NetworkCredential> a cui accede la proprietà <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> di <xref:System.Data.Services.Client.DataServiceContext>, come nell'esempio seguente:  
  
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
  
 Per ulteriori informazioni, vedere [Procedura: specificare le credenziali client per una richiesta di servizio dati](specify-client-creds-for-a-data-service-request-wcf.md).  
  
 Quando il servizio dati richiede credenziali di accesso che non possono essere specificate tramite un oggetto <xref:System.Net.NetworkCredential>, ad esempio un cookie o un token basato sulle attestazioni, è necessario impostare manualmente le intestazioni nella richiesta HTTP, generalmente le intestazioni `Authorization` e `Cookie`. Per ulteriori informazioni su questo tipo di scenario di autenticazione, vedere il post di blog [OData and Authentication – Part 3 – ClientSide Hooks](https://devblogs.microsoft.com/odata/odata-and-authentication-part-3-clientside-hooks/). Per un esempio di come impostare le intestazioni HTTP in un messaggio di richiesta, vedere [Procedura: impostare intestazioni nella richiesta client](how-to-set-headers-in-the-client-request-wcf-data-services.md).  
  
## <a name="impersonation"></a>Rappresentazione  
 Generalmente il servizio dati accede alle risorse richieste, ad esempio i file sul server o un database, tramite le credenziali del processo di lavoro che ospita il servizio dati. Quando si usa la rappresentazione, ASP.NET applicazioni possono essere eseguite con l'identità Windows (account utente) dell'utente che effettua la richiesta. La rappresentazione è di utilizzo comune in applicazioni che si basano su IIS per autenticare l'utente e le credenziali di questo principio sono usate per accedere alle risorse richieste. Per ulteriori informazioni, vedere [ASP.NET Impersonation](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100)).  
  
## <a name="configuring-data-service-authorization"></a>Configurazione dell'autorizzazione del servizio dati  
 L'autorizzazione è il conferimento dell'accesso alle risorse dell'applicazione concesso a un principio o un processo identificato in base a un'autenticazione precedentemente riuscita. Come regola generale, è opportuno concedere agli utenti del servizio dati solo i diritti sufficienti per eseguire le operazioni richieste dalle applicazioni client.  
  
### <a name="restrict-access-to-data-service-resources"></a>Restrizione dell'accesso alle risorse del servizio dati  
 Per impostazione predefinita, WCF Data ServicesWCF Data Services consente di concedere l'accesso in lettura e scrittura comune alle risorse del servizio dati (set di entità e operazioni del servizio) a qualsiasi utente in grado di accedere al servizio dati. Le regole che definiscono l'accesso in lettura e scrittura possono essere specificate separatamente per ogni set di entità esposto dal servizio dati così come per qualsiasi operazione del servizio. Si consiglia di limitare l'accesso in lettura e scrittura solo alle risorse richieste dall'applicazione client. Per ulteriori informazioni, vedere Requisiti minimi di [accesso alle risorse](configuring-the-data-service-wcf-data-services.md#accessRequirements).  
  
### <a name="implement-role-based-interceptors"></a>Intercettori basati sulla regola di implementazione  
 Gli intercettori consentono di intercettare le richieste delle risorse del servizio dati prima che vengano elaborate dal servizio dati. Per ulteriori informazioni, consultate [Intercettori.](interceptors-wcf-data-services.md) Gli intercettori consentono di concedere l'autorizzazione in base all'utente autenticato che effettua la richiesta. Per un esempio di come limitare l'accesso alle risorse del servizio dati in base a un'identità utente autenticata, vedere [Procedura: intercettare](how-to-intercept-data-service-messages-wcf-data-services.md)i messaggi del servizio dati.  
  
### <a name="restrict-access-to-the-persisted-data-store-and-local-resources"></a>Restrizione dell'accesso all'archivio dati persistente e alle risorse locali  
 È opportuno concedere agli account usati per accedere all'archivio persistente solo i diritti in un database o nel file system sufficienti a supportare i requisiti del servizio dati. Quando viene usata l'autenticazione anonima, questo è l'account usato per eseguire l'applicazione hosting. Per altre informazioni, vedere [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md). Quando viene usata la rappresentazione, agli utenti autenticati deve essere concesso l'accesso alle risorse, generalmente come parte di un gruppo di Windows.  
  
## <a name="other-security-considerations"></a>Altre considerazioni sulla sicurezza  
  
### <a name="secure-the-data-in-the-payload"></a>Protezione dei dati nel payload  
OData si basa sul protocollo HTTP. In un messaggio HTTP, è possibile che l'intestazione contenga credenziali dell'utente rilevanti, a seconda dell'autenticazione implementata dal servizio dati. È possibile che anche il corpo del messaggio contenga dati del cliente rilevanti che devono essere protetti. In entrambi i casi, si consiglia di usare SSL per proteggere queste informazioni in rete.  
  
### <a name="ignored-message-headers-and-cookies"></a>Intestazioni dei messaggi e cookie ignorati  
 Le intestazioni delle richieste HTTP, diverse da quelle che dichiarano i tipi di contenuto e i percorsi delle risorse, vengono ignorate e non vengono mai impostate dal servizio dati.  
  
 I cookie possono essere utilizzati come parte di uno schema di autenticazione, ad esempio con ASP.NET l'autenticazione basata su form. Tuttavia, tutti i cookie HTTP impostati su una richiesta in ingresso vengono ignorati da WCF DataServices. L'host di un servizio dati può elaborare il cookie, ma il runtime di WCF Data ServicesWCF Data Services non analizza né restituisce mai i cookie. La libreria client WCF Data ServicesWCF Data Services inoltre non elabora i cookie inviati nella risposta.  
  
### <a name="custom-hosting-requirements"></a>Requisiti dell'hosting personalizzato  
 Per impostazione predefinita, WCF Data ServicesWCF Data Services viene creato come ASP.NET applicazione ospitata in IIS. In tal modo il servizio dati potrà usare i comportamenti sicuri della piattaforma. È possibile definire WCF Data ServicesWCF Data Services ospitati da un host personalizzato. Per ulteriori informazioni, vedere [Hosting del servizio dati](hosting-the-data-service-wcf-data-services.md). I componenti e la piattaforma che ospitano un servizio dati devono assicurare i seguenti comportamenti di sicurezza per impedire attacchi sul servizio dati:  
  
- Limitare la lunghezza dell'URI accettata in una richiesta del servizio dati per tutte le possibili operazioni.  
  
- Limitare la dimensione dei messaggi HTTP in ingresso e in uscita.  
  
- Limitare il numero totale di richieste in sospeso in qualsiasi momento.  
  
- Limitare le dimensioni delle intestazioni HTTP e i relativi valori e fornire l'accesso WCF Data ServicesWCF Data Services ai dati dell'intestazione.  
  
- Rilevare e contrastare gli attacchi noti, ad esempio attacchi di tipo riproduzione di messaggi e SYN TCP.  
  
### <a name="values-are-not-further-encoded"></a>Valori non ulteriormente codificati  
 I valori delle proprietà inviati al servizio dati non sono ulteriormente codificati dal runtime di WCF Data ServicesWCF Data Services . Ad esempio, quando una proprietà di stringa di un'entità contiene contenuto HTML formattato, i tag non vengono codificati nel formato HTML dal servizio dati. Il servizio dati non codifica ulteriormente neanche i valori di proprietà nella risposta. La libreria client inoltre non esegue nessuna codifica aggiuntiva.  
  
### <a name="considerations-for-client-applications"></a>Considerazioni per le applicazioni client  
 Le considerazioni sulla sicurezza seguenti si applicano alle applicazioni che utilizzano il client WCF Data ServicesWCF Data Services per accedere ai servizi OData:The following security considerations apply to applications that use the WCF Data Services client to access OData services:  
  
- La libreria client presuppone che i protocolli usati per accedere al servizio dati forniscano un livello di sicurezza appropriato.  
  
- La libreria client usa tutti i valori predefiniti per i timeout e le opzioni di analisi degli stack di trasporto forniti dalla piattaforma sottostante.  
  
- La libreria client non legge le impostazioni dai file di configurazione dell'applicazione.  
  
- La libreria client non implementa alcun meccanismo di accesso tra domini. Al contrario, usa i meccanismi forniti dallo stack HTTP sottostante.  
  
- La libreria client non dispone di elementi dell'interfaccia utente e non visualizza i dati né esegue il rendering dei dati che riceve o invia.  
  
- È opportuno che le applicazioni client convalidino sempre l'input dell'utente e i dati accettati da servizi non attendibili.  
  
## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Libreria client WCF Data Services](wcf-data-services-client-library.md)

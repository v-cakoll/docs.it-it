---
title: Procedure consigliate per l'hosting in Internet Information Services (IIS)
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: e62fed4f6a711ecc317b8f758d4948a477d136e1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595271"
---
# <a name="internet-information-services-hosting-best-practices"></a>Procedure consigliate per l'hosting in Internet Information Services (IIS)
In questo argomento vengono descritte alcune procedure consigliate per l'hosting di servizi Windows Communication Foundation (WCF).  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementazione di servizi WCF come DLL  
 L'implementazione di un servizio WCF come DLL distribuita nella directory \bin di un'applicazione Web consente di riutilizzare il servizio all'esterno del modello di applicazione Web, ad esempio in un ambiente di testing in cui non è possibile distribuire Internet Information Services (IIS).  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Host di servizi in applicazioni ospitate da IIS  
 Non utilizzare le API self-host imperative per creare nuovi host di servizio in ascolto sui trasporti di rete non supportati in modo nativo dall'ambiente host IIS (ad esempio, IIS 6,0 per ospitare i servizi TCP, perché la comunicazione TCP non è supportata in modo nativo in IIS 6,0). Questo approccio non è consigliato. Gli host di servizi creati in modo imperativo non sono conosciuti all'interno dell'ambiente host IIS. Il punto critico è il fatto che l'elaborazione eseguita da servizi creati in modo imperativo non viene considerata da IIS quando determina se il pool di applicazioni host è inattivo. Di conseguenza, le applicazioni con host di servizi creati in modo imperativo hanno un ambiente host IIS che elimina bruscamente i processi host IIS.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URI ed endpoint ospitati da IIS  
 Gli endpoint per un servizio ospitato da IIS devono essere configurati tramite URI (Uniform Resource Identifier), non tramite indirizzi assoluti. Ciò garantisce che l'indirizzo endpoint rientri nel set di indirizzi URI che appartengono all'applicazione host e assicurano che l'attivazione basata su messaggi si verifichi come previsto.  
  
## <a name="state-management-and-process-recycling"></a>Riciclo del processo e della gestione dello stato  
 L'ambiente host IIS è ottimizzato per servizi che non mantengono lo stato locale in memoria. IIS ricicla il processo host in risposta a numerosi eventi esterni e interni, causando la perdita di qualsiasi stato volatile archiviato esclusivamente in memoria. I servizi ospitati in IIS devono archiviare il proprio stato fuori dal processo (ad esempio, in un database) o in una cache in memoria che può essere ricreata facilmente se si verifica un evento di riciclo dell'applicazione.  
  
> [!NOTE]
> I protocolli utilizzati da WCF per garantire l'affidabilità e la sicurezza a livello di messaggio utilizzano lo stato in memoria volatile. Le sessioni affidabili e le sessioni di sicurezza di WCF possono terminare in modo imprevisto a causa di riciclo dell'applicazione. Le applicazioni ospitate da IIS che utilizzano questi protocolli devono dipendere da una chiave di sessione fornita da WCF per la correlazione dello stato del livello applicazione, ad esempio un costrutto a livello di applicazione o un'intestazione di correlazione personalizzata, oppure disabilitare il riciclo dei processi IIS per l'applicazione ospitata.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Ottimizzazione delle prestazioni in scenari di livello intermedio  
 Per ottenere prestazioni ottimali in uno *scenario di livello intermedio*, ovvero un servizio che effettua chiamate ad altri servizi in risposta ai messaggi in arrivo, creare un'istanza del client del servizio WCF al servizio remoto e riutilizzarlo in più richieste in ingresso. La creazione di un'istanza dei client del servizio WCF è un'operazione costosa relativa all'esecuzione di una chiamata al servizio su un'istanza client preesistente e gli scenari di livello intermedio producono un miglioramento delle prestazioni distinto attraverso la memorizzazione nella cache di client remoti tra le richieste. I client del servizio WCF sono thread-safe, pertanto non è necessario sincronizzare l'accesso a un client su più thread.  
  
 Gli scenari di livello intermedio offrono vantaggi a livello di prestazioni anche utilizzando le API asincrone generate dall'opzione `svcutil /a`. L' `/a` opzione fa in modo che lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) generi i `BeginXXX/EndXXX` metodi per ogni operazione del servizio, che consente di effettuare chiamate potenzialmente prolungate a servizi remoti per i thread in background.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF in scenari multihomed o con nomi multipli  
 È possibile distribuire i servizi WCF all'interno di una Web farm IIS, in cui un set di computer condivide un nome esterno comune, ad esempio, `http://www.contoso.com` ma viene indirizzato singolarmente da nomi host diversi, ad esempio, `http://www.contoso.com` potrebbe indirizzare il traffico a due computer diversi denominati `http://machine1.internal.contoso.com` e `http://machine2.internal.contoso.com` . Questo scenario di distribuzione è completamente supportato da WCF, ma richiede una configurazione speciale del sito Web IIS che ospita i servizi WCF per visualizzare il nome host corretto (esterno) nei metadati del servizio (Web Services Description Language).  
  
 Per assicurarsi che venga visualizzato il nome host corretto nei metadati del servizio generati da WCF, configurare l'identità predefinita per il sito Web IIS che ospita i servizi WCF per l'utilizzo di un nome host esplicito. Ad esempio, i computer che risiedono all'interno della `www.contoso.com` farm devono usare un binding del sito IIS *: 80: www. contoso. com per http e \* : 443: www. contoso. com per HTTPS.  
  
 È possibile configurare le associazioni del sito Web IIS utilizzando lo snap-in IIS Microsoft Management Console (MMC).  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>I pool di applicazioni che sono in esecuzione in contesti utente diversi sovrascrivono gli assembly da altri account nella cartella temporanea  
 Per assicurarsi che i pool di applicazioni in esecuzione in contesti utente diversi non possano sovrascrivere gli assembly da altri account nella cartella temporanea dei file ASP.NET, utilizzare identità e cartelle temporanee diverse per applicazioni diverse. Se si hanno, ad esempio, due applicazioni virtuali /Application1 e / Application2, è possibile creare due pool Application, A e B, con due identità diverse. Il pool dell'applicazione A può essere eseguito sotto un'identità utente (user1) mentre il pool dell'applicazione B può essere eseguito sotto un'altra identità utente (user2). Configurare inoltre /Application1 in modo che utilizzi A e /Application2 in modo che utilizzi B.  
  
 In Web. config è possibile configurare la cartella temporanea usando \<system.web/compilation/@tempFolder> . Per/Application1, può essere "c:\tempForUser1" e per Application2 può essere "c:\tempForUser2". Concedere a queste due cartelle l'autorizzazione di scrittura corrispondente per le due identità.  
  
 Di conseguenza, user2 non può modificare la cartella di generazione del codice per /application2 (sotto c:\tempForUser1).  
  
## <a name="enabling-asynchronous-processing"></a>Abilitazione dell'elaborazione asincrona  
 Per impostazione predefinita, i messaggi inviati a un servizio WCF ospitato in IIS 6,0 e versioni precedenti vengono elaborati in modo sincrono. ASP.NET chiama WCF nel relativo thread (il thread di lavoro ASP.NET) e WCF usa un altro thread per elaborare la richiesta. Poiché il thread di lavoro viene mantenuto in WCF fino al completamento dell'elaborazione, le richieste vengono elaborate in modo sincrono. L'elaborazione asincrona delle richieste consente una maggiore scalabilità, poiché riduce il numero di thread necessari per l'elaborazione di una richiesta. WCF non viene tenuto al thread ASP.NET durante l'elaborazione della richiesta. Non è consigliabile usare il comportamento asincrono per i computer che eseguono IIS 6,0, perché non è possibile limitare le richieste in ingresso che aprono il server a attacchi *di tipo Denial of Service* (DOS). A partire da IIS 7.0, è stato introdotto un limite al numero di richieste simultanee, ovvero `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Grazie a questo nuovo limite, è possibile utilizzare l'elaborazione asincrona in modo sicuro.  Per impostazione predefinita, in IIS 7.0 il gestore asincrono e il modulo sono registrati. Se l'elaborazione asincrona di richieste è stata disattivata, è possibile abilitarla manualmente nel file Web.config dell'applicazione. Le impostazioni da utilizzare dipendono dall'impostazione `aspNetCompatibilityEnabled`. Se `aspNetCompatibilityEnabled` è impostato su `false`, configurare `System.ServiceModel.Activation.ServiceHttpModule` come illustrato nel frammento di configurazione seguente.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="false" />
  </system.serviceModel>  
  <system.webServer>  
    <modules>  
      <remove name="ServiceModel"/>  
      <add name="ServiceModel"
           preCondition="integratedMode,runtimeVersionv2.0"
           type="System.ServiceModel.Activation.ServiceHttpModule, System.ServiceModel,Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
    </modules>  
    </system.webServer>  
```  
  
 Se `aspNetCompatibilityEnabled` è impostato su `true`, configurare `System.ServiceModel.Activation.ServiceHttpHandlerFactory` come illustrato nel frammento di configurazione seguente.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
  </system.serviceModel>  
  <system.webServer>  
    <handlers>  
          <clear/>  
          <add name="TestAsyncHttpHandler"
               path="*.svc"
               verb="*"
               type="System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
               />  
    </handlers>
  </system.webServer>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di hosting di servizi](../samples/hosting.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))

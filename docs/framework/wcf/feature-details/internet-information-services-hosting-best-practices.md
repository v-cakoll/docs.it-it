---
title: Procedure consigliate per l'hosting in Internet Information Services (IIS)
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: 0ca5e20b846a1b10f5a52748ff06a4af958b2f4c
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46009401"
---
# <a name="internet-information-services-hosting-best-practices"></a>Procedure consigliate per l'hosting in Internet Information Services (IIS)
Questo argomento descrive alcune procedure consigliate per l'hosting di servizi Windows Communication Foundation (WCF).  
  
## <a name="implementing-wcf-services-as-dlls"></a>Implementazione di servizi WCF come DLL  
 L'implementazione di un WCF service come una DLL distribuita nella directory \bin di un'applicazione Web consente che riutilizzare il servizio all'esterno del modello di applicazione Web, ad esempio, in un ambiente di test che non abbia distribuito Internet Information Services (IIS).  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>Host di servizi in applicazioni ospitate da IIS  
 Non utilizzare API indipendenti imperative per creare nuovi host di servizi che ascoltano sulla rete trasporti non supportati a livello nativo dall'ambiente host IIS (ad esempio, [!INCLUDE[iis601](../../../../includes/iis601-md.md)] per ospitare servizi TCP, perché la comunicazione TCP non è supportata a livello nativo su [!INCLUDE[iis601](../../../../includes/iis601-md.md)]). Questo approccio non è consigliato. Gli host di servizi creati in modo imperativo non sono conosciuti all'interno dell'ambiente host IIS. Il punto critico è il fatto che l'elaborazione eseguita da servizi creati in modo imperativo non viene considerata da IIS quando determina se il pool di applicazioni host è inattivo. Di conseguenza, le applicazioni con host di servizi creati in modo imperativo hanno un ambiente host IIS che elimina bruscamente i processi host IIS.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URI ed endpoint ospitati da IIS  
 Gli endpoint per un servizio ospitato da IIS devono essere configurati tramite URI (Uniform Resource Identifier), non tramite indirizzi assoluti. Ciò garantisce che l'indirizzo endpoint rientri nel set di indirizzi URI che appartengono all'applicazione host e assicurano che l'attivazione basata su messaggi si verifichi come previsto.  
  
## <a name="state-management-and-process-recycling"></a>Riciclo del processo e della gestione dello stato  
 L'ambiente host IIS è ottimizzato per servizi che non mantengono lo stato locale in memoria. IIS ricicla il processo host in risposta a numerosi eventi esterni e interni, causando la perdita di qualsiasi stato volatile archiviato esclusivamente in memoria. I servizi ospitati in IIS devono archiviare il proprio stato fuori dal processo (ad esempio, in un database) o in una cache in memoria che può essere ricreata facilmente se si verifica un evento di riciclo dell'applicazione.  
  
> [!NOTE]
>  I protocolli WCF utilizzati per la sicurezza e affidabilità di livello di messaggio usano lo stato in memoria volatile. Le sessioni affidabili WCF e le sessioni di sicurezza potrebbero terminare in modo imprevisto a causa di ricicli delle applicazioni. Applicazioni ospitate in IIS che utilizzano questi protocolli devono dipendere da qualcosa diversa dalla chiave di sessione fornita da WCF per la correlazione tra stato a livello di applicazione (ad esempio, un costrutto a livello di applicazione o un'intestazione di correlazione personalizzata) oppure disabilitare Riciclo IIS per l'applicazione ospitata.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>Ottimizzazione delle prestazioni in scenari di livello intermedio  
 Per ottenere prestazioni ottimali in un *scenario di livello intermedio*, ovvero un servizio che effettua chiamate ad altri servizi in risposta ai messaggi in arrivo, creare una sola volta il client del servizio WCF al servizio remoto e riutilizzarla in più in ingresso richieste. Creazione di un'istanza client del servizio WCF è un'operazione dispendiosa rispetto all'esecuzione di un servizio di chiamata su un'istanza client preesistente e gli scenari di livello intermedio memorizzando miglioramenti delle prestazioni distinti client remoti tra le richieste. I client del servizio WCF sono thread-safe, pertanto non è necessario sincronizzare l'accesso a un client attraverso più thread.  
  
 Gli scenari di livello intermedio offrono vantaggi a livello di prestazioni anche utilizzando le API asincrone generate dall'opzione `svcutil /a`. Il `/a` opzione causa il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare `BeginXXX/EndXXX` metodi per ogni operazione del servizio, che consente chiamate potenzialmente di lunga ai servizi remoti da eseguire nella thread in background.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>WCF in scenari multihomed o con nomi multipli  
 È possibile distribuire i servizi WCF all'interno di una Web farm IIS, in cui un set di computer condividono un nome esterno comune (ad esempio http://www.contoso.com) ma sono indirizzati individualmente tramite nomi host diversi (ad esempio, http://www.contoso.com potrebbe indirizzare il traffico a due computer diversi denominati http://machine1.internal.contoso.com e http://machine2.internal.contoso.com). Questo scenario di distribuzione è completamente supportato da WCF, ma richiede una configurazione speciale del sito Web IIS che ospita i servizi WCF per visualizzare il nome di host corretto (esterno) nei metadati del servizio (Web Services Description Language).  
  
 Per garantire che venga visualizzato il nome host corretto nei metadati del servizio che WCF generato, configurare l'identità predefinita per il sito Web IIS che ospita i servizi WCF per utilizzare un nome host esplicito. Ad esempio, i computer che si trovano all'interno della farm www.contoso.com devono usare un'associazione del sito IIS di *: 80:www.contoso.com per HTTP e \*: 443:www.contoso.com per HTTPS.  
  
 È possibile configurare le associazioni del sito Web IIS utilizzando lo snap-in IIS Microsoft Management Console (MMC).  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>I pool di applicazioni che sono in esecuzione in contesti utente diversi sovrascrivono gli assembly da altri account nella cartella temporanea  
 Per assicurare che i pool di applicazioni in esecuzione in contesti utente diversi non possano sovrascrivere gli assembly da altri account nella cartella temporanea dei file [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], utilizzare identità diverse e cartelle temporanee per le diverse applicazioni. Se si hanno, ad esempio, due applicazioni virtuali /Application1 e / Application2, è possibile creare due pool Application, A e B, con due identità diverse. Il pool dell'applicazione A può essere eseguito sotto un'identità utente (user1) mentre il pool dell'applicazione B può essere eseguito sotto un'altra identità utente (user2). Configurare inoltre /Application1 in modo che utilizzi A e /Application2 in modo che utilizzi B.  
  
 Nel file Web. config, è possibile configurare la cartella temporanea utilizzando \< system.web/compilation/@tempFolder>. Per inoltre/Application1, può essere "c:\tempForUser1" e per application2, può essere "c:\tempForUser2". Concedere a queste due cartelle l'autorizzazione di scrittura corrispondente per le due identità.  
  
 Di conseguenza, user2 non può modificare la cartella di generazione del codice per /application2 (sotto c:\tempForUser1).  
  
## <a name="enabling-asynchronous-processing"></a>Abilitazione dell'elaborazione asincrona  
 Per impostazione predefinita i messaggi inviati a un servizio WCF ospitato in IIS 6.0 e versioni precedenti vengono processati in modo sincrono. ASP.NET chiama WCF nel relativo thread (il thread di lavoro ASP.NET) e WCF utilizza un altro thread per elaborare la richiesta. Poiché il thread di lavoro viene mantenuto in WCF fino al completamento dell'elaborazione, le richieste vengono elaborate in modo sincrono. L'elaborazione asincrona delle richieste consente una scalabilità maggiore poiché riduce il numero di thread necessarie per elaborare una richiesta, poiché WCF non viene mantenuto il thread ASP.NET durante l'elaborazione della richiesta. Utilizzo della modalità asincrona non è consigliato per computer che eseguono IIS 6.0 poiché non è possibile limitare le richieste in ingresso che espongono il server di *Denial Of Service* attacchi (DOS). A partire da IIS 7.0, è stato introdotto un limite al numero di richieste simultanee, ovvero `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`. Grazie a questo nuovo limite, è possibile utilizzare l'elaborazione asincrona in modo sicuro.  Per impostazione predefinita, in IIS 7.0 il gestore asincrono e il modulo sono registrati. Se l'elaborazione asincrona di richieste è stata disattivata, è possibile abilitarla manualmente nel file Web.config dell'applicazione. Le impostazioni da utilizzare dipendono dall'impostazione `aspNetCompatibilityEnabled`. Se `aspNetCompatibilityEnabled` è impostato su `false`, configurare `System.ServiceModel.Activation.ServiceHttpModule` come illustrato nel frammento di configurazione seguente.  
  
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
 [Esempi di Hosting del servizio](https://msdn.microsoft.com/library/f703a3f6-0fba-418a-a92f-7ce75ccfa47e)  
 [Windows Server AppFabric con funzionalità di Hosting](https://go.microsoft.com/fwlink/?LinkId=201276)

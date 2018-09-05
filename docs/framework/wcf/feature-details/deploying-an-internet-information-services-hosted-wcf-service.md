---
title: Distribuzione di un servizio WCF ospitato in Internet Information Services (IIS)
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: b2b58de703a0864ac0666cb4738a95726e28bcaf
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43740101"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Distribuzione di un servizio WCF ospitato in Internet Information Services (IIS)
Lo sviluppo e distribuzione di un servizio Windows Communication Foundation (WCF) ospitato in Internet Information Services (IIS) include le attività seguenti:  
  
-   Verificare che IIS, ASP.NET, WCF e il componente di attivazione WCF siano installati e registrati correttamente.  
  
-   Creare una nuova applicazione IIS o riusare un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] esistente.  
  
-   Creare un file con estensione svc del servizio WCF.  
  
-   Distribuire l'implementazione del servizio nell'applicazione IIS.  
  
-   Configurare il servizio WCF.  
  
 Per una procedura dettagliata della creazione di un servizio WCF ospitato in IIS, vedere [Procedura: ospitare un servizio WCF in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Verificare che IIS, ASP.NET e WCF siano installati e registrati correttamente.  
 WCF, IIS e ASP.NET deve essere installato per i servizi WCF ospitati in IIS funzioni correttamente. Le procedure per l'installazione di WCF (come parte di [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET e IIS variano a seconda della versione del sistema operativo in uso. Per altre informazioni sull'installazione di WCF e il [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], vedere [programma di installazione Web di Microsoft .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=201185). Vedere le istruzioni per l'installazione di IIS [installazione di IIS](https://go.microsoft.com/fwlink/?LinkId=201188).  
  
 Il processo di installazione per il [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] registra automaticamente WCF con IIS se IIS è già presente nel computer. Se si installa IIS dopo il [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], è necessario un passaggio aggiuntivo per registrare WCF con IIS e [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. A tal fine, è possibile procedere come segue, a seconda del sistema operativo:  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)], Windows 7, e [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: usare il [strumento di registrazione ServiceModel (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) strumento registrare WCF di IIS: per usare questo strumento, digitare **ServiceModelReg.exe /i /x** in Visual Studio prompt dei comandi. Per aprire il prompt dei comandi, fare clic sul pulsante Start, selezionare **Tutti i programmi**, **Microsoft Visual Studio 2012**, **Visual Studio Tools**, quindi **Prompt dei comandi di Visual Studio**.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]: installare il sottocomponente Componenti di attivazione di Windows Communication Foundation di [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. A tale scopo, nel Pannello di controllo, fare clic su **Aggiungi / Rimuovi programmi** e quindi **Add\/Installazione componenti di Windows**. Verrà avviata l' **Aggiunta guidata componenti di Windows**.  
  
-   Windows 7:  
  
 È necessario infine verificare che ASP.NET sia configurato per utilizzare .NET Framework 4. Per effettuare questa operazione, eseguire lo strumento ASPNET_Regiis con l'opzione -i. Per altre informazioni, vedere [strumento di registrazione ASP.NET IIS](https://go.microsoft.com/fwlink/?LinkId=201186)  
  
## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Creare una nuova applicazione IIS o riutilizzare un'applicazione ASP.NET esistente  
 Servizi WCF ospitati in IIS devono risiedere all'interno di un'applicazione IIS. È possibile creare una nuova applicazione IIS per ospitare servizi WCF in modo esclusivo. In alternativa, è possibile distribuire un servizio WCF in un'applicazione esistente che sta già ospitando [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] contenuto (ad esempio pagine aspx e servizi Web ASP.NET [ASMX]). Per altre informazioni su queste opzioni, vedere la "Hosting WCF Side-by-Side con ASP.NET" e "Hosting WCF Services in modalità di compatibilità ASP.NET" sezioni nel [servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
 Si noti che in [!INCLUDE[iis601](../../../../includes/iis601-md.md)] e versioni successive un'applicazione di programmazione isolata e orientata a oggetti viene riavviata periodicamente. Il valore predefinito è 1740 minuti. Il valore massimo supportato è 71.582 minuti. Il riavvio può essere disabilitato. Per altre informazioni su questa proprietà, vedere la [PeriodicRestartTime](https://go.microsoft.com/fwlink/?LinkId=109968).  
  
## <a name="create-an-svc-file-for-the-wcf-service"></a>Creare un file con estensione svc per il servizio WCF  
 Servizi WCF ospitati in IIS sono rappresentati come file di dati speciali (file con estensione svc) all'interno dell'applicazione IIS. Questo modello è simile al modo in cui le pagine ASMX sono rappresentate all'interno di un'applicazione IIS come file con estensione asmx. Un file con estensione svc contiene una direttiva di elaborazione specifica di WCF ([\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)) che consente l'infrastruttura di hosting di WCF di attivare servizi ospitati in risposta ai messaggi in arrivo. La sintassi più comune per un file con estensione svc viene illustrata nell'istruzione seguente:  
  
```  
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>  
```  
  
 È costituito il [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva e un solo attributo, `Service`. Il valore dell'attributo `Service` è il nome del tipo Common Language Runtime (CLR) dell'implementazione del servizio. L'utilizzo di questa direttiva equivale fondamentalmente alla creazione di un host del servizio tramite il seguente codice:  
  
```csharp  
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );  
```  
  
 È inoltre possibile una configurazione di hosting aggiuntiva, ad esempio la creazione di un elenco di indirizzi di base per il servizio. È anche possibile utilizzare un <xref:System.ServiceModel.Activation.ServiceHostFactory> personalizzato per estendere la direttiva per l'utilizzo con soluzioni di hosting personalizzate. Le applicazioni di IIS che ospitano servizi WCF non sono responsabili della gestione di creazione e la durata di <xref:System.ServiceModel.ServiceHost> istanze. L'infrastruttura di hosting WCF gestito creerà i necessari <xref:System.ServiceModel.ServiceHost> dell'istanza in modo dinamico quando viene ricevuta la prima richiesta per il file con estensione svc. L'istanza non viene rilasciata finché non viene chiusa in modo esplicito dal codice o finché l'applicazione non viene riciclata.  
  
 Per altre informazioni sulla sintassi dei file con estensione svc, vedere [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).  
  
## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Distribuire l'implementazione del servizio all'applicazione IIS  
 Servizi WCF ospitati in IIS utilizzano lo stesso modello di compilazione dinamica come [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]. Come [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], è possibile distribuire il codice di implementazione per i servizi WCF ospitati in IIS in vari modi e in varie posizioni, come indicato di seguito:  
  
-   Come file dll precompilato nella Global Assembly Cache (GAC) o nella directory \bin dell'applicazione. I file binari precompilati non vengono aggiornati finché non viene distribuita una nuova versione della libreria di classi.  
  
-   Come file di origine non compilati che si trovano nella directory \App_Code dell'applicazione. I file di origine situati in questa directory vengono richiesti dinamicamente durante l'elaborazione della prima richiesta dell'applicazione. Qualsiasi modifica ai file nella directory \App_Code provoca il riciclo e la ricompilazione dell'intera applicazione quando viene ricevuta la richiesta successiva.  
  
-   Come codice non compilato posizionato direttamente nel file con estensione svc. Codice di implementazione può essere anche trovarsi in linea nel file con estensione svc del servizio, dopo il \@direttiva ServiceHost. Qualsiasi modifica al codice inline provoca il riciclo e la ricompilazione dell'applicazione quando viene ricevuta la richiesta successiva.  
  
 Per altre informazioni sul [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] modello di compilazione, vedere [Cenni preliminari sulla compilazione ASP.NET](https://go.microsoft.com/fwlink/?LinkId=94773).  
  
## <a name="configure-the-wcf-service"></a>Configurare il servizio WCF  
 Servizi WCF ospitati in IIS memorizzano la propria configurazione nel file Web. config dell'applicazione. Servizi ospitati in IIS usano la sintassi e gli stessi elementi di configurazione come servizi WCF ospitati all'esterno di IIS. I vincoli seguenti sono tuttavia specifici per l'ambiente host IIS:  
  
-   Indirizzi di base per i servizi ospitati in IIS.  
  
-   Le applicazioni di servizi di hosting WCF all'esterno di IIS possono controllarne l'indirizzo di base dei servizi che ospitano passando un set di base indirizzo URI per il <xref:System.ServiceModel.ServiceHost> costruttore o fornendo un [ \<host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) elemento il configurazione del servizio. I servizi ospitati in IIS non sono in grado di controllare i propri indirizzi di base che corrispondono agli indirizzi dei rispettivi file con estensione svc.  
  
### <a name="endpoint-addresses-for-iis-hosted-services"></a>Indirizzi endpoint per i servizi ospitati in IIS  
 Quando sono ospitati in IIS, gli indirizzi endpoint sono sempre considerati relativi all'indirizzo del file con estensione svc che rappresenta il servizio. Ad esempio, se l'indirizzo di base di un servizio WCF è http://localhost/Application1/MyService.svc con la configurazione dell'endpoint seguente.  
  
```xml  
<endpoint address="anotherEndpoint" .../>  
```  
  
 Ciò fornisce un endpoint che è possibile contattarlo "http://localhost/Application1/MyService.svc/anotherEndpoint".  
  
 Analogamente, l'elemento di configurazione di endpoint che usa una stringa vuota come indirizzo relativo fornisce un endpoint raggiungibile al http://localhost/Application1/MyService.svc, ovvero l'indirizzo di base.  
  
```xml  
<endpoint address="" ... />  
```  
  
 Per gli endpoint del servizio ospitati in IIS è necessario utilizzare sempre indirizzi endpoint relativi. Fornisce un indirizzo endpoint completo (ad esempio, http://localhost/MyService.svc) può provocare errori nella distribuzione del servizio se l'indirizzo dell'endpoint non punta all'applicazione IIS che ospita il servizio che espone l'endpoint. L'utilizzo di indirizzi endpoint relativi per i servizi di hosting evita potenziali conflitti.  
  
### <a name="available-transports"></a>Trasporti disponibili  
 Servizi WCF ospitati in IIS 5.1 e [!INCLUDE[iis601](../../../../includes/iis601-md.md)] sono limitate all'uso di comunicazioni basate su HTTP. Su queste piattaforme IIS, la configurazione di un servizio ospitato affinché utilizzi un'associazione non HTTP, comporta un errore durante l'attivazione del servizio. Per [!INCLUDE[iisver](../../../../includes/iisver-md.md)], i trasporti supportati includono HTTP, Net.TCP, Net.Pipe, Net.MSMQ e msmq.formatname per la compatibilità delle versioni precedenti con le applicazioni MSMQ esistenti.  
  
### <a name="http-transport-security"></a>Protezione del trasporto HTTP  
 Servizi WCF ospitati in IIS possono avvalersi del protocollo HTTP (ad esempio, HTTPS e HTTP gli schemi di autenticazione, ad esempio Basic, Digest e l'autenticazione integrata di Windows) di sicurezza del trasporto, purché la directory virtuale IIS che contiene il servizio supporta quelli Impostazioni. Le impostazioni di sicurezza del trasporto HTTP sull'associazione di un endpoint di hosting devono corrispondere alle impostazioni di sicurezza del trasporto sulla directory virtuale IIS che lo contiene.  
  
 Ad esempio, un endpoint WCF configurato per usare l'autenticazione digest HTTP deve risiedere in una directory virtuale IIS che è configurata anche per consentire l'autenticazione digest HTTP. Combinazioni non corrispondenti di impostazioni di IIS e le impostazioni di endpoint WCF generano un errore durante l'attivazione del servizio.  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting in Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Procedure consigliate per l'hosting in Internet Information Services (IIS)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Windows Server AppFabric con funzionalità di Hosting](https://go.microsoft.com/fwlink/?LinkId=201276)

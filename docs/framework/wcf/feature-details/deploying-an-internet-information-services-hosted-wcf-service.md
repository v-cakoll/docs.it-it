---
title: Distribuzione di un servizio WCF ospitato in Internet Information Services (IIS)
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 67f6877546951bd92b235218f10f6ccc7011ef5c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463859"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Distribuzione di un servizio WCF ospitato in Internet Information Services (IIS)

Lo sviluppo e la distribuzione di un servizio Windows Communication Foundation (WCF) ospitato in Internet Information Services (IIS) è costituito dalle attività seguenti:

- Assicurarsi che IIS, ASP.NET, WCF e il componente di attivazione WCF siano installati e registrati correttamente.

- Creare una nuova applicazione IIS o riutilizzare un'applicazione ASP.NET esistente.

- Creare un file con estensione svc per il servizio WCF.

- Distribuire l'implementazione del servizio nell'applicazione IIS.

- Configurare il servizio WCF.

Per una procedura dettagliata della creazione di un servizio WCF ospitato da IIS, vedere [Procedura: ospitare un servizio WCF in IIS](how-to-host-a-wcf-service-in-iis.md).

## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Verificare che IIS, ASP.NET e WCF siano installati e registrati correttamente.

PER il corretto funzionamento dei servizi WCF ospitati da IIS, è necessario che i servizi WCF WCF, IIS e ASP.NET. Le procedure per l'installazione di WCF (come parte di .NET Framework), ASP.NET e IIS variano a seconda del sistema operativo. Per ulteriori informazioni sull'installazione di WCF e .NET Framework, vedere [Installare .NET Framework per gli sviluppatori](../../install/guide-for-developers.md). Per installare IIS in Windows 10, aprire **Programmi e funzionalità** nel Pannello di **controllo** e quindi selezionare Attiva o disattiva le funzionalità **di Windows**. In **Funzionalità Windows**selezionare Internet Information **Services** e quindi scegliere **OK**.

![Funzionalità di Windows con IIS evidenziato](./media/windows-features-iis.png)

Le istruzioni per l'installazione di IIS in altri sistemi operativi sono disponibili in [Installare IIS in Windows Vista e Windows 7](/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7) e Installare [IIS 8.5 in Windows Server 2012 R2.](/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2)

Il processo di installazione di .NET Framework registra automaticamente WCF con IIS se IIS è già presente nel computer. Se IIS viene installato dopo .NET Framework, è necessario un passaggio aggiuntivo per registrare WCF con IIS e ASP.NET. A tal fine, è possibile procedere come segue, a seconda del sistema operativo:

- Windows 7 e Windows Server 2003: utilizzare lo [strumento ServiceModel Registration Tool (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) per registrare WCF con IIS. Per utilizzare questo strumento, digitare **ServiceModelReg.exe /i /x** nel prompt dei comandi per [gli sviluppatori per Visual Studio](../../tools/developer-command-prompt-for-vs.md).

- Windows 7: infine, è necessario verificare che ASP.NET sia configurata per l'utilizzo di .NET Framework versione 4 o successiva. A tale scopo, eseguire lo `–i` strumento ASPNET_Regiis con l'opzione. Per ulteriori informazioni, vedere [ASP.NET strumento di registrazione IIS](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90)).

## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Creare una nuova applicazione IIS o riutilizzare un'applicazione ASP.NET esistente

I servizi WCF ospitati da IIS devono risiedere all'interno di un'applicazione IIS. È possibile creare una nuova applicazione IIS per ospitare esclusivamente i servizi WCF. In alternativa, è possibile distribuire un servizio WCF in un'applicazione esistente che ospita già ASP.NET contenuto 2.0 (ad esempio pagine aspx e servizi Web ASP.NET [ASMX]). Per ulteriori informazioni su queste opzioni, vedere le sezioni "Hosting WCF Side-by-Side with ASP.NET" e "Hosting di servizi WCF in modalità compatibilità ASP.NET" in [Servizi WCF e ASP.NET](wcf-services-and-aspnet.md).

Si noti che IIS 6.0 e versioni successive riavviano periodicamente un'applicazione di programmazione isolata orientata agli oggetti. Il valore predefinito è 1740 minuti. Il valore massimo supportato è 71.582 minuti. Il riavvio può essere disabilitato. Per ulteriori informazioni su questa proprietà, vedere [PeriodicRestartTime](https://docs.microsoft.com/previous-versions/iis/6.0-sdk/ms525914(v=vs.90)).

## <a name="create-an-svc-file-for-the-wcf-service"></a>Creare un file con estensione svc per il servizio WCF

I servizi WCF ospitati in IIS sono rappresentati come file di contenuto speciali (file con estensione svc) all'interno dell'applicazione IIS. Questo modello è simile al modo in cui le pagine ASMX sono rappresentate all'interno di un'applicazione IIS come file con estensione asmx. Un file con estensione svc contiene una direttiva di elaborazione specifica di WCF ([\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)) che consente all'infrastruttura di hosting WCF di attivare i servizi ospitati in risposta ai messaggi in arrivo. La sintassi più comune per un file con estensione svc viene illustrata nell'istruzione seguente:

`<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>`

È costituito dalla `Service` [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva ServiceHost e da un singolo attributo, . Il valore dell'attributo `Service` è il nome del tipo Common Language Runtime (CLR) dell'implementazione del servizio. L'utilizzo di questa direttiva equivale fondamentalmente alla creazione di un host del servizio tramite il seguente codice:

```csharp
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );
```

È inoltre possibile una configurazione di hosting aggiuntiva, ad esempio la creazione di un elenco di indirizzi di base per il servizio. È anche possibile utilizzare un <xref:System.ServiceModel.Activation.ServiceHostFactory> personalizzato per estendere la direttiva per l'utilizzo con soluzioni di hosting personalizzate. Le applicazioni IIS che ospitano i servizi WCF <xref:System.ServiceModel.ServiceHost> non sono responsabili della gestione della creazione e della durata delle istanze. L'infrastruttura di hosting <xref:System.ServiceModel.ServiceHost> WCF gestita crea l'istanza necessaria in modo dinamico quando viene ricevuta la prima richiesta per il file con estensione svc. L'istanza non viene rilasciata finché non viene chiusa in modo esplicito dal codice o finché l'applicazione non viene riciclata.

Per ulteriori informazioni sulla sintassi dei file con estensione svc, vedere [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).

## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Distribuire l'implementazione del servizio all'applicazione IIS

I servizi WCF ospitati in IIS usano lo stesso modello di compilazione dinamica di ASP.NET 2.0. Come con ASP.NET, è possibile distribuire il codice di implementazione per i servizi WCF ospitati da IIS in diversi modi in varie posizioni, come indicato di seguito:

- Come file dll precompilato nella Global Assembly Cache (GAC) o nella directory \bin dell'applicazione. I file binari precompilati non vengono aggiornati finché non viene distribuita una nuova versione della libreria di classi.

- Come file di origine non compilati che si trovano nella directory App_Code dell'applicazione. I file di origine situati in questa directory vengono richiesti dinamicamente durante l'elaborazione della prima richiesta dell'applicazione. Qualsiasi modifica ai file nella directory \App_Code provoca il riciclo e la ricompilazione dell'intera applicazione quando viene ricevuta la richiesta successiva.

- Come codice non compilato inserito direttamente nel file con estensione svc. Il codice di implementazione può anche essere posizionato inline \@nel file con estensione svc del servizio, dopo la direttiva ServiceHost.Implementation code can also be inline in the service's .svc file, after the ServiceHost directive. Qualsiasi modifica al codice inline provoca il riciclo e la ricompilazione dell'applicazione quando viene ricevuta la richiesta successiva.

Per ulteriori informazioni sul modello di compilazione di ASP.NET 2.0, vedere [Cenni preliminari](https://docs.microsoft.com/previous-versions/aspnet/ms178466(v=vs.100))sulla compilazione ASP.NET .

## <a name="configure-the-wcf-service"></a>Configurare il servizio WCF

I servizi WCF ospitati da IIS archiviano la configurazione nel file Web.config delle applicazioni. I servizi ospitati da IIS utilizzano gli stessi elementi di configurazione e la stessa sintassi dei servizi WCF ospitati all'esterno di IIS. I vincoli seguenti sono tuttavia specifici per l'ambiente host IIS:

- Indirizzi di base per i servizi ospitati in IIS.

- Le applicazioni che ospitano servizi WCF all'esterno di IIS possono controllare l'indirizzo <xref:System.ServiceModel.ServiceHost> di base dei servizi che ospitano passando un set di URI dell'indirizzo di base al costruttore o fornendo un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) host>elemento nella configurazione del servizio. I servizi ospitati in IIS non sono in grado di controllare i propri indirizzi di base che corrispondono agli indirizzi dei rispettivi file con estensione svc.

### <a name="endpoint-addresses-for-iis-hosted-services"></a>Indirizzi endpoint per i servizi ospitati in IIS

Quando sono ospitati in IIS, gli indirizzi endpoint sono sempre considerati relativi all'indirizzo del file con estensione svc che rappresenta il servizio. Ad esempio, se l'indirizzo di `http://localhost/Application1/MyService.svc` base di un servizio WCF è con la configurazione dell'endpoint seguente:For example, if the base address of a WCF service is with the following endpoint configuration:

```xml
<endpoint address="anotherEndpoint" />
```

In questo modo viene fornito `http://localhost/Application1/MyService.svc/anotherEndpoint`un endpoint raggiungibile in .

Analogamente, l'elemento di configurazione dell'endpoint che utilizza una `http://localhost/Application1/MyService.svc`stringa vuota come indirizzo relativo fornisce un endpoint raggiungibile in , ovvero l'indirizzo di base.

```xml
<endpoint address="" />
```

Per gli endpoint del servizio ospitati in IIS è necessario utilizzare sempre indirizzi endpoint relativi. La fornitura di un indirizzo endpoint `http://localhost/MyService.svc`completo, ad esempio , può causare errori nella distribuzione del servizio se l'indirizzo dell'endpoint non punta all'applicazione IIS che ospita il servizio esponendo l'endpoint. L'utilizzo di indirizzi endpoint relativi per i servizi di hosting evita potenziali conflitti.

### <a name="available-transports"></a>Trasporti disponibili

I servizi WCF ospitati in IIS 5.1 e IIS 6.0 sono limitati all'utilizzo della comunicazione basata su HTTP. Su queste piattaforme IIS, la configurazione di un servizio ospitato affinché utilizzi un'associazione non HTTP, comporta un errore durante l'attivazione del servizio. Per IIS 7.0, i trasporti supportati includono HTTP, Net.TCP, Net.Pipe, Net.MSMQ e msmq.formatname per garantire la compatibilità con le versioni precedenti di MSMQ.

### <a name="http-transport-security"></a>Protezione del trasporto HTTP

I servizi WCF ospitati da IIS possono utilizzare la sicurezza del trasporto HTTP (ad esempio, gli schemi di autenticazione HTTPS e HTTP, ad esempio di base, digest e autenticazione integrata di Windows) purché la directory virtuale IIS che contiene il servizio supporti tali impostazioni. Le impostazioni di sicurezza del trasporto HTTP sull'associazione di un endpoint di hosting devono corrispondere alle impostazioni di sicurezza del trasporto sulla directory virtuale IIS che lo contiene.

Ad esempio, un endpoint WCF configurato per utilizzare l'autenticazione del digest HTTP deve risiedere in una directory virtuale IIS configurata anche per consentire l'autenticazione del digest HTTP. Combinazioni non corrispondenti di impostazioni IIS e impostazioni dell'endpoint WCF generano un errore durante l'attivazione del servizio.

## <a name="see-also"></a>Vedere anche

- [Host in Internet Information Services](hosting-in-internet-information-services.md)
- [Procedure consigliate per l'hosting in Internet Information Services (IIS)](internet-information-services-hosting-best-practices.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))

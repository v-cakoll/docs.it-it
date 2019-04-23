---
title: 'Procedura: Abilitare la traccia WIF'
ms.date: 03/30/2017
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
author: BrucePerlerMS
ms.openlocfilehash: 83382a8375538acc04d293ee938a4e845d5e8820
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59769034"
---
# <a name="how-to-enable-wif-tracing"></a>Procedura: Abilitare la traccia WIF
## <a name="applies-to"></a>Si applica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Web Form ASP.NET®  
  
## <a name="summary"></a>Riepilogo  
 Questo argomento include le procedure dettagliate per abilitare la traccia WIF in un'applicazione ASP.NET. Sono inoltre disponibili istruzioni per testare l'applicazione per verificare che il listener e il log di traccia funzionino correttamente. In questa guida procedurale non sono incluse le istruzioni dettagliate per la creazione di un servizio token di sicurezza (STS, Security Token Service); viene invece utilizzato il servizio token di sicurezza di sviluppo che viene fornito con lo strumento Identity and Access. Il servizio token di sicurezza di sviluppo non esegue una reale autenticazione ed è finalizzato unicamente ai test. Per completare questa guida procedurale sarà necessario installare Identity and Access Tool. Può essere scaricato dal seguente percorso: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)  
  
> [!IMPORTANT]
>  L'abilitazione della traccia WIF per le applicazioni passive, ovvero le applicazioni che usano il protocollo WS-Federation, possono esporre potenzialmente l'applicazione ad attacchi Denial of Service (DoS) o alla divulgazione di informazioni a malintenzionati. Sono inclusi sia i relying party passivi che i servizi token di sicurezza passivi. Per questo motivo, è consigliabile non abilitare la traccia WIF per relying party passivi o servizi token di sicurezza passivi in ambiente di produzione.  
  
## <a name="contents"></a>Sommario  
  
-   Obiettivi  
  
-   Panoramica  
  
-   Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare la traccia  
  
-   Passaggio 2: eseguire i test sulla soluzione  
  
## <a name="objectives"></a>Obiettivi  
  
-   Creare un'applicazione ASP.NET semplice che usa WIF e il servizio token di sicurezza per lo sviluppo locale dallo strumento Identity and Access  
  
-   Abilitare la traccia e verificare che funzioni  
  
## <a name="overview"></a>Panoramica  
 La traccia consente di eseguire il debug e la risoluzione di molti tipi di problemi con WIF, inclusi token, cookie, attestazioni, messaggi del protocollo e altro ancora. La traccia WIF è simile alla traccia WCF. Ad esempio, è possibile scegliere il livello di dettaglio delle tracce per visualizzare i vari tipi di messaggi, da solo quelli critici a tutti i messaggi. Le tracce WIF possono essere generate in file **xml** o in file **svclog** visualizzabili tramite il visualizzatore di tracce di servizi (Service Trace Viewer). Questo strumento è disponibile nel **bin** directory di Windows SDK percorso di installazione nel computer, ad esempio: **C:\Programmi\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.  
  
## <a name="summary-of-steps"></a>Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare la traccia  
  
-   Passaggio 2: eseguire i test sulla soluzione  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a>Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare la traccia  
 In questo passaggio verrà creata una nuova applicazione Web Form ASP.NET e si modificherà il file *Web.config* per abilitare la traccia.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Per creare un'applicazione ASP.NET semplice  
  
1. Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.  
  
2. Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.  
  
3. In **Nome** immettere `TestApp` e fare clic su **OK**.  
  
4. Fare clic con il pulsante destro del mouse sul progetto **TestApp** in **Esplora soluzioni** e quindi scegliere **Identity and Access**.  
  
5. Verrà visualizzata la finestra **Identity and Access**. In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**.  
  
6. Creare una nuova cartella denominata **registri** nella radice del **c:** unità, ad esempio illustrato: **C:\Logs.**  
  
7. Aggiungere l'elemento **\<system.diagnostics>** seguente al file di configurazione *Web.config* subito dopo l'elemento di chiusura **\</configSections>**, come illustrato:  
  
    ```xml  
    <configuration>  
        <configSections>  
            ...
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  Il percorso di directory specificato nell'attributo **initializeData** deve esistere prima di poter avviare la registrazione. Se il percorso non esiste, non verrà creato alcun log.  
  
     Le impostazioni di configurazione precedenti abilitano la traccia **Verbose** per WIF e salvano il log risultante nel file **C:logsWIF.xml**.  
  
## <a name="step-2--test-your-solution"></a>Passaggio 2: eseguire i test sulla soluzione  
 In questo passaggio si testerà l'applicazione ASP.NET abilitata per WIF per verificare che i log vengano registrati.  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a>Per testare il corretto funzionamento della traccia per l'applicazione ASP.NET abilitata per WIF  
  
1. Eseguire la soluzione premendo **F5**. Dovrebbe essere visualizzata la home page predefinita di ASP.NET e l'autenticazione dovrebbe avvenire automaticamente con il nome utente *Terry*, ovvero l'utente predefinito restituito dal servizio token di sicurezza per lo sviluppo.  
  
2. Chiudere la finestra del browser e passare quindi alla cartella **C:\logs**. Aprire il file **C:\logs\WIF.xml** con un editor di testo.  
  
3. Controllare il file **WIF.xml** e verificare che contenga voci che iniziano con **\<E2ETraceEvent>**. Queste tracce conterranno elementi **\<TraceRecord >** con le descrizioni per l'attività di traccia, ad esempio **Convalida di SecurityToken**.

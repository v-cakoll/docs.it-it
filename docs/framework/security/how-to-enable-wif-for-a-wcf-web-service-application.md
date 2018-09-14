---
title: "Procedura: Abilitare WIF per un'applicazione del servizio Web WCF"
ms.date: 03/30/2017
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 71897299d68c2f0e43def8e70730ea456d6e9e24
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45514625"
---
# <a name="how-to-enable-wif-for-a-wcf-web-service-application"></a>Procedura: Abilitare WIF per un'applicazione del servizio Web WCF
## <a name="applies-to"></a>Si applica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Microsoft® Windows® Communication Foundation (WCF)  
  
## <a name="summary"></a>Riepilogo  
 In questa guida procedurale vengono fornite le procedure dettagliate per abilitare WIF in un servizio Web WCF. Vengono inoltre fornite le istruzioni su come testare l'applicazione per verificare il corretto funzionamento del servizio Web presentando delle attestazioni quando l'applicazione viene eseguita. In questa guida procedurale non sono incluse le istruzioni dettagliate per la creazione di un servizio token di sicurezza (STS, Security Token Service); viene invece utilizzato il servizio token di sicurezza di sviluppo che viene fornito con lo strumento Identity and Access. Il servizio token di sicurezza di sviluppo non esegue una reale autenticazione ed è finalizzato unicamente ai test. Per completare questa guida procedurale sarà necessario installare Identity and Access Tool. Questo strumento può essere scaricato dal seguente percorso: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)  
  
## <a name="contents"></a>Sommario  
  
-   Obiettivi  
  
-   Panoramica  
  
-   Riepilogo dei passaggi  
  
-   Passaggio 1: creare un semplice servizio WCF  
  
-   Passaggio 2: creare un'applicazione client per il servizio WCF  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="objectives"></a>Obiettivi  
  
-   Creare un servizio WCF che richiede token pubblicati  
  
-   Creare un client WCF che richiede un token da un servizio token di sicurezza e lo passa al servizio WCF  
  
## <a name="overview"></a>Panoramica  
 In questa guida procedurale viene illustrato in che modo uno sviluppatore può utilizzare l'autenticazione federata durante lo sviluppo di servizi WCF. Trai i vantaggi derivanti dall'utilizzo della federazione nei servizi WCF sono inclusi:  
  
1.  Factoring della logica dell'autenticazione dal codice del servizio WCF  
  
2.  Riutilizzo delle soluzioni esistenti di gestione delle identità  
  
3.  Interoperabilità con altre soluzioni di identità  
  
4.  Flessibilità e resilienza verso le modifiche future  
  
 WIF e il corrispondente Identity and Access Tool semplificano lo sviluppo e il test di un servizio WCF utilizzando l'autenticazione con federazione, come mostrato nei passaggi che seguono.  
  
## <a name="summary-of-steps"></a>Riepilogo dei passaggi  
  
-   Passaggio 1: creare un semplice servizio WCF  
  
-   Passaggio 2: creare un'applicazione client per il servizio WCF  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="step-1--create-a-simple-wcf-service"></a>Passaggio 1: creare un semplice servizio WCF  
 In questo passaggio, verrà creato un nuovo servizio WCF che utilizza il servizio token di sicurezza di sviluppo incluso in Identity and Access Tool.  
  
#### <a name="to-create-a-simple-wcf-service"></a>Per creare un semplice servizio WCF  
  
1.  Avviare Visual Studio come amministratore in modalità con privilegi elevati.  
  
2.  In Visual Studio fare clic su **File**, **Nuovo** e quindi su **Progetto**.  
  
3.  Nella finestra **Nuovo progetto** fare clic su **Applicazione servizio WCF**.  
  
4.  In **Nome** immettere `TestService` e fare clic su **OK**.  
  
5.  Fare clic con il pulsante destro del mouse sul progetto **TestService** in **Esplora soluzioni** e quindi selezionare **Identity and Access**.  
  
6.  Verrà visualizzata la finestra **Identity and Access**. In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**. Lo strumento Identity and Access configura il servizio per l'uso di WIF e per l'outsourcing dell'autenticazione al servizio token di sicurezza per lo sviluppo locale (**LocalSTS**) aggiungendo elementi di configurazione al file *Web.config*.  
  
7.  Nel file *Service1.svc.cs* aggiungere una direttiva `using` per lo spazio dei nomi **System.Security.Claims** e sostituire il codice esistente con il seguente, quindi salvare il file:  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     Il metodo `ComputeResponse` visualizza le proprietà di varie attestazioni che sono pubblicate da **LocalSTS**.  
  
8.  Nel file *IService1.cs* sostituire il codice esistente con il seguente, quindi salvare il file:  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. Compilare il progetto.  
  
10. Premere **CTRL+F5** per eseguire il servizio senza avviare il debugger. Verrà visualizzata una pagina Web per il servizio nella quale è possibile verificare che **LocalSTS** sia in esecuzione esaminando l'area di notifica (barra delle applicazioni).  
  
    > [!IMPORTANT]
    >  Sia **TestService** sia **LocalSTS** devono essere in esecuzione quando viene aggiunto il riferimento del servizio all'applicazione client nel passaggio successivo.  
  
## <a name="step-2--create-a-client-application-for-the-wcf-service"></a>Passaggio 2: creare un'applicazione client per il servizio WCF  
 In questo passaggio, verrà creata un'applicazione console che utilizza il servizio STS di sviluppo per l'autenticazione con il servizio WCF creato nel passaggio precedente.  
  
#### <a name="to-create-a-client-application"></a>Per creare un'applicazione client  
  
1.  In Visual Studio fare clic con il pulsante destro del mouse sulla soluzione, scegliere **Aggiungi** e quindi fare clic su **Nuovo progetto**.  
  
2.  Nella finestra **Aggiungi nuovo progetto** selezionare **Applicazione console** nell'elenco dei modelli di **Visual C#**, immettere `Client` e quindi scegliere **OK**. Il nuovo progetto verrà creato nella cartella della soluzione.  
  
3.  Fare clic con il pulsante destro del mouse su **Riferimenti** nel progetto **Client** e quindi scegliere **Aggiungi riferimento al servizio**.  
  
4.  Nella finestra **Aggiungi riferimento al servizio** fare clic sulla freccia a discesa sul pulsante **Individua** e fare clic su **Servizi nella soluzione**. Nel campo **Indirizzo** verrà automaticamente inserito il servizio WCF precedentemente creato e il campo **Spazio dei nomi** verrà impostato su **ServiceReference1**. Fare clic su **OK**.  
  
    > [!IMPORTANT]
    >  Sia **TestService** sia **LocalSTS** devono essere in esecuzione quando viene aggiunto il riferimento del servizio al client.  
  
5.  In Visual Studio verranno generate classi proxy per il servizio WCF e verranno aggiunte tutte le informazioni di riferimento necessarie. Verranno inoltre aggiunti elementi al file *App.config* per configurare il client in modo da ottenere un token dal servizio token di sicurezza per l'autenticazione con il servizio. Al termine di questo processo verrà aperto il file **Program.cs**. Aggiungere una direttiva `using` per **System.ServiceModel** e un'altra per **Client.ServiceReference1**, sostituire il metodo **Main** con il codice seguente e quindi salvare il file:  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6.  Aprire il file *App.config* e aggiungere il seguente codice XML come primo elemento figlio sotto l'elemento `<system.serviceModel>`, quindi salvare il file:  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
    ```  
  
     In questo modo viene disabilitata la convalida del certificato.  
  
7.  Fare clic con il pulsante destro del mouse sulla soluzione **TestService** e fare clic su **Imposta progetti di avvio**. Verrà aperta la pagina delle proprietà **Progetto di avvio**. Nella pagina delle proprietà **Progetto di avvio** selezionare **Progetti di avvio multipli** e quindi fare clic sul campo **Azione** per ciascun progetto e scegliere **Avvio** dal menu a discesa. Fare clic su **OK** per salvare le impostazioni.  
  
8.  Compilare la soluzione.  
  
## <a name="step-3--test-your-solution"></a>Passaggio 3: eseguire i test sulla soluzione  
 In questo passaggio verrà eseguito il test dell'applicazione WCF abilitata per WIF e verrà verificata la visualizzazione delle attestazioni.  
  
#### <a name="to-test-your-wif-enabled-wcf-application-for-claims"></a>Per eseguire il test sulle attestazioni dell'applicazione WCF abilitata per WIF  
  
1.  Premere **F5** per compilare ed eseguire l'applicazione. Verranno visualizzati una finestra della console e il testo seguente: **Premere INVIO per richiamare il servizio e qualsiasi altro tasto per chiudere l'applicazione:**  
  
2.  Premere **INVIO**. Verranno visualizzate le seguenti informazioni sulle attestazioni nella console:  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  Sia **TestService** che **LocalSTS** devono essere in esecuzione prima di premere **INVIO**. Verrà visualizzata una pagina Web per il servizio nella quale è possibile verificare che **LocalSTS** sia in esecuzione esaminando l'area di notifica (barra delle applicazioni).  
  
3.  La visualizzazione delle attestazioni nella console è la prova dell'avvenuta autenticazione con il servizio STS per la visualizzazione delle attestazioni dal servizio WCF.

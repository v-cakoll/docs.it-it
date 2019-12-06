---
title: Esempio di federazione
ms.date: 03/30/2017
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
ms.openlocfilehash: c143ad9315df94a2d836a2c2c742ffa9a7728511
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837883"
---
# <a name="federation-sample"></a>Esempio di federazione
Nell'esempio viene illustrata la sicurezza federata.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Windows Communication Foundation (WCF) fornisce il supporto per la distribuzione di architetture di sicurezza federata tramite l'`wsFederationHttpBinding`. L'elemento `wsFederationHttpBinding` offre un'associazione sicura, affidabile e interoperativa che comporta l'utilizzo di HTTP come meccanismo di trasporto sottostante per la comunicazione request/reply e Text/XML come formato di trasmissione per la codifica. Per ulteriori informazioni sulla Federazione in WCF, vedere [Federazione](../../../../docs/framework/wcf/feature-details/federation.md).  
  
 Lo scenario è costituito da 4 elementi:  
  
- Servizio della libreria  
  
- Servizio token di protezione della libreria  
  
- Servizio token di protezione HomeRealm  
  
- Client della libreria  
  
 Il servizio della libreria supporta due operazioni, `BrowseBooks` e `BuyBook`. Consente accesso anonimo all'operazione `BrowseBooks`, ma richiede accesso autenticato per l'operazione `BuyBooks`. L'autenticazione prende il form di un token pubblicato dal Servizio token di sicurezza della libreria. Il file di configurazione per Servizio della Libreria punta i client al Servizio token di protezione della libreria utilizzando l'`wsFederationHttpBinding`.  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 Il servizio token di protezione della libreria richiede quindi che i client si autentichino utilizzando un token pubblicato dal servizio token di protezione HomeRealm. Anche in questo caso, il file di configurazione per il servizio token di protezione della libreria punta i client al servizio token di protezione HomeRealm utilizzando `wsFederationHttpBinding`.  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 La sequenza di eventi quando si accede all'operazione `BuyBook` è la seguente:  
  
1. Il client effettua l'accesso al servizio token di sicurezza HomeRealm utilizzando le credenziali di Windows.  
  
2. Il servizio token di protezione HomeRealm pubblica un token che può essere utilizzato per accedere al servizio token di protezione della libreria.  
  
3. Il client accede al servizio token di protezione della libreria utilizzando il token pubblicato dal servizio token di protezione HomeRealm.  
  
4. Il servizio token di protezione della libreria pubblica un token che può essere utilizzato per accedere al servizio della libreria.  
  
5. Il client accede a al servizio della libreria utilizzando il token pubblicato dal servizio token di sicurezza della libreria.  
  
6. Il client accede all'operazione `BuyBook`.  
  
 Vedere le istruzioni seguenti su come impostare ed eseguire l'esempio.  
  
> [!NOTE]
> Per eseguire l'esempio, è necessario disporre delle autorizzazioni di scrittura per la directory **wwwroot** .  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Aprire la finestra del prompt dei comandi SDK. Nel percorso di esempio, eseguire Setup.bat. Ciò crea le directory virtuali richieste per l'esempio e installa i certificati obbligatori con le autorizzazioni adeguate.  
  
    > [!NOTE]
    > Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di SDK di Windows. e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK. Questa variabile di ambiente viene impostata automaticamente all'interno di un prompt dei comandi di SDK di Windows. In Windows Vista, è necessario assicurarsi che sia installata la compatibilità di gestione con IIS 6,0 perché la configurazione utilizza gli script di amministratore di IIS. Per eseguire lo script di configurazione in Windows Vista sono necessari i privilegi di amministratore.  
  
2. Aprire FederationSample. sln in Visual Studio e scegliere **Compila soluzione** dal menu **Compila** . Compila i file di progetto comuni, il servizio della libreria, gli STS della libreria, gli STS di HomeRealm e li distribuisce in IIS. Compila anche l'applicazione client della libreria e posiziona il file eseguibile BookStoreClient.exe nella cartella FederationSample\BookStoreClient\bin\Debug.  
  
3. Fare doppio clic su BookStoreClient.exe. Verrà visualizzata la finestra BookStoreClient.  
  
4. È possibile esplorare i libri disponibili nella libreria facendo clic su **Sfoglia libri**.  
  
5. Per acquistare un libro specifico, selezionare il libro nell'elenco e fare clic su **Acquista libro**. L'applicazione si avvia e effettua l'autenticazione utilizzando l'autenticazione di Windows con il servizio token di protezione HomeRealm.  
  
     L'esempio è configurato per consentire agli utenti di acquistare libri che costano 15$ o meno. Il tentativo di acquistare volumi che costano più di 15$ comporta il ricevimento da parte del client di un messaggio Accesso negato dal servizio della libreria.  
  
    > [!NOTE]
    > L'esempio non aggiorna il limite di credito dell'utente dopo un acquisto. È possibile acquistare ripetutamente libri entro i limiti di credito (fissi) dell'utente.  
  
#### <a name="to-clean-up"></a>Per eseguire la pulizia  
  
1. Eseguire Cleanup.bat. Ciò consente di eliminare le directory virtuali create durante l'installazione e di rimuovere inoltre i certificati installati durante l'installazione.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  

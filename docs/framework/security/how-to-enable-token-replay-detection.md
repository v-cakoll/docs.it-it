---
title: 'Procedura: Abilitare il rilevamento della riproduzione del token'
ms.date: 03/30/2017
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b9c187998b4af41e1a56ed9a64625da7e4f95d5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-token-replay-detection"></a>Procedura: Abilitare il rilevamento della riproduzione del token
## <a name="applies-to"></a>Si applica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Web Form ASP.NET®  
  
## <a name="summary"></a>Riepilogo  
 Questo argomento include le procedure dettagliate per abilitare il rilevamento riproduzione del token in un'applicazione ASP.NET che usa WIF. Sono inoltre disponibili istruzioni su come testare l'applicazione per verificare che il rilevamento riproduzione del token sia abilitato. In questa guida procedurale non sono incluse le istruzioni dettagliate per la creazione di un servizio token di sicurezza (STS, Security Token Service); viene invece utilizzato il servizio token di sicurezza di sviluppo che viene fornito con lo strumento Identity and Access. Il servizio token di sicurezza di sviluppo non esegue una reale autenticazione ed è finalizzato unicamente ai test. Per completare questa guida procedurale sarà necessario installare Identity and Access Tool. Questo strumento può essere scaricato dal seguente percorso: [Identity and Access Tool](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
## <a name="contents"></a>Sommario  
  
-   Obiettivi  
  
-   Panoramica  
  
-   Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare il rilevamento riproduzione  
  
-   Passaggio 2: eseguire i test sulla soluzione  
  
## <a name="objectives"></a>Obiettivi  
  
-   Creare un'applicazione ASP.NET semplice che usa WIF e il servizio token di sicurezza per lo sviluppo locale dallo strumento Identity and Access  
  
-   Abilitare il rilevamento riproduzione del token e verificare che funzioni  
  
## <a name="overview"></a>Panoramica  
 Un attacco di tipo replay si verifica quando un client tenta di eseguire l'autenticazione per una relying party con un token del servizio token di sicurezza già usato dal client. Per prevenire questo tipo di attacco, WIF contiene una cache di rilevamento riproduzione dei token del servizio token di sicurezza usati in precedenza. Quando è abilitato, il rilevamento riproduzione controlla il token della richiesta in arrivo e verifica se il token è stato usato o meno in precedenza. Se il token è già stato usato, la richiesta viene rifiutata e viene generata un'eccezione <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException>.  
  
 I passaggi seguenti illustrano le modifiche di configurazione necessarie per abilitare il rilevamento riproduzione.  
  
## <a name="summary-of-steps"></a>Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare il rilevamento riproduzione  
  
-   Passaggio 2: eseguire i test sulla soluzione  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-replay-detection"></a>Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare il rilevamento riproduzione  
 In questo passaggio verrà creata una nuova applicazione Web Form ASP.NET e si modificherà il file *Web.config* per abilitare il rilevamento riproduzione.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Per creare un'applicazione ASP.NET semplice  
  
1.  Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.  
  
2.  Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.  
  
3.  In **Nome** immettere `TestApp` e fare clic su **OK**.  
  
4.  Fare clic con il pulsante destro del mouse sul progetto **TestApp** in **Esplora soluzioni** e quindi scegliere **Identity and Access**.  
  
5.  Verrà visualizzata la finestra **Identity and Access**. In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**.  
  
6.  Aggiungere l'elemento **\<tokenReplayDetection>** seguente al file di configurazione *Web.config* subito dopo gli elementi **\<system.identityModel>** e **\<identityConfiguration>**, come illustrato:  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled="true"/>  
    ```  
  
## <a name="step-2--test-your-solution"></a>Passaggio 2: eseguire i test sulla soluzione  
 In questo passaggio si testerà l'applicazione ASP.NET abilitata per WIF per verificare che il rilevamento riproduzione sia stato abilitato.  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-replay-detection"></a>Per testare il corretto funzionamento del rilevamento riproduzione per l'applicazione ASP.NET abilitata per WIF  
  
1.  Eseguire la soluzione premendo **F5**. Dovrebbe essere visualizzata la home page predefinita di ASP.NET e l'autenticazione dovrebbe avvenire automaticamente con il nome utente *Terry*, ovvero l'utente predefinito restituito dal servizio token di sicurezza per lo sviluppo.  
  
2.  Premere il pulsante **Indietro** del browser. Dovrebbe essere visualizzata un pagina **Errore del server nell'applicazione '/'** con la descrizione seguente: *ID1062: Rilevata riproduzione per: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, seguita da *AssertionId* e *Autorità di certificazione*.  
  
     Questa pagina di errore viene visualizzata perché è stata generata un'eccezione di tipo <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> al rilevamento della riproduzione token. Questo errore si verifica perché si sta tentando di inviare nuovamente la richiesta POST iniziale della prima presentazione del token. Il pulsante **Indietro** non causerà questo comportamento nelle richieste successive al server.

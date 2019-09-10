---
title: 'Procedura: Visualizzare lo stato di accesso effettuato con WIF'
ms.date: 03/30/2017
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
author: BrucePerlerMS
ms.openlocfilehash: d2500c6ded485fca76715425b9a52258e07be08d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851549"
---
# <a name="how-to-display-signed-in-status-using-wif"></a>Procedura: Visualizzare lo stato di accesso effettuato con WIF
## <a name="applies-to"></a>Si applica a  
  
- Microsoft® Windows® Identity Foundation (WIF) 4.5  
  
- Web Form ASP.NET®  
  
## <a name="summary"></a>Riepilogo  
 Questo argomento descrive come visualizzare lo stato di accesso in un'applicazione ASP.NET abilitata per WIF. WIF fornisce il meccanismo per rendere un'applicazione in grado di riconoscere attestazioni e per gestire autenticazione e autorizzazione per le risorse dell'applicazione.  
  
## <a name="contents"></a>Sommario  
  
- Panoramica  
  
- Riepilogo dei passaggi  
  
- Passaggio 1: installare l'estensione Identity and Access  
  
- Passaggio 2: creare un'applicazione ASP.NET relying party  
  
- Passaggio 3: abilitare il servizio token di sicurezza per lo sviluppo locale per autenticare gli utenti  
  
- Passaggio 4: modificare l'applicazione ASP.NET per visualizzare lo stato di accesso  
  
- Passaggio 5: testare l'integrazione tra WIF e l'applicazione ASP.NET  
  
## <a name="overview"></a>Panoramica  
 Questo argomento dimostra come creare una semplice applicazione in grado di riconoscere attestazioni mediante WIF e come visualizzare facilmente se un utente è connesso o meno. La procedura seguente usa il servizio token di sicurezza per lo sviluppo locale incluso nell'estensione di Visual Studio Identity and Access. Il servizio token di sicurezza per lo sviluppo locale è destinato a un ambiente di sviluppo e test per fornire un metodo semplice per l'integrazione delle attestazioni nelle applicazioni. Non deve mai essere usato in ambiente di produzione, perché non esegue effettivamente l'autenticazione e non sono richieste credenziali. Tuttavia, il codice imperativo nei passaggi seguenti è lo stesso per un'applicazione utilizzabile in produzione con i meccanismi di autenticazione effettivi.  
  
## <a name="summary-of-steps"></a>Riepilogo dei passaggi  
  
- Passaggio 1: installare l'estensione Identity and Access  
  
- Passaggio 2: creare un'applicazione ASP.NET relying party  
  
- Passaggio 3: abilitare il servizio token di sicurezza per lo sviluppo locale per autenticare gli utenti  
  
- Passaggio 4: modificare l'applicazione ASP.NET per visualizzare lo stato di accesso  
  
- Passaggio 5: testare l'integrazione tra WIF e l'applicazione ASP.NET  
  
## <a name="step-1--install-the-identity-and-access-extension"></a>Passaggio 1: installare l'estensione Identity and Access  
 Questo passaggio descrive come configurare l'estensione Identity and Access in Visual Studio 2012. Questa estensione consente di automatizzare il processo di configurazione dell'applicazione per comunicare con gli endpoint del servizio token di sicurezza.  
  
### <a name="to-install-the-identity-and-access-extension"></a>Per installare l'estensione Identity and Access  
  
1. Avviare Visual Studio come amministratore in modalità con privilegi elevati.  
  
2. In Visual Studio fare clic su **Strumenti** e quindi su **Gestione estensioni**. Verrà visualizzata la finestra **Gestione estensioni**.  
  
3. In **Gestione estensioni** fare clic su **Estensioni online** nel menu a sinistra e quindi selezionare **Visual Studio Gallery**.  
  
4. Nell'angolo superiore destro di **Gestione estensioni** cercare *Identity and Access*.  
  
5. L'elemento **Identity and Access** verrà visualizzato nei risultati della ricerca. Fare clic su di esso e quindi su **Scarica**.  
  
6. Verrà visualizzata la finestra di dialogo **Scarica e installa** . Se si accettano le condizioni di licenza, fare clic su **Installa**.  
  
7. Al termine dell'installazione dell'estensione **Identity and Access**, riavviare Visual Studio in modalità amministratore.  
  
## <a name="step-2--create-a-relying-party-aspnet-application"></a>Passaggio 2: creare un'applicazione ASP.NET relying party  
 Questo passaggio descrive come creare un'applicazione Web Form ASP.NET relying party che verrà integrata con WIF.  
  
### <a name="to-create-a-simple-aspnet-application"></a>Per creare un'applicazione ASP.NET semplice  
  
1. Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.  
  
2. Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.  
  
3. In **Nome** immettere `TestApp` e fare clic su **OK**.  
  
## <a name="step-3--enable-local-development-sts-to-authenticate-users"></a>Passaggio 3: abilitare il servizio token di sicurezza per lo sviluppo locale per autenticare gli utenti  
 Questo passaggio descrive come abilitare il servizio token di sicurezza per lo sviluppo locale nell'applicazione. Il servizio token di sicurezza per lo sviluppo locale viene abilitato tramite l'estensione Identity and Access per Visual Studio.  
  
### <a name="to-enable-local-development-sts-in-your-aspnet-application"></a>Per abilitare il servizio token di sicurezza per lo sviluppo locale nell'applicazione ASP.NET  
  
1. In Visual Studio fare clic con il pulsante destro del mouse sul progetto **TestApp** in **Esplora soluzioni** e quindi scegliere **Identity and Access**.  
  
2. Verrà visualizzata la finestra **Identity and Access**. In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**.  
  
## <a name="step-4--modify-your-aspnet-application-to-display-sign-in-status"></a>Passaggio 4: modificare l'applicazione ASP.NET per visualizzare lo stato di accesso  
 Questo passaggio descrive come modificare l'applicazione ASP.NET per visualizzare in modo dinamico se l'utente corrente ha effettuato l'accesso. Una volta configurato il provider del servizio token di sicurezza, WIF gestisce le attestazioni in ingresso. È ora necessario configurare il codice dell'applicazione per visualizzare il risultato dell'autenticazione.  
  
### <a name="to-display-sign-in-status"></a>Per visualizzare lo stato di accesso  
  
1. In Visual Studio aprire il file **Default.aspx** nel progetto **TestApp**.  
  
2. Sostituire il markup esistente nel file **Default.aspx** con il seguente:  
  
    ```aspx-csharp  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3. Salvare **Default.aspx** e quindi aprire il file code-behind denominato **Default.aspx.cs**.  
  
    > [!NOTE]
    > Il file **Default.aspx.cs** potrebbe essere nascosto sotto **Default.aspx** in Esplora soluzioni. Se **Default.aspx.cs** non è visibile, espandere **Default.aspx** facendo clic sul triangolo accanto.  
  
4. Sostituire il codice esistente nel file **Default.aspx.cs** con il seguente:  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5. Salvare **Default.aspx.cs** e compilare l'applicazione.  
  
## <a name="step-5--test-the-integration-between-wif-and-your-aspnet-application"></a>Passaggio 5: testare l'integrazione tra WIF e l'applicazione ASP.NET  
 Questo passaggio descrive la procedura per testare l'integrazione tra WIF e l'applicazione ASP.NET.  
  
### <a name="to-test-the-integration-between-wif-and-aspnet"></a>Per testare l'integrazione tra WIF e ASP.NET  
  
1. In Visual Studio premere **F5** per avviare il debug dell'applicazione. Se non vengono rilevati errori, verrà aperta una nuova finestra del browser.  
  
2. Si può notare che il browser reindirizza automaticamente la richiesta al servizio token di sicurezza e quindi apre la pagina Default.aspx. Se WIF è configurato correttamente, il sito visualizzerà il testo seguente: **"È stato eseguito l'accesso"** .

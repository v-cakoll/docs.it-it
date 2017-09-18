---
title: 'Procedura: Compilare un''applicazione ASP.NET in grado di riconoscere attestazioni con l''autenticazione basata su moduli'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
caps.latest.revision: 6
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 987157bc3663330d9c610c1016787890e9dc6137
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a>Procedura: Compilare un'applicazione ASP.NET in grado di riconoscere attestazioni con l'autenticazione basata su moduli
## <a name="applies-to"></a>Si applica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Web Form ASP.NET®  
  
## <a name="summary"></a>Riepilogo  
 Questo argomento include le procedure dettagliate per creare un'applicazione Web Form ASP.NET semplice, in grado di riconoscere attestazioni, che usa l'autenticazione basata su form. Sono inoltre disponibili istruzioni per testare l'applicazione al fine di assicurarsi che le attestazioni vengano presentate quando un utente accede con l'autenticazione basata su form.  
  
## <a name="contents"></a>Sommario  
  
-   Obiettivi  
  
-   Panoramica  
  
-   Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
  
-   Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione basata su form  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="objectives"></a>Obiettivi  
  
-   Configurare un'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione basata su form  
  
-   Testare l'applicazione Web Form ASP.NET per verificare se funziona correttamente  
  
## <a name="overview"></a>Panoramica  
 In .NET 4.5, WIF e l'autorizzazione basata sulle attestazioni sono diventati parte integrante del framework. In precedenza, per usare le attestazioni da un utente ASP.NET, era necessario installare WIF e quindi effettuare il cast delle interfacce su oggetti Principal come `Thread.CurrentPrincipal` o `HttpContext.Current.User`. Ora le attestazioni vengono gestite automaticamente da questi oggetti Principal.  
  
 L'autenticazione basata su form ha tratto vantaggio dall'inclusione di WIF in .NET 4.5, perché a tutti gli utenti autenticati con credenziali basate su form vengono associate automaticamente le attestazioni. È possibile iniziare subito a usare queste attestazioni in un'applicazione ASP.NET che usa l'autenticazione basata su form, come illustrato di seguito in questa procedura.  
  
## <a name="summary-of-steps"></a>Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
  
-   Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione basata su form  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
 In questo passaggio si creerà una nuova applicazione Web Form ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Per creare un'applicazione ASP.NET semplice  
  
1.  Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.  
  
2.  Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.  
  
3.  In **Nome** immettere `TestApp` e fare clic su **OK**.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione basata su form  
 In questo passaggio si aggiungerà una voce al file di configurazione *Web.config* e si modificherà il file *Default.aspx* per visualizzare le informazioni sulle attestazioni per un account.  
  
#### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a>Per configurare l'applicazione ASP.NET per le attestazioni usando l'autenticazione basata su form  
  
1.  Nel file *Default.aspx* sostituire il markup esistente con il seguente:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Forms authenticated user.          
        </p>  
        <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
     Questo passaggio aggiunge alla pagina *Default.aspx* un controllo GridView che verrà popolato con le attestazioni recuperate dall'autenticazione basata su form.  
  
2.  Salvare il file *Default.aspx* e quindi aprire il relativo file code-behind denominato *Default.aspx.cs*. Sostituire il codice esistente con quello seguente:  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        public partial class _Default : Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                    this.ClaimsGridView.DataBind();  
                }  
            }  
        }  
    }  
    ```  
  
     Il codice sopra riportato visualizzerà le attestazioni relative a un utente autenticato, inclusi gli utenti identificati dall'autenticazione basata su form.  
  
## <a name="step-3--test-your-solution"></a>Passaggio 3: eseguire i test sulla soluzione  
 In questo passaggio verrà testata l'applicazione Web Form ASP.NET e si verificherà che le attestazioni vengano presentate quando un utente accede con l'autenticazione basata su form.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Per testare le attestazioni con l'applicazione Web Form ASP.NET usando l'autenticazione basata su form  
  
1.  Premere **F5** per compilare ed eseguire l'applicazione. Verrà visualizzata la pagina *Default.aspx*, con i collegamenti **Register** e **Log in** nella parte superiore destra. Fare clic su **Register**.  
  
2.  Nella pagina **Register** creare un account utente e quindi fare clic su **Register**. L'account verrà creato usando l'autenticazione basata su form e l'utente verrà automaticamente connesso.  
  
3.  Dopo il reindirizzamento alla home page, sotto il titolo **Your Claims** dovrebbe essere visualizzata una tabella che include le informazioni sulle attestazioni **Issuer**, **OriginalIssuer**, **Type**, **Value** e **ValueType** per l'account usato.


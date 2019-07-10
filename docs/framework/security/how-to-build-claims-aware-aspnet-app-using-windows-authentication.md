---
title: "Procedura: Compilare un'applicazione ASP.NET che può riconoscere attestazioni con l'autenticazione di Windows"
ms.date: 03/30/2017
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
author: BrucePerlerMS
ms.openlocfilehash: 9b58a4066538441a48bc6646f364e846a25cc8c8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742507"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a>Procedura: Compilare un'applicazione ASP.NET che può riconoscere attestazioni con l'autenticazione di Windows
## <a name="applies-to"></a>Si applica a  
  
- Microsoft® Windows® Identity Foundation (WIF)  
  
- Web Form ASP.NET®  
  
## <a name="summary"></a>Riepilogo  
 Questo argomento include le procedure dettagliate per creare una semplice applicazione Web Form ASP.NET in grado di riconoscere attestazioni che usa l'autenticazione di Windows. Sono inoltre disponibili istruzioni per testare l'applicazione per assicurarsi che le attestazioni vengano presentate quando un utente accede con l'autenticazione di Windows.  
  
## <a name="contents"></a>Sommario  
  
- Obiettivi  
  
- Panoramica  
  
- Riepilogo dei passaggi  
  
- Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
  
- Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione di Windows  
  
- Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="objectives"></a>Obiettivi  
  
- Configurare un'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione di Windows  
  
- Testare l'applicazione Web Form ASP.NET per verificare se funziona correttamente  
  
## <a name="overview"></a>Panoramica  
 In .NET 4.5, WIF e l'autorizzazione basata sulle attestazioni sono diventati parte integrante del framework. In precedenza, per usare le attestazioni da un utente ASP.NET, era necessario installare WIF e quindi effettuare il cast delle interfacce su oggetti Principal come `Thread.CurrentPrincipal` o `HttpContext.Current.User`. Ora le attestazioni vengono gestite automaticamente da questi oggetti Principal.  
  
 L'autenticazione di Windows ha tratto vantaggio dall'inclusione di WIF in .NET 4.5, perché a tutti gli utenti autenticati con credenziali di Windows vengono associate automaticamente le attestazioni. È possibile iniziare subito a usare queste attestazioni in un'applicazione ASP.NET che usa l'autenticazione di Windows, come illustrato di seguito in questa procedura.  
  
## <a name="summary-of-steps"></a>Riepilogo dei passaggi  
  
- Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
  
- Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione di Windows  
  
- Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
 In questo passaggio si creerà una nuova applicazione Web Form ASP.NET.  
  
### <a name="to-create-a-simple-aspnet-application"></a>Per creare un'applicazione ASP.NET semplice  
  
1. Avviare Visual Studio e quindi fare clic su **File**, **Nuovo** e **Progetto**.  
  
2. Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.  
  
3. In **Nome** immettere `TestApp` e fare clic su **OK**.  
  
4. Dopo la creazione del progetto **TestApp** fare clic su di esso in **Esplora soluzioni**. Le proprietà del progetto verranno visualizzate nel riquadro **Proprietà** sotto a **Esplora soluzioni**. Impostare la proprietà **Autenticazione di Windows** su **Abilitata**.  
  
    > [!WARNING]
    >  L'autenticazione di Windows è disabilitata per impostazione predefinita nelle nuove applicazioni ASP.NET, pertanto è necessario abilitarla manualmente.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a>Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione di Windows  
 In questo passaggio si aggiungerà una voce di configurazione al file di configurazione *Web.config* e si modificherà il file *Default.aspx* per visualizzare informazioni sulle attestazioni per un account.  
  
### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a>Per configurare l'applicazione ASP.NET per le attestazioni usando l'autenticazione di Windows  
  
1. Nel file *Default.aspx* del progetto **TestApp** sostituire il markup esistente con il seguente:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Windows authenticated user.          
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
  
     Questo passaggio aggiunge un controllo GridView alla pagina *Default.aspx* che verrà popolato con le attestazioni recuperate dall'autenticazione di Windows.  
  
2. Salvare il file *Default.aspx* e quindi aprire il relativo file code-behind denominato *Default.aspx.cs*. Sostituire il codice esistente con quello seguente:  
  
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
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
     Il codice sopra riportato visualizzerà le attestazioni relative a un utente autenticato.  
  
3. Per modificare il tipo di autenticazione dell'applicazione, modificare il blocco **\<authentication>** nella sezione **\<system.web>** del file *Web.config* radice del progetto in modo che includa solo la voce di configurazione seguente:  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4. Modificare infine il blocco **\<authorization>** nella sezione **\<system.web>** dello stesso file *Web.config* per forzare l'autenticazione:  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a>Passaggio 3: eseguire i test sulla soluzione  
 In questo passaggio verrà testata l'applicazione Web Form ASP.NET e si verificherà che le attestazioni vengano presentate quando un utente accede con l'autenticazione di Windows.  
  
### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a>Per testare le attestazioni con l'applicazione Web Form ASP.NET usando l'autenticazione di Windows  
  
1. Premere **F5** per compilare ed eseguire l'applicazione. Verrà visualizzato il file *Default.aspx* e il nome dell'account Windows personale (incluso il nome di dominio) dovrebbe già essere visualizzato come utente autenticato in alto a destra nella pagina. Il contenuto della pagina deve includere una tabella con le attestazioni recuperate dall'account di Windows.

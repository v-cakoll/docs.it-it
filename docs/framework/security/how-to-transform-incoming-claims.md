---
title: 'Procedura: Trasformare le attestazioni in ingresso'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
caps.latest.revision: 4
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bcf0e640e6b6b45ddb87070c7d6df2fa6dadc834
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-transform-incoming-claims"></a>Procedura: Trasformare le attestazioni in ingresso
## <a name="applies-to"></a>Si applica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Web Form ASP.NET®  
  
## <a name="summary"></a>Riepilogo  
 Questo argomento include le procedure dettagliate per creare una semplice applicazione Web Form ASP.NET in grado di riconoscere attestazioni e trasformare le attestazioni in ingresso. Sono inoltre disponibili istruzioni su come testare l'applicazione per verificare che le attestazioni trasformate vengano presentate quando l'applicazione viene eseguita.  
  
## <a name="contents"></a>Sommario  
  
-   Obiettivi  
  
-   Panoramica  
  
-   Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
  
-   Passaggio 2: implementare la trasformazione delle attestazioni con un ClaimsAuthenticationManager personalizzato  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="objectives"></a>Obiettivi  
  
-   Configurare un'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni  
  
-   Trasformare le attestazioni in ingresso tramite l'aggiunta di un'attestazione per il ruolo di amministratore  
  
-   Testare l'applicazione Web Form ASP.NET per verificare se funziona correttamente  
  
## <a name="overview"></a>Panoramica  
 WIF espone una classe denominata <xref:System.Security.Claims.ClaimsAuthenticationManager> che consente agli utenti di modificare le attestazioni prima che vengano presentate a un'applicazione relying party. La classe <xref:System.Security.Claims.ClaimsAuthenticationManager> è utile per la separazione dei compiti tra l'autenticazione e il codice dell'applicazione sottostante. L'esempio seguente dimostra come aggiungere un ruolo alle attestazioni nel <xref:System.Security.Claims.ClaimsPrincipal> in ingresso che potrebbe essere richiesto dalla relying party.  
  
## <a name="summary-of-steps"></a>Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
  
-   Passaggio 2: implementare la trasformazione delle attestazioni con un ClaimsAuthenticationManager personalizzato  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
 In questo passaggio si creerà una nuova applicazione Web Form ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Per creare un'applicazione ASP.NET semplice  
  
1.  Avviare Visual Studio come amministratore in modalità con privilegi elevati.  
  
2.  In Visual Studio fare clic su **File**, **Nuovo** e quindi su **Progetto**.  
  
3.  Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.  
  
4.  In **Nome** immettere `TestApp` e fare clic su **OK**.  
  
5.  Fare clic con il pulsante destro del mouse sul progetto **TestApp** in **Esplora soluzioni** e quindi scegliere **Identity and Access**.  
  
6.  Verrà visualizzata la finestra **Identity and Access**. In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**.  
  
7.  Nel file *Default.aspx* sostituire il markup esistente con il seguente e quindi salvare il file:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
          <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
8.  Aprire il file code-behind denominato *Default.aspx.cs*. Sostituire il codice esistente con il seguente e quindi salvare il file:  
  
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
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a>Passaggio 2: implementare la trasformazione delle attestazioni con un ClaimsAuthenticationManager personalizzato  
 In questo passaggio si eseguirà l'override di funzionalità predefinite nella classe <xref:System.Security.Claims.ClaimsAuthenticationManager> per aggiungere un ruolo di amministratore per l'entità di sicurezza in ingresso.  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a>Per implementare la trasformazione delle attestazioni con un ClaimsAuthenticationManager personalizzato  
  
1.  In Visual Studio fare clic con il pulsante destro del mouse sulla soluzione, scegliere **Aggiungi** e quindi fare clic su **Nuovo progetto**.  
  
2.  Nella finestra **Aggiungi nuovo progetto** selezionare **Libreria di classi** nell'elenco dei modelli di **Visual C#**, immettere `ClaimsTransformation` e quindi scegliere **OK**. Il nuovo progetto verrà creato nella cartella della soluzione.  
  
3.  Fare clic con il pulsante destro del mouse su **Riferimenti** nel progetto **ClaimsTransformation** e quindi scegliere **Aggiungi riferimento**.  
  
4.  Nella finestra **Gestione riferimenti** selezionare **System.IdentityModel** e quindi fare clic su **OK**.  
  
5.  Aprire **Class1.cs** oppure, se non esiste, fare clic con il pulsante destro del mouse su **ClaimsTransformation**, scegliere **Aggiungi** e quindi fare clic su **Classe**.  
  
6.  Aggiungere le direttive using seguenti al file di codice:  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  Aggiungere la classe e il metodo seguenti nel file di codice.  
  
    > [!WARNING]
    >  Il codice seguente è solo a scopo dimostrativo. Assicurarsi di verificare le autorizzazioni previste nel codice di produzione.  
  
    ```csharp  
    public class ClaimsTransformationModule : ClaimsAuthenticationManager  
    {  
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)  
        {  
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)  
            {  
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));  
            }  
  
            return incomingPrincipal;  
        }  
    }  
    ```  
  
8.  Salvare il file e compilare il progetto **ClaimsTransformation**.  
  
9. Nel progetto ASP.NET **TestApp** fare clic con il pulsante destro del mouse su Riferimenti e quindi scegliere **Aggiungi riferimento**.  
  
10. Nella finestra **Gestione riferimenti** selezionare **Soluzione** nel menu a sinistra, selezionare **ClaimsTransformation** tra le opzioni compilate e quindi fare clic su **OK**.  
  
11. Nel file **Web.config** radice passare alla voce **\<system.identityModel>**. Aggiungere la riga seguente negli elementi  **\<identityConfiguration >** e salvare il file:  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a>Passaggio 3: eseguire i test sulla soluzione  
 In questo passaggio verrà testata l'applicazione Web Form ASP.NET e si verificherà che le attestazioni vengano presentate quando un utente accede con l'autenticazione basata su form.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Per testare le attestazioni con l'applicazione Web Form ASP.NET usando l'autenticazione basata su form  
  
1.  Premere **F5** per compilare ed eseguire l'applicazione. Dovrebbe essere visualizzato il file *Default.aspx*.  
  
2.  Nella pagina *Default.aspx* dovrebbe essere visualizzata una tabella sotto il titolo **Your Claims** che include le informazioni sulle attestazioni **Issuer**, **OriginalIssuer**, **Type**, **Value** e **ValueType** per l'account usato. L'ultima riga dovrebbe essere come la seguente:  
  
    ||||||  
    |-|-|-|-|-|  
    |LOCAL AUTHORITY|LOCAL AUTHORITY|http://schemas.microsoft.com/ws/2008/06/identity/claims/role|Amministrazione|http://www.w3.org/2001/XMLSchema#string|


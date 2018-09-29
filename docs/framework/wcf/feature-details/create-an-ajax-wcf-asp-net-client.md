---
title: Creare un servizio WCF compatibile con AJAX e un Client ASP.NET in Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 954ee0409f370c3fa28814a70d51334fd75f7b79
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2018
ms.locfileid: "47454315"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>Procedura: creare un servizio WCF compatibile con AJAX e un client ASP.NET che accede al servizio

In questo argomento viene illustrato come usare Visual Studio per creare un servizio compatibile con AJAX Windows Communication Foundation (WCF) e un client ASP.NET che accede al servizio.

## <a name="create-an-aspnet-web-app"></a>Creare un'app Web ASP.NET

1. Aprire Visual Studio.

1. Dal **File** dal menu **New** > **progetto**

1. Nel **nuovo progetto** finestra di dialogo espandere il **installati** > **Visual c#** > **Web** categoria e quindi Selezionare **applicazione Web ASP.NET (.NET Framework)**.

1. Denominare il progetto **SandwichServices** e fare clic su **OK**.

1. Nel **nuova applicazione Web ASP.NET** finestra di dialogo, seleziona **vuota** e quindi selezionare **OK**.

   ![Finestra di tipo app web ASP.NET in Visual Studio](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>Aggiungere un web form

1. Fare clic sul progetto in SandwichServices **Esplora soluzioni** e selezionare **Add** > **nuovo elemento**.

1. Nel **Aggiungi nuovo elemento** finestra di dialogo espandere il **installato** > **Visual c#** > **Web** categoria, quindi Selezionare il **Web Form** modello.

1. Accettare il nome predefinito (**WebForm1**), quindi selezionare **Add**.

   *WebForm1.aspx* viene aperto in **origine** visualizzazione.

1. Aggiungere il markup seguente all'interno di  **\<corpo >** tag:

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>Creare un servizio WCF abilitato per AJAX

1. Fare clic sul progetto in SandwichServices **Esplora soluzioni** e selezionare **Add** > **nuovo elemento**.

1. Nel **Aggiungi nuovo elemento** finestra di dialogo espandere il **installato** > **Visual c#** > **Web** categoria, quindi Selezionare il **servizio WCF (compatibile con AJAX)** modello.

   ![Modello di elemento (compatibile con AJAX) del servizio WCF in Visual Studio](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. Nome del servizio **CostService** e quindi selezionare **Add**.

   *CostService.svc.cs* viene aperto nell'editor.

1. Implementare l'operazione nel servizio. Aggiungere il metodo seguente alla classe CostService per calcolare il costo di una quantità di panini:

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>Configurare il client per accedere al servizio

1. Aprire il *WebForm1.aspx* del file e selezionare il **progettazione** visualizzazione.

2. Dal **View** dal menu **della casella degli strumenti**.

3. Espandere la **AJAX Extensions** nodo e trascinare un **ScriptManager** nel form.

4. Nel **origine** consente di visualizzare, aggiungere il codice seguente tra i  **\<ScriptManager >** tag per specificare il percorso del servizio WCF:

    ```html
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

1. Aggiungere il codice per la funzione Javascript `Calculate()`. Inserire il codice seguente nel **head** sezione di web form:

    ```javascript
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
    ```

   Questo codice chiama il metodo di CostService per calcolare il prezzo per tre panini e quindi Visualizza il risultato nel controllo span chiamato **additionResult**.

## <a name="run-the-program"></a>Eseguire il programma

Verificare che l'opzione *WebForm1.aspx* ha lo stato attivo e quindi premere **avviare** pulsante per avviare il client web. Il pulsante dispone di un triangolo verde e trovo una **IIS Express (Microsoft Edge)**. In alternativa, premere **F5**. Scegliere il **prezzo di 3 panini** pulsante per generare l'output previsto di "3.75".

## <a name="example-code"></a>codice di esempio

Seguito è riportato il codice completo nel *CostService.svc.cs* file:

```csharp
using System.ServiceModel;
using System.ServiceModel.Activation;

namespace SandwichServices
{
    [ServiceContract(Namespace = "")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class CostService
    {
        [OperationContract]
        public double CostOfSandwiches(int quantity)
        {
            return 1.25 * quantity;
        }
    }
}
```

Seguito è riportato l'intero contenuto del *WebForm1.aspx* pagina:

```aspx-csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="SandwichServices.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
        <asp:ScriptManager ID="ScriptManager1" runat="server">
            <Services>
                <asp:ServiceReference Path="~/CostService.svc" />
            </Services>
        </asp:ScriptManager>

        <input type="button" value="Price of 3 sandwiches" onclick="Calculate()" />
        <br />
        <span id="additionResult"></span>
    </form>
</body>
</html>
```

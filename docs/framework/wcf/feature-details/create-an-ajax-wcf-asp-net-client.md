---
title: Creare un servizio WCF abilitato per AJAX e un client ASP.NET in Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 1f5c9eb1750b0df28836f147d5b4be1b223bb52e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053686"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>Procedura: Creare un servizio WCF abilitato per AJAX e un client ASP.NET che acceda al servizio

In questo argomento viene illustrato come utilizzare Visual Studio per creare un servizio Windows Communication Foundation (WCF) abilitato per AJAX e un client ASP.NET che accede al servizio.

## <a name="create-an-aspnet-web-app"></a>Creare un'app Web ASP.NET

1. Aprire Visual Studio.

1. Scegliere **nuovo** > **progetto** dal menu **file** .

1. Nella finestra di dialogo **nuovo progetto** espandere la categoria**Visual C#**   >  **Web** **installata** > , quindi selezionare **applicazione Web ASP.NET (.NET Framework)** .

1. Denominare il progetto **SandwichServices** e fare clic su **OK**.

1. Nella finestra di dialogo **nuova applicazione Web ASP.NET** selezionare **vuoto** e quindi fare clic su **OK**.

   ![Finestra di dialogo tipo di app Web ASP.NET in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>Aggiungi un Web Form

1. Fare clic con il pulsante destro del mouse sul progetto SandwichServices in **Esplora soluzioni** e scegliere **Aggiungi** > **nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** espandere la categoria**Visual C#**   >  **Web** **installata** > , quindi selezionare il modello **Web Form** .

1. Accettare il nome predefinito (**WebForm1**), quindi selezionare **Aggiungi**.

   *WebForm1. aspx* verrà aperto nella visualizzazione **origine** .

1. Aggiungere il markup seguente all'interno del  **\<corpo >** Tag:

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>Creare un servizio WCF abilitato per AJAX

1. Fare clic con il pulsante destro del mouse sul progetto SandwichServices in **Esplora soluzioni** e scegliere **Aggiungi** > **nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** espandere la categoria**Visual C#**   >  **Web** **installata** > , quindi selezionare il modello **servizio WCF (abilitato per AJAX)** .

   ![Modello di elemento del servizio WCF (abilitato per AJAX) in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. Assegnare al servizio il nome **CostService** e quindi selezionare **Aggiungi**.

   *CostService.svc.cs* viene aperto nell'editor.

1. Implementare l'operazione nel servizio. Aggiungere il metodo seguente alla classe CostService per calcolare il costo di una quantità di panini:

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>Configurare il client per l'accesso al servizio

1. Aprire il file *WebForm1. aspx* e selezionare la visualizzazione **progettazione** .

2. Scegliere **casella degli strumenti**dal menu **Visualizza** .

3. Espandere il nodo **Estensioni AJAX** e trascinare un **ScriptManager** nel form.

4. Tornare alla visualizzazione **origine** , aggiungere il seguente codice tra i  **\<tag ScriptManager >** per specificare il percorso del servizio WCF:

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. Aggiungere il codice per la funzione `Calculate()`JavaScript. Inserire il codice seguente nella sezione **Head** del Web Form:

    ```html
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

   Questo codice chiama il metodo di CostService per calcolare il prezzo per tre panini, quindi Visualizza il risultato nell'intervallo denominato **additionResult**.

## <a name="run-the-program"></a>Eseguire il programma

Verificare che *WebForm1. aspx* abbia lo stato attivo e quindi fare clic sul pulsante **Start** per avviare il client Web. Il pulsante ha un triangolo verde e indica un elemento come **IIS Express (Microsoft Edge)** . In alternativa, è possibile premere **F5**. Fare clic sul pulsante **prezzo di 3 panini** per generare l'output previsto di "3,75".

## <a name="example-code"></a>codice di esempio

Di seguito è riportato il codice completo nel file *CostService.svc.cs* :

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

Di seguito è riportato il contenuto completo della pagina *WebForm1. aspx* :

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

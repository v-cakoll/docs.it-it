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
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="bf507-102">Procedura: Creare un servizio WCF abilitato per AJAX e un client ASP.NET che acceda al servizio</span><span class="sxs-lookup"><span data-stu-id="bf507-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="bf507-103">In questo argomento viene illustrato come utilizzare Visual Studio per creare un servizio Windows Communication Foundation (WCF) abilitato per AJAX e un client ASP.NET che accede al servizio.</span><span class="sxs-lookup"><span data-stu-id="bf507-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="bf507-104">Creare un'app Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bf507-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="bf507-105">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bf507-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="bf507-106">Scegliere **nuovo** > **progetto** dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="bf507-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="bf507-107">Nella finestra di dialogo **nuovo progetto** espandere la categoria**Visual C#**   >  **Web** **installata** > , quindi selezionare **applicazione Web ASP.NET (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="bf507-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="bf507-108">Denominare il progetto **SandwichServices** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf507-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="bf507-109">Nella finestra di dialogo **nuova applicazione Web ASP.NET** selezionare **vuoto** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf507-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Finestra di dialogo tipo di app Web ASP.NET in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="bf507-111">Aggiungi un Web Form</span><span class="sxs-lookup"><span data-stu-id="bf507-111">Add a web form</span></span>

1. <span data-ttu-id="bf507-112">Fare clic con il pulsante destro del mouse sul progetto SandwichServices in **Esplora soluzioni** e scegliere **Aggiungi** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="bf507-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="bf507-113">Nella finestra di dialogo **Aggiungi nuovo elemento** espandere la categoria**Visual C#**   >  **Web** **installata** > , quindi selezionare il modello **Web Form** .</span><span class="sxs-lookup"><span data-stu-id="bf507-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="bf507-114">Accettare il nome predefinito (**WebForm1**), quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bf507-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="bf507-115">*WebForm1. aspx* verrà aperto nella visualizzazione **origine** .</span><span class="sxs-lookup"><span data-stu-id="bf507-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="bf507-116">Aggiungere il markup seguente all'interno del  **\<corpo >** Tag:</span><span class="sxs-lookup"><span data-stu-id="bf507-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="bf507-117">Creare un servizio WCF abilitato per AJAX</span><span class="sxs-lookup"><span data-stu-id="bf507-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="bf507-118">Fare clic con il pulsante destro del mouse sul progetto SandwichServices in **Esplora soluzioni** e scegliere **Aggiungi** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="bf507-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="bf507-119">Nella finestra di dialogo **Aggiungi nuovo elemento** espandere la categoria**Visual C#**   >  **Web** **installata** > , quindi selezionare il modello **servizio WCF (abilitato per AJAX)** .</span><span class="sxs-lookup"><span data-stu-id="bf507-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Modello di elemento del servizio WCF (abilitato per AJAX) in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="bf507-121">Assegnare al servizio il nome **CostService** e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bf507-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="bf507-122">*CostService.svc.cs* viene aperto nell'editor.</span><span class="sxs-lookup"><span data-stu-id="bf507-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="bf507-123">Implementare l'operazione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="bf507-123">Implement the operation in the service.</span></span> <span data-ttu-id="bf507-124">Aggiungere il metodo seguente alla classe CostService per calcolare il costo di una quantità di panini:</span><span class="sxs-lookup"><span data-stu-id="bf507-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="bf507-125">Configurare il client per l'accesso al servizio</span><span class="sxs-lookup"><span data-stu-id="bf507-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="bf507-126">Aprire il file *WebForm1. aspx* e selezionare la visualizzazione **progettazione** .</span><span class="sxs-lookup"><span data-stu-id="bf507-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="bf507-127">Scegliere **casella degli strumenti**dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="bf507-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="bf507-128">Espandere il nodo **Estensioni AJAX** e trascinare un **ScriptManager** nel form.</span><span class="sxs-lookup"><span data-stu-id="bf507-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="bf507-129">Tornare alla visualizzazione **origine** , aggiungere il seguente codice tra i  **\<tag ScriptManager >** per specificare il percorso del servizio WCF:</span><span class="sxs-lookup"><span data-stu-id="bf507-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="bf507-130">Aggiungere il codice per la funzione `Calculate()`JavaScript.</span><span class="sxs-lookup"><span data-stu-id="bf507-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="bf507-131">Inserire il codice seguente nella sezione **Head** del Web Form:</span><span class="sxs-lookup"><span data-stu-id="bf507-131">Place the following code in the **head** section of the web form:</span></span>

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

   <span data-ttu-id="bf507-132">Questo codice chiama il metodo di CostService per calcolare il prezzo per tre panini, quindi Visualizza il risultato nell'intervallo denominato **additionResult**.</span><span class="sxs-lookup"><span data-stu-id="bf507-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="bf507-133">Eseguire il programma</span><span class="sxs-lookup"><span data-stu-id="bf507-133">Run the program</span></span>

<span data-ttu-id="bf507-134">Verificare che *WebForm1. aspx* abbia lo stato attivo e quindi fare clic sul pulsante **Start** per avviare il client Web.</span><span class="sxs-lookup"><span data-stu-id="bf507-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="bf507-135">Il pulsante ha un triangolo verde e indica un elemento come **IIS Express (Microsoft Edge)** .</span><span class="sxs-lookup"><span data-stu-id="bf507-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="bf507-136">In alternativa, è possibile premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="bf507-136">Or, you can press **F5**.</span></span> <span data-ttu-id="bf507-137">Fare clic sul pulsante **prezzo di 3 panini** per generare l'output previsto di "3,75".</span><span class="sxs-lookup"><span data-stu-id="bf507-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="bf507-138">codice di esempio</span><span class="sxs-lookup"><span data-stu-id="bf507-138">Example code</span></span>

<span data-ttu-id="bf507-139">Di seguito è riportato il codice completo nel file *CostService.svc.cs* :</span><span class="sxs-lookup"><span data-stu-id="bf507-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

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

<span data-ttu-id="bf507-140">Di seguito è riportato il contenuto completo della pagina *WebForm1. aspx* :</span><span class="sxs-lookup"><span data-stu-id="bf507-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

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

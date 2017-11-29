---
title: 'Procedura: creare un servizio WCF compatibile con AJAX e un client ASP.NET che accede al servizio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a45a186b0d281976f3d6ad554d75742ba0f1cd50
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="b871f-102">Procedura: creare un servizio WCF compatibile con AJAX e un client ASP.NET che accede al servizio</span><span class="sxs-lookup"><span data-stu-id="b871f-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>
<span data-ttu-id="b871f-103">In questo argomento viene illustrato come utilizzare Visual Studio 2008 per creare un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] compatibile con AJAX e un client ASP.NET che accede a tale servizio.</span><span class="sxs-lookup"><span data-stu-id="b871f-103">This topic shows how to use Visual Studio 2008 to create an AJAX-enabled [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and an ASP.NET client that accesses the service.</span></span> <span data-ttu-id="b871f-104">Il codice per il servizio e per il client viene fornito nella sezione Esempio dopo la descrizione dei passaggi necessari per la creazione del servizio e del client della sezione Procedure.</span><span class="sxs-lookup"><span data-stu-id="b871f-104">The code for the service and for the client are provided in the Example section after the steps for creating them are described in the Procedures section.</span></span>  
  
### <a name="to-create-the-aspnet-client-application"></a><span data-ttu-id="b871f-105">Per creare un'applicazione client ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b871f-105">To create the ASP.NET client application</span></span>  
  
1.  <span data-ttu-id="b871f-106">Aprire [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b871f-106">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="b871f-107">Dal **File** dal menu **New**, quindi **progetto**, quindi **Web**, quindi selezionare **applicazione Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="b871f-107">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Application**.</span></span>  
  
3.  <span data-ttu-id="b871f-108">Denominare il progetto `SandwichServices` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b871f-108">Name the Project `SandwichServices` and click **OK**.</span></span>  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a><span data-ttu-id="b871f-109">Per creare il servizio WCF compatibile con AJAX</span><span class="sxs-lookup"><span data-stu-id="b871f-109">To create the WCF AJAX-enabled service</span></span>  
  
1.  <span data-ttu-id="b871f-110">Fare doppio clic sul `SandwichServices` nel progetto di **Esplora** window e selezionare **Aggiungi**, quindi **nuovo elemento**e quindi **sevizio WCF compatibile AJAX** .</span><span class="sxs-lookup"><span data-stu-id="b871f-110">Right-click the `SandwichServices` project in the **Solution Explorer** window and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>  
  
2.  <span data-ttu-id="b871f-111">Nome del servizio `CostService` nel **nome** casella e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b871f-111">Name the service `CostService` in the **Name** box and click **Add**.</span></span>  
  
3.  <span data-ttu-id="b871f-112">Aprire il file CostService.svc.cs.</span><span class="sxs-lookup"><span data-stu-id="b871f-112">Open the CostService.svc.cs file.</span></span>  
  
4.  <span data-ttu-id="b871f-113">Specificare il `Namespace` per <xref:System.ServiceModel.ServiceContractAttribute> come `SandwichService`:</span><span class="sxs-lookup"><span data-stu-id="b871f-113">Specify the `Namespace` for <xref:System.ServiceModel.ServiceContractAttribute> as `SandwichService`:</span></span>  
  
    ```  
    namespace SandwichServices  
    {  
      [ServiceContract(Namespace = "SandwichServices")]  
      [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
       public class CostService  
       {  
         …  
       }  
     }  
    ```  
  
5.  <span data-ttu-id="b871f-114">Implementare le operazioni nel servizio.</span><span class="sxs-lookup"><span data-stu-id="b871f-114">Implement the operations in the service.</span></span> <span data-ttu-id="b871f-115">Aggiungere <xref:System.ServiceModel.OperationContractAttribute> a ognuna delle operazioni per indicare che fanno parte del contratto.</span><span class="sxs-lookup"><span data-stu-id="b871f-115">Add the <xref:System.ServiceModel.OperationContractAttribute> to each of the operations to indicate that they are part of the contract.</span></span> <span data-ttu-id="b871f-116">Nell'esempio seguente viene implementato un metodo che restituisce il costo di una determinata quantità di panini.</span><span class="sxs-lookup"><span data-stu-id="b871f-116">The following example implements a method that returns the cost of a given quantity of sandwiches.</span></span>  
  
    ```  
    public class CostService  
    {  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
    // Add more operations here and mark them with [OperationContract]  
    }  
    ```  
  
### <a name="to-configure-the-client-to-access-the-service"></a><span data-ttu-id="b871f-117">Per configurare il client per l'accesso al servizio</span><span class="sxs-lookup"><span data-stu-id="b871f-117">To configure the client to access the service</span></span>  
  
1.  <span data-ttu-id="b871f-118">Aprire la pagina Default.aspx e selezionare il **progettazione** visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b871f-118">Open the Default.aspx page and select the **Design** view.</span></span>  
  
2.  <span data-ttu-id="b871f-119">Dal **vista** dal menu **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="b871f-119">From the **View** menu, select **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="b871f-120">Espandere il **Estensioni AJAX** nodo e trascinare un **ScriptManager** sulla pagina Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="b871f-120">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** on to the Default.aspx page.</span></span>  
  
4.  <span data-ttu-id="b871f-121">Fare doppio clic su di **ScriptManager** e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b871f-121">Right-click the **ScriptManager** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="b871f-122">Espandere il **servizi** insieme il **proprietà** finestra per aprire la **Editor della raccolta ServiceReference** finestra.</span><span class="sxs-lookup"><span data-stu-id="b871f-122">Expand the **Services** collection in the **Properties** window to open up the **ServiceReference Collection Editor** window.</span></span>  
  
6.  <span data-ttu-id="b871f-123">Fare clic su **Aggiungi**, specificare `CostService.svc` come il **percorso** a cui fa riferimento e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b871f-123">Click **Add**, specify `CostService.svc` as the **Path** referenced, and click **OK**.</span></span>  
  
7.  <span data-ttu-id="b871f-124">Espandere il **HTML** nodo il **della casella degli strumenti** e trascinare e rilasciare un **Input (pulsante)** sulla pagina Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="b871f-124">Expand the **HTML** node in the **Toolbox** and drag and drop an **Input (Button)** on to the Default.aspx page.</span></span>  
  
8.  <span data-ttu-id="b871f-125">Fare doppio clic su di **pulsante** e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b871f-125">Right-click the **Button** and select **Properties**.</span></span>  
  
9. <span data-ttu-id="b871f-126">Modifica il **valore** campo `Price for 3 Sandwiches`.</span><span class="sxs-lookup"><span data-stu-id="b871f-126">Change the **Value** field to `Price for 3 Sandwiches`.</span></span>  
  
10. <span data-ttu-id="b871f-127">Fare doppio clic su di **pulsante** per accedere al codice JavaScript.</span><span class="sxs-lookup"><span data-stu-id="b871f-127">Double-click the **Button** to access the JavaScript code.</span></span>  
  
11. <span data-ttu-id="b871f-128">Passare il codice JavaScript seguente all'interno di <`script`> elemento.</span><span class="sxs-lookup"><span data-stu-id="b871f-128">Pass in the following JavaScript code within the <`script`> element.</span></span>  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a><span data-ttu-id="b871f-129">Per accedere al servizio dal client</span><span class="sxs-lookup"><span data-stu-id="b871f-129">To access the service from the client</span></span>  
  
1.  <span data-ttu-id="b871f-130">Utilizzare Ctrl + F5 per avviare il servizio e il client Web.</span><span class="sxs-lookup"><span data-stu-id="b871f-130">Use Ctrl +F5 to launch the service and the Web client.</span></span> <span data-ttu-id="b871f-131">Fare clic su di **prezzo di 3 panini alla griglia** pulsante per generare l'output previsto di "3.75".</span><span class="sxs-lookup"><span data-stu-id="b871f-131">Click the **Price for 3 Grilled Sandwiches** button to generate the expected output of "3.75".</span></span>  
  
## <a name="example"></a><span data-ttu-id="b871f-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="b871f-132">Example</span></span>  
 <span data-ttu-id="b871f-133">In questo esempio è contenuto il codice del servizio presente nel file WCFService.svc.cs e il codice del client presente nel file Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="b871f-133">This example contains the service code contained in the WCFService.svc.cs file and the client code contained in the Default.aspx file.</span></span>  
  
```  
//The service code contained in the CostService.svc.cs file.  
  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace SandwichServices  
{  
    [ServiceContract(Namespace="SandwichServices")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class CostService  
    {  
        // Add [WebGet] attribute to use HTTP GET  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
        // Add more operations here and mark them with [OperationContract]  
    }  
}  
//The code for hosting the service is contained in the CostService.svc file.  
  
<%@ ServiceHost Language="C#" Debug="true" Service="SandwichServices.CostService" CodeBehind="CostService.svc.cs" %>  
  
//The client code contained in the Default.aspx file.  
  
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="SandwichServices._Default" %>  
  
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">  
  
<html >  
<head runat="server">  
    <title>Untitled Page</title>  
<script language="javascript" type="text/javascript">  
// <!CDATA[  
  
function Button1_onclick() {  
var service = new SandwichServices.CostService();  
service.CostOfSandwiches(3, onSuccess, null, null);  
}  
  
function onSuccess(result){  
alert(result);  
}  
  
// ]]>  
</script>  
</head>  
<body>  
    <form id="form1" runat="server">  
    <div>  
  
    </div>  
    <asp:ScriptManager ID="ScriptManager1" runat="server">  
        <services>  
            <asp:servicereference Path="CostService.svc" />  
        </services>  
    </asp:ScriptManager>  
    </form>  
    <p>  
        <input id="Button1" type="button" value="Price for 3 Sandwiches" onclick="return Button1_onclick()" /></p>  
</body>  
</html>  
```     

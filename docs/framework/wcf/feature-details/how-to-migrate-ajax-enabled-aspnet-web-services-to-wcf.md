---
title: 'Procedura: Eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF'
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: dfbb32a751623fb1e3753cfd8bbbaf5910d571b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143000"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a><span data-ttu-id="12088-102">Procedura: Eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF</span><span class="sxs-lookup"><span data-stu-id="12088-102">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>
<span data-ttu-id="12088-103">In questo argomento descrive le procedure necessarie per eseguire la migrazione di un servizio ASP.NET AJAX di base a un servizio compatibile con AJAX Windows Communication Foundation (WCF) equivalente.</span><span class="sxs-lookup"><span data-stu-id="12088-103">This topic outlines procedures to migrate a basic ASP.NET AJAX service to an equivalent AJAX-enabled Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="12088-104">Viene illustrato come creare una versione WCF equivalente a livello funzionale di un servizio ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="12088-104">It shows how to create a functionally equivalent WCF version of an ASP.NET AJAX service.</span></span> <span data-ttu-id="12088-105">I due servizi possono quindi essere usati contemporaneamente, o il servizio WCF è utilizzabile per sostituire il servizio ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="12088-105">The two services can then be used side by side, or the WCF service can be used to replace the ASP.NET AJAX service.</span></span>

 <span data-ttu-id="12088-106">La migrazione di una versione esistente di ASP.NET AJAX servizio a un servizio AJAX WCF offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="12088-106">Migrating an existing ASP.NET AJAX service to a WCF AJAX service gives you the following benefits:</span></span>

-   <span data-ttu-id="12088-107">È possibile esporre il servizio AJAX come servizio SOAP tramite una minima configurazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="12088-107">You can expose your AJAX service as a SOAP service with minimal extra configuration.</span></span>

-   <span data-ttu-id="12088-108">È possibile trarre vantaggio dalle funzionalità WCF, ad esempio traccia e così via.</span><span class="sxs-lookup"><span data-stu-id="12088-108">You can benefit from WCF features such as tracing, and so on.</span></span>

 <span data-ttu-id="12088-109">Le procedure seguenti presuppongono che si usi Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="12088-109">The following procedures assume that you are using Visual Studio 2012.</span></span>

 <span data-ttu-id="12088-110">Il codice generato dalle procedure descritte in questo argomento viene fornito nell'esempio riportato dopo le procedure stesse.</span><span class="sxs-lookup"><span data-stu-id="12088-110">The code that results from the procedures outlined in this topic is provided in the example following the procedures.</span></span>

 <span data-ttu-id="12088-111">Per altre informazioni sull'esposizione di un servizio WCF tramite un endpoint compatibile con AJAX, vedere il [come: Utilizzare la configurazione per aggiungere un Endpoint ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="12088-111">For more information about exposing a WCF service through an AJAX-enabled endpoint, see the [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) topic.</span></span>

### <a name="to-create-and-test-the-aspnet-web-service-application"></a><span data-ttu-id="12088-112">Per creare e testare l'applicazione del servizio Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="12088-112">To create and test the ASP.NET Web service application</span></span>

1.  <span data-ttu-id="12088-113">Open Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="12088-113">Open Visual Studio 2012.</span></span>

2.  <span data-ttu-id="12088-114">Dal **File** dal menu **New**, quindi **progetto**, quindi **Web**, quindi selezionare **applicazione servizio Web ASP.NET** .</span><span class="sxs-lookup"><span data-stu-id="12088-114">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Service Application**.</span></span>

3.  <span data-ttu-id="12088-115">Denominare il progetto `ASPHello` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="12088-115">Name the project `ASPHello` and click **OK**.</span></span>

4.  <span data-ttu-id="12088-116">Rimuovere il commento dalla riga nel file Service1.asmx.cs che contiene `System.Web.Script.Services.ScriptService]` per abilitare AJAX per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="12088-116">Uncomment the line in the Service1.asmx.cs file that contains `System.Web.Script.Services.ScriptService]` to enable AJAX for this service.</span></span>

5.  <span data-ttu-id="12088-117">Dal **compilare** dal menu **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="12088-117">From the **Build** menu, select **Build Solution**.</span></span>

6.  <span data-ttu-id="12088-118">Scegliere **Avvia senza eseguire debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="12088-118">From the **Debug** menu, select **Start Without Debugging**.</span></span>

7.  <span data-ttu-id="12088-119">Nella pagina Web generata, selezionare l'operazione `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="12088-119">On the Web page generated, select the `HelloWorld` operation.</span></span>

8.  <span data-ttu-id="12088-120">Fare clic sui **Invoke** pulsante la `HelloWorld` pagina di test.</span><span class="sxs-lookup"><span data-stu-id="12088-120">Click the **Invoke** button on the `HelloWorld` test page.</span></span> <span data-ttu-id="12088-121">Si dovrebbe ricevere la risposta XML seguente:</span><span class="sxs-lookup"><span data-stu-id="12088-121">You should receive the following XML response.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. <span data-ttu-id="12088-122">Questa risposta conferma che si dispone di un servizio ASP.NET.AJAX funzionante e, in particolare, che il servizio ha esposto un endpoint su Service1.asmx/HelloWorld che risponde alle richieste HTTP POST e restituisce XML.</span><span class="sxs-lookup"><span data-stu-id="12088-122">This response confirms that you now have a functioning ASP.NET AJAX service and, in particular, that the service has now exposed an endpoint at Service1.asmx/HelloWorld that responds to HTTP POST requests and returns XML.</span></span>

     <span data-ttu-id="12088-123">A questo punto si è pronti per convertire questo servizio per utilizzare un servizio AJAX WCF.</span><span class="sxs-lookup"><span data-stu-id="12088-123">Now you are ready to convert this service to use a WCF AJAX service.</span></span>

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a><span data-ttu-id="12088-124">Per creare un'applicazione di servizio AJAX WCF equivalente</span><span class="sxs-lookup"><span data-stu-id="12088-124">To create an equivalent WCF AJAX service application</span></span>

1.  <span data-ttu-id="12088-125">Fare doppio clic il **ASPHello** del progetto e selezionare **Add**, quindi **nuovo elemento**e quindi **sevizio WCF compatibile AJAX**.</span><span class="sxs-lookup"><span data-stu-id="12088-125">Right-click the **ASPHello** project and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>

2.  <span data-ttu-id="12088-126">Nome del servizio `WCFHello` e fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="12088-126">Name the service `WCFHello` and click **Add**.</span></span>

3.  <span data-ttu-id="12088-127">Aprire il file WCFHello.svc.cs.</span><span class="sxs-lookup"><span data-stu-id="12088-127">Open the WCFHello.svc.cs file.</span></span>

4.  <span data-ttu-id="12088-128">Da Service1.asmx.cs, copiare l'implementazione seguente del `HelloWorld` operazione.</span><span class="sxs-lookup"><span data-stu-id="12088-128">From Service1.asmx.cs, copy the following implementation of the `HelloWorld` operation.</span></span>

    ```
    public string HelloWorld()
    {
         return "Hello World";
    }
    ```

5.  <span data-ttu-id="12088-129">Incolla implementazione copiata del `HelloWorld` operazione nel file WCFHello.svc.cs al posto di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="12088-129">Paste to copied implementation of the `HelloWorld` operation into the WCFHello.svc.cs file in place of the following code.</span></span>

    ```
    public void DoWork()
    {
          // Add your operation implementation here
          return;
    }
    ```

6.  <span data-ttu-id="12088-130">Specificare il `Namespace` dell'attributo per <xref:System.ServiceModel.ServiceContractAttribute> come `WCFHello`.</span><span class="sxs-lookup"><span data-stu-id="12088-130">Specify the `Namespace` attribute for <xref:System.ServiceModel.ServiceContractAttribute> as `WCFHello`.</span></span>

    ```
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7.  <span data-ttu-id="12088-131">Aggiungere il <xref:System.ServiceModel.Web.WebInvokeAttribute> per il `HelloWorld` operazione e impostare le <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> proprietà da restituire <xref:System.ServiceModel.Web.WebMessageFormat.Xml>.</span><span class="sxs-lookup"><span data-stu-id="12088-131">Add the <xref:System.ServiceModel.Web.WebInvokeAttribute> to the `HelloWorld` operation and set the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> property to return <xref:System.ServiceModel.Web.WebMessageFormat.Xml>.</span></span> <span data-ttu-id="12088-132">Se non impostato, il tipo restituito predefinito è <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span><span class="sxs-lookup"><span data-stu-id="12088-132">Note that, if not set, the default return type is <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span>

    ```
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8.  <span data-ttu-id="12088-133">Dal **compilare** dal menu **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="12088-133">From the **Build** menu, select **Build Solution**.</span></span>

9. <span data-ttu-id="12088-134">Aprire il file Wcfhello svc e il **eseguire il Debug** dal menu **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="12088-134">Open the WCFHello.svc file and from the **Debug** menu, select **Start Without Debugging**.</span></span>

10. <span data-ttu-id="12088-135">Il servizio esporrà un endpoint a `WCFHello.svc/HelloWorld`, che risponde alle richieste HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="12088-135">The service now exposes an endpoint at `WCFHello.svc/HelloWorld`, which responds to HTTP POST requests.</span></span> <span data-ttu-id="12088-136">Le richieste HTTP POST non possono essere sottoposte a test dal browser, ma l'endpoint restituisce l'XML seguente.</span><span class="sxs-lookup"><span data-stu-id="12088-136">HTTP POST requests cannot be tested from the browser, but the endpoint returns XML following XML.</span></span>

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. <span data-ttu-id="12088-137">Il `WCFHello.svc/HelloWorld` e il `Service1.aspx/HelloWorld` gli endpoint sono ora funzionalmente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="12088-137">The `WCFHello.svc/HelloWorld` and the `Service1.aspx/HelloWorld` endpoints are now functionally equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="12088-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="12088-138">Example</span></span>
 <span data-ttu-id="12088-139">Il codice che scaturisce dalle procedure descritte in questo argomento viene fornito nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="12088-139">The code that results from the procedures outlined in this topic is provided in the following example.</span></span>

```csharp
//This is the ASP.NET code in the Service1.asmx.cs file.

using System;
using System.Collections;
using System.ComponentModel;
using System.Data;
using System.Linq;
using System.Web;
using System.Web.Services;
using System.Web.Services.Protocols;
using System.Xml.Linq;
using System.Web.Script.Services;

namespace ASPHello
{
    /// <summary>
    /// Summary description for Service1.
    /// </summary>
    [WebService(Namespace = "http://tempuri.org/")]
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]
    [ToolboxItem(false)]
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.
    [System.Web.Script.Services.ScriptService]
    public class Service1 : System.Web.Services.WebService
    {

        [WebMethod]
        public string HelloWorld()
        {
            return "Hello World";
        }
    }
}

//This is the WCF code in the WCFHello.svc.cs file.
using System;
using System.Linq;
using System.Runtime.Serialization;
using System.ServiceModel;
using System.ServiceModel.Activation;
using System.ServiceModel.Web;

namespace ASPHello
{
    [ServiceContract(Namespace = "WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class WCFHello
    {
        // Add [WebInvoke] attribute to use HTTP GET.
        [OperationContract]
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
        public string HelloWorld()
        {
            return "Hello World";
        }

        // Add more operations here and mark them with [OperationContract].
    }
}
```

 <span data-ttu-id="12088-140">Il tipo <xref:System.Xml.XmlDocument> non è supportato da <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> perché non è serializzabile mediante <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="12088-140">The <xref:System.Xml.XmlDocument> type is not supported by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because it is not serializable by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="12088-141">È possibile utilizzare un tipo <xref:System.Xml.Linq.XDocument> oppure serializzare <xref:System.Xml.XmlDocument.DocumentElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="12088-141">You can use either an <xref:System.Xml.Linq.XDocument> type, or serialize the <xref:System.Xml.XmlDocument.DocumentElement%2A> instead.</span></span>

 <span data-ttu-id="12088-142">Se i servizi Web ASMX sono in fase di aggiornamento e migrazione side-by-side ai servizi WCF, evitare di mapping di due tipi per lo stesso nome sul client.</span><span class="sxs-lookup"><span data-stu-id="12088-142">If ASMX Web services are being upgraded and migrated side-by-side to WCF services, avoid mapping two types to the same name on the client.</span></span> <span data-ttu-id="12088-143">Se viene utilizzato lo stesso tipo sia in un <xref:System.Web.Services.WebMethodAttribute> che in un <xref:System.ServiceModel.ServiceContractAttribute>, nei serializzatori verrà generata un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="12088-143">This causes an exception in serializers if the same type is used in a <xref:System.Web.Services.WebMethodAttribute> and a <xref:System.ServiceModel.ServiceContractAttribute>:</span></span>

-   <span data-ttu-id="12088-144">Se viene aggiunto per primo servizio WCF, richiamare il metodo sul servizio Web ASMX provoca un'eccezione in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> perché la definizione dello stile WCF dell'ordine nel proxy ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="12088-144">If WCF service is added first, invoking the method on ASMX Web Service causes exception in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> because the WCF style definition of the order in the proxy takes precedence.</span></span>

-   <span data-ttu-id="12088-145">Se viene aggiunto per primo servizio Web ASMX, richiamare il metodo sul servizio WCF provoca un'eccezione in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> perché la definizione dello stile di servizio Web dell'ordine nel proxy ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="12088-145">If ASMX Web Service is added first, invoking method on WCF service causes exception in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because the Web Service style definition of the order in the proxy takes precedence.</span></span>

 <span data-ttu-id="12088-146">Esistono differenze significative di comportamento tra <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e <xref:System.Web.Script.Serialization.JavaScriptSerializer> ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="12088-146">There are significant differences in behavior between the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> and the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>.</span></span> <span data-ttu-id="12088-147"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, ad esempio, rappresenta un dizionario come una matrice di coppie chiave/valore, mentre ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> rappresenta un dizionario come oggetti JSON effettivi.</span><span class="sxs-lookup"><span data-stu-id="12088-147">For example, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> represents a dictionary as an array of key/value pairs, whereas the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> represents a dictionary as actual JSON objects.</span></span> <span data-ttu-id="12088-148">Pertanto quello seguente è il dizionario rappresentato in ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="12088-148">So the following is the dictionary represented in ASP.NET AJAX.</span></span>

```
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 <span data-ttu-id="12088-149">Tale dizionario è rappresentato negli oggetti JSON come mostrato nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="12088-149">This dictionary is represented in JSON objects as shown in the following list:</span></span>

-   <span data-ttu-id="12088-150">[{"Key": "Uno", "Value": 1}, {"Key": "Due", "Value": 2}] per il</span><span class="sxs-lookup"><span data-stu-id="12088-150">[{"Key":"one","Value":1},{"Key":"two","Value":2}] by the</span></span> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>

-   <span data-ttu-id="12088-151">{"uno": 1, "due": 2} da ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="12088-151">{"one":1,"two":2} by the ASP.NET AJAX</span></span> <xref:System.Web.Script.Serialization.JavaScriptSerializer>

 <span data-ttu-id="12088-152"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> è più potente perché può gestire dizionari in cui il tipo di chiave non è una stringa, mentre <xref:System.Web.Script.Serialization.JavaScriptSerializer> non è in grado di farlo.</span><span class="sxs-lookup"><span data-stu-id="12088-152">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is more powerful in the sense that it can handle dictionaries where the key type is not string, while the <xref:System.Web.Script.Serialization.JavaScriptSerializer> cannot.</span></span> <span data-ttu-id="12088-153">Quest'ultimo, tuttavia, è più favorevole a JSON.</span><span class="sxs-lookup"><span data-stu-id="12088-153">But the latter is more JSON-friendly.</span></span>

 <span data-ttu-id="12088-154">Le differenze significative tra questi serializzatori sono riepilogate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="12088-154">The significant differences between these serializers are summarized in the following table.</span></span>

|<span data-ttu-id="12088-155">Categoria delle differenze</span><span class="sxs-lookup"><span data-stu-id="12088-155">Category of Differences</span></span>|<span data-ttu-id="12088-156">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="12088-156">DataContractJsonSerializer</span></span>|<span data-ttu-id="12088-157">JavaScriptSerializer per ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="12088-157">ASP.NET AJAX JavaScriptSerializer</span></span>|
|-----------------------------|--------------------------------|---------------------------------------|
|<span data-ttu-id="12088-158">Deserializzazione del buffer vuoto (new byte[0]) in <xref:System.Object> (o <xref:System.Uri> o alcune altre classi).</span><span class="sxs-lookup"><span data-stu-id="12088-158">Deserializing the empty buffer (new byte[0]) into <xref:System.Object> (or <xref:System.Uri>, or some other classes).</span></span>|<span data-ttu-id="12088-159">SerializationException</span><span class="sxs-lookup"><span data-stu-id="12088-159">SerializationException</span></span>|<span data-ttu-id="12088-160">Null</span><span class="sxs-lookup"><span data-stu-id="12088-160">null</span></span>|
|<span data-ttu-id="12088-161">Serializzazione di</span><span class="sxs-lookup"><span data-stu-id="12088-161">Serialization of</span></span> <xref:System.DBNull.Value>|<span data-ttu-id="12088-162">{} (o { Type":"#System"})</span><span class="sxs-lookup"><span data-stu-id="12088-162">{} (or {"__type":"#System"})</span></span>|<span data-ttu-id="12088-163">Null</span><span class="sxs-lookup"><span data-stu-id="12088-163">Null</span></span>|
|<span data-ttu-id="12088-164">Serializzazione dei membri privati di tipi [Serializable].</span><span class="sxs-lookup"><span data-stu-id="12088-164">Serialization of the private members of [Serializable] types.</span></span>|<span data-ttu-id="12088-165">serializzato</span><span class="sxs-lookup"><span data-stu-id="12088-165">serialized</span></span>|<span data-ttu-id="12088-166">non serializzato</span><span class="sxs-lookup"><span data-stu-id="12088-166">not serialized</span></span>|
|<span data-ttu-id="12088-167">Serializzazione delle proprietà pubbliche di tipi <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="12088-167">Serialization of the public properties of <xref:System.Runtime.Serialization.ISerializable> types.</span></span>|<span data-ttu-id="12088-168">non serializzato</span><span class="sxs-lookup"><span data-stu-id="12088-168">not serialized</span></span>|<span data-ttu-id="12088-169">serializzato</span><span class="sxs-lookup"><span data-stu-id="12088-169">serialized</span></span>|
|<span data-ttu-id="12088-170">"Estensioni" di JSON</span><span class="sxs-lookup"><span data-stu-id="12088-170">"Extensions" of JSON</span></span>|<span data-ttu-id="12088-171">È conforme alla specifica JSON, che richiede le virgolette per i nomi dei membri di un oggetto ({"a":"hello"}).</span><span class="sxs-lookup"><span data-stu-id="12088-171">Adheres to the JSON specification, which requires quotes on object member names ({"a":"hello"}).</span></span>|<span data-ttu-id="12088-172">Supporta i nomi dei membri di un oggetto senza virgolette ({a:"hello"}).</span><span class="sxs-lookup"><span data-stu-id="12088-172">Supports the names of object members without quotes ({a:"hello"}).</span></span>|
|<xref:System.DateTime> <span data-ttu-id="12088-173">Ora UTC (Coordinated Universal Time)</span><span class="sxs-lookup"><span data-stu-id="12088-173">Coordinated Universal Time (UTC)</span></span>|<span data-ttu-id="12088-174">Non supporta il formato "\\/Date(123456789U)\\/" o "\\/data\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\\\/)".</span><span class="sxs-lookup"><span data-stu-id="12088-174">Does not support format "\\/Date(123456789U)\\/" or "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)".</span></span>|<span data-ttu-id="12088-175">Supporta il formato "\\/Date(123456789U)\\/" e "\\/data\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\ \\/) "come valori DateTime.</span><span class="sxs-lookup"><span data-stu-id="12088-175">Supports format "\\/Date(123456789U)\\/" and "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)" as DateTime values.</span></span>|
|<span data-ttu-id="12088-176">Rappresentazione di dizionari</span><span class="sxs-lookup"><span data-stu-id="12088-176">Representation of dictionaries</span></span>|<span data-ttu-id="12088-177">Una matrice di KeyValuePair\<K, V >, gestisce tipi di chiave che non sono stringhe.</span><span class="sxs-lookup"><span data-stu-id="12088-177">An array of KeyValuePair\<K,V>, handles key types that are not strings.</span></span>|<span data-ttu-id="12088-178">Come gli oggetti JSON effettivi, ma gestisce solo i tipi di chiave che sono stringhe.</span><span class="sxs-lookup"><span data-stu-id="12088-178">As actual JSON objects - but only handles key types that are strings.</span></span>|
|<span data-ttu-id="12088-179">Caratteri di escape</span><span class="sxs-lookup"><span data-stu-id="12088-179">Escaped characters</span></span>|<span data-ttu-id="12088-180">Sempre con un carattere di escape barra (/); non consente mai caratteri JSON non validi senza carattere di escape, ad esempio "\n".</span><span class="sxs-lookup"><span data-stu-id="12088-180">Always with an escape forward slash (/); never allows un-escaped invalid JSON characters, such as "\n".</span></span>|<span data-ttu-id="12088-181">Con un carattere di escape barra (/) per i valori DateTime.</span><span class="sxs-lookup"><span data-stu-id="12088-181">With an escape forward slash (/) for DateTime values.</span></span>|

## <a name="see-also"></a><span data-ttu-id="12088-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12088-182">See also</span></span>

- [<span data-ttu-id="12088-183">Procedura: Usare la configurazione per aggiungere un endpoint ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="12088-183">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)

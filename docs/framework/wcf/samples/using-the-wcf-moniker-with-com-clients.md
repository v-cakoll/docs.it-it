---
title: Utilizzo del moniker WCF con i client COM
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: bcac9e344e2d981f9f165480cb84ac37c99fa5b0
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837779"
---
# <a name="using-the-wcf-moniker-with-com-clients"></a><span data-ttu-id="dce76-102">Utilizzo del moniker WCF con i client COM</span><span class="sxs-lookup"><span data-stu-id="dce76-102">Using the WCF Moniker with COM Clients</span></span>
<span data-ttu-id="dce76-103">In questo esempio viene illustrato come utilizzare il moniker del servizio Windows Communication Foundation (WCF) per integrare servizi Web in ambienti di sviluppo basati su COM, ad esempio Microsoft Office Visual Basic, Applications Edition (Office VBA) o Visual Basic 6,0.</span><span class="sxs-lookup"><span data-stu-id="dce76-103">This sample demonstrates how to use the Windows Communication Foundation (WCF) service moniker to integrate Web services into COM-based development environments, such as Microsoft Office Visual Basic for Applications (Office VBA) or Visual Basic 6.0.</span></span> <span data-ttu-id="dce76-104">L'esempio è costituito da un client Windows Script Host (file con estensione vbs), una libreria di classi di supporto (file con estensione dll) e una libreria di servizi (file con estensione dll) ospitati in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="dce76-104">This sample consists of a Windows Script Host client (.vbs), a supporting client library (.dll), and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="dce76-105">Il servizio è un servizio di calcolatrice e il client COM chiama operazioni matematiche, Add, Subtract, Multiply e Divide, nel servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-105">The service is a calculator service and the COM client calls math operations—Add, Subtract, Multiply, and Divide—on the service.</span></span> <span data-ttu-id="dce76-106">L'attività del client è visibile nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="dce76-106">Client activity is visible in the message box windows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dce76-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dce76-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="dce76-108">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="dce76-108">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dce76-109">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="dce76-109">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="dce76-110">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="dce76-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dce76-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="dce76-111">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 <span data-ttu-id="dce76-112">Il servizio implementa un contratto `ICalculator` definito nel modo illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="dce76-112">The service implements an `ICalculator` contract defined as shown in the following code example.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="dce76-113">Nell'esempio vengono descritti tre approcci alternativi per l'uso del moniker:</span><span class="sxs-lookup"><span data-stu-id="dce76-113">The sample demonstrates the three alternative approaches for using the moniker:</span></span>  
  
- <span data-ttu-id="dce76-114">Contratto tipizzato: il contratto viene registrato come tipo visibile a COM sul computer client.</span><span class="sxs-lookup"><span data-stu-id="dce76-114">Typed contract – The contract is registered as a COM visible type on the client computer.</span></span>  
  
- <span data-ttu-id="dce76-115">Contratto WSDL: il contratto viene fornito sotto forma di documento WSDL.</span><span class="sxs-lookup"><span data-stu-id="dce76-115">WSDL contract – The contract is supplied in the form of a WSDL document.</span></span>  
  
- <span data-ttu-id="dce76-116">Contratto MEX: il contratto viene recuperato in fase di esecuzione da un endpoint di scambio di metadati (MEX).</span><span class="sxs-lookup"><span data-stu-id="dce76-116">Metadata Exchange contract – The contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="typed-contract"></a><span data-ttu-id="dce76-117">Contratto tipizzato</span><span class="sxs-lookup"><span data-stu-id="dce76-117">Typed Contract</span></span>  
 <span data-ttu-id="dce76-118">Per usare il moniker con un uso del contratto tipizzato, è necessario registrare con COM i tipi per il contratto di servizio forniti degli attribuiti appropriati.</span><span class="sxs-lookup"><span data-stu-id="dce76-118">To use the moniker with a typed contract use, appropriately attributed types for the service contract must be registered with COM.</span></span> <span data-ttu-id="dce76-119">Per prima cosa, è necessario generare un client usando lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="dce76-119">First, a client must be generated by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="dce76-120">Eseguire il comando seguente da un prompt dei comandi nella directory del client per generare il proxy tipizzato.</span><span class="sxs-lookup"><span data-stu-id="dce76-120">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 <span data-ttu-id="dce76-121">Questa classe deve essere inclusa in un progetto e il progetto deve essere configurato per generare un assembly visibile a COM e firmato durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="dce76-121">This class must be included in a project and the project should be configured to generate a COM-visible, signed assembly when compiled.</span></span> <span data-ttu-id="dce76-122">Nel file AssemblyInfo.cs deve essere incluso l'attributo seguente:</span><span class="sxs-lookup"><span data-stu-id="dce76-122">The following attribute should be included in the AssemblyInfo.cs file.</span></span>  
  
```csharp
[assembly: ComVisible(true)]  
```  
  
 <span data-ttu-id="dce76-123">Dopo aver compilato il progetto, registrare i tipi visibili a COM usando `regasm`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dce76-123">After building the project, register the COM-visible types by using `regasm` as shown in the following example.</span></span>  
  
```console  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 <span data-ttu-id="dce76-124">L'assembly creato deve essere aggiunto alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="dce76-124">The assembly that is created should be added to the Global Assembly Cache.</span></span> <span data-ttu-id="dce76-125">Sebbene non sia strettamente obbligatoria, questa operazione semplifica il processo in cui la fase di esecuzione individua l'assembly.</span><span class="sxs-lookup"><span data-stu-id="dce76-125">Though not strictly required, this simplifies the process of the runtime locating the assembly.</span></span> <span data-ttu-id="dce76-126">Il comando seguente aggiunge l'assembly alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="dce76-126">The following command adds the assembly to the Global Assembly Cache.</span></span>  
  
```console  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
> <span data-ttu-id="dce76-127">Il moniker del servizio richiede solo la registrazione del tipo e non usa il proxy per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-127">The service moniker requires only the type registration and does not use the proxy to communicate with the service.</span></span>  
  
 <span data-ttu-id="dce76-128">L'applicazione client ComCalcClient.vbs usa la funzione `GetObject` per costruire un proxy per il servizio, usando la sintassi del moniker del servizio per specificare l'indirizzo, l'associazione e contratto per il servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-128">ComCalcClient.vbs client application uses the `GetObject` function to construct a proxy for the service, using the service moniker syntax to specify the address, binding, and contract for the service.</span></span>  
  
```vbscript
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,   
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 <span data-ttu-id="dce76-129">I parametri usati dal moniker specificano:</span><span class="sxs-lookup"><span data-stu-id="dce76-129">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="dce76-130">L'indirizzo dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-130">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="dce76-131">L'associazione che il client dovrebbe usare per connettersi a quell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dce76-131">The binding that the client should use to connect with that endpoint.</span></span> <span data-ttu-id="dce76-132">In questo caso, il wsHttpBinding definito dal sistema viene usato anche se le associazioni personalizzate possono essere definite nei file di configurazione del client.</span><span class="sxs-lookup"><span data-stu-id="dce76-132">In this case, the system-defined wsHttpBinding is used though custom bindings can be defined in client configuration files.</span></span> <span data-ttu-id="dce76-133">Per l'uso con Windows Script Host, l'associazione personalizzata viene definita in un file Cscript.exe.config nella stessa directory di Cscript.exe.</span><span class="sxs-lookup"><span data-stu-id="dce76-133">For use with the Windows Script Host, the custom binding is defined in a Cscript.exe.config file in the same directory as Cscript.exe.</span></span>  
  
- <span data-ttu-id="dce76-134">Il tipo del contratto è supportato sull'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dce76-134">The type of the contract that is supported at the endpoint.</span></span> <span data-ttu-id="dce76-135">Questo è il tipo generato e registrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dce76-135">This is the type that was generated and registered above.</span></span> <span data-ttu-id="dce76-136">Poiché lo script di Visual Basic non fornisce un ambiente COM fortemente tipizzato, è necessario specificare un identificatore per il contratto.</span><span class="sxs-lookup"><span data-stu-id="dce76-136">Because Visual Basic script does not provide a strongly-typed COM environment, an identifier for the contract must be specified.</span></span> <span data-ttu-id="dce76-137">Questo GUID è l'`interfaceID` da CalcProxy.tlb e può essere visualizzato usando gli strumenti COM, ad esempio il Visualizzatore oggetti OLE/COM (OleView.exe).</span><span class="sxs-lookup"><span data-stu-id="dce76-137">This GUID is the `interfaceID` from CalcProxy.tlb, which can be viewed by using COM tools such as the OLE/COM Object Viewer (OleView.exe).</span></span> <span data-ttu-id="dce76-138">Per ambienti fortemente tipizzati, ad esempio Office VBA o Visual Basic 6.0, è possibile aggiungere un riferimento esplicito alla libreria dei tipi e dichiarare quindi il tipo dell'oggetto proxy, invece di usare il parametro del contratto.</span><span class="sxs-lookup"><span data-stu-id="dce76-138">For strongly-typed environments such as Office VBA or Visual Basic 6.0, adding an explicit reference to the type library and then declaring the type of the proxy object can be used in place of the contract parameter.</span></span> <span data-ttu-id="dce76-139">In questo modo si fornisce anche supporto IntelliSense durante lo sviluppo dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="dce76-139">This also provides IntelliSense support during client application development.</span></span>  
  
 <span data-ttu-id="dce76-140">Una volta costruita l'istanza del proxy con il moniker del servizio, l'applicazione client può chiamare i metodi sul proxy e l'infrastruttura del moniker del servizio può chiamare le operazioni del servizio corrispondenti:</span><span class="sxs-lookup"><span data-stu-id="dce76-140">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 Quando si esegue l'esempio, la risposta dell'operazione viene visualizzata in una finestra di messaggio di Windows Script Host. Viene illustrato un client COM che esegue chiamate COM usando il moniker tipizzato per comunicare con un servizio WCF. <span data-ttu-id="dce76-143">Nonostante si usi COM nell'applicazione client, la comunicazione con il servizio è costituita solo da chiamate del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="dce76-143">Despite the use of COM in the client application, the communication with the service consists only of Web service calls.</span></span>  
  
## <a name="wsdl-contract"></a><span data-ttu-id="dce76-144">Contratto WSDL</span><span class="sxs-lookup"><span data-stu-id="dce76-144">WSDL Contract</span></span>  
 <span data-ttu-id="dce76-145">Per usare il moniker con un contratto WSDL non è richiesta alcuna registrazione della libreria client, ma il contratto WSDL per il servizio deve essere recuperato tramite un meccanismo fuori banda, ad esempio usando un browser per accedere all'endpoint WSDL per il servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-145">To use the moniker with a WSDL contract, no client library registration is required but the WSDL contract for the service must be retrieved through an out-of-band mechanism such as using a browser to access the WSDL endpoint for the service.</span></span> <span data-ttu-id="dce76-146">Il moniker può accedere quindi a quel contratto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dce76-146">The moniker can then access that contract at execution time.</span></span>  
  
 <span data-ttu-id="dce76-147">L'applicazione client ComCalcClient.vbs usa `FileSystemObject` per accedere al file WSDL salvato sul computer locale, quindi usa la funzione `GetObject` per costruire un proxy per il servizio:</span><span class="sxs-lookup"><span data-stu-id="dce76-147">The ComCalcClient.vbs client application uses the `FileSystemObject` to access the locally saved WSDL file and then again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
```vbscript  
' Open the WSDL contract file and read it all into the wsdlContract string  
Const ForReading = 1  
Set objFSO = CreateObject("Scripting.FileSystemObject")  
Set objFile = objFSO.OpenTextFile("serviceWsdl.xml", ForReading)  
wsdlContract = objFile.ReadAll  
objFile.Close  
  
' Create a string for the service moniker including the content of the WSDL contract file  
wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
```  
  
 <span data-ttu-id="dce76-148">I parametri usati dal moniker specificano:</span><span class="sxs-lookup"><span data-stu-id="dce76-148">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="dce76-149">L'indirizzo dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-149">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="dce76-150">L'associazione che il client deve usare per connettersi con quell'endpoint e lo spazio dei nomi nel quale viene definita quell'associazione.</span><span class="sxs-lookup"><span data-stu-id="dce76-150">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="dce76-151">In questo caso, viene usata `wsHttpBinding_ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="dce76-151">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="dce76-152">Il WSDL che definisce il contratto.</span><span class="sxs-lookup"><span data-stu-id="dce76-152">The WSDL that defines the contract.</span></span> <span data-ttu-id="dce76-153">In questo caso è la stringa letta dal file serviceWsdl.xml.</span><span class="sxs-lookup"><span data-stu-id="dce76-153">In this case this is the string that has been read from the serviceWsdl.xml file.</span></span>  
  
- <span data-ttu-id="dce76-154">Il nome e lo spazio dei nomi del contratto.</span><span class="sxs-lookup"><span data-stu-id="dce76-154">The name and namespace of the contract.</span></span> <span data-ttu-id="dce76-155">Questa identificazione è richiesta perché il WSDL potrebbe contenere più di un contratto.</span><span class="sxs-lookup"><span data-stu-id="dce76-155">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="dce76-156">Per impostazione predefinita, i servizi WCF generano file WSDL distinti per ogni spazio dei nomi utilizzato da.</span><span class="sxs-lookup"><span data-stu-id="dce76-156">By default, WCF services generate separate WSDL files for each namespace that the use.</span></span> <span data-ttu-id="dce76-157">Questi vengono collegati usando il costrutto di importazione di WSDL.</span><span class="sxs-lookup"><span data-stu-id="dce76-157">These are linked with the use of the WSDL import construct.</span></span> <span data-ttu-id="dce76-158">Poiché il moniker si aspetta una sola definizione WSDL, il servizio deve usare un solo spazio dei nomi, come illustrato in questo esempio, o i file separati devono essere uniti manualmente.</span><span class="sxs-lookup"><span data-stu-id="dce76-158">Because the moniker expects a single WSDL definition, the service must either use a single namespace as demonstrated in this sample or the separate files must be manually merged.</span></span>  
  
 <span data-ttu-id="dce76-159">Una volta costruita l'istanza del proxy con il moniker del servizio, l'applicazione client può chiamare i metodi sul proxy e l'infrastruttura del moniker del servizio può chiamare le operazioni del servizio corrispondenti:</span><span class="sxs-lookup"><span data-stu-id="dce76-159">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 Quando si esegue l'esempio, la risposta dell'operazione viene visualizzata in una finestra di messaggio di Windows Script Host. <span data-ttu-id="dce76-161">Viene illustrato un client COM che esegue chiamate COM usando il moniker con un contratto WSDL per comunicare con un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="dce76-161">This demonstrates a COM client making COM calls using the moniker with a WSDL contract to communicate with a WCF service.</span></span>  
  
## <a name="metadata-exchange-contract"></a><span data-ttu-id="dce76-162">Contratto di scambio di metadati</span><span class="sxs-lookup"><span data-stu-id="dce76-162">Metadata Exchange Contract</span></span>  
 <span data-ttu-id="dce76-163">Per usare il moniker con un contratto MEX, come per il contratto WSDL, non è richiesta alcuna registrazione client.</span><span class="sxs-lookup"><span data-stu-id="dce76-163">To use the moniker with a MEX contract, as with the WSDL contract, no client registration is required.</span></span> <span data-ttu-id="dce76-164">Il contratto per il servizio viene recuperato in fase di esecuzione usando lo scambio di metadati interno.</span><span class="sxs-lookup"><span data-stu-id="dce76-164">The contract for the service is retrieved at execution time through the internal use of Metadata Exchange.</span></span>  
  
 <span data-ttu-id="dce76-165">L'applicazione client ComCalcClient.vbs usa quindi la funzione `GetObject` per costruire un proxy per il servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-165">The ComCalcClient.vbs client application again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
```vbscript  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 <span data-ttu-id="dce76-166">I parametri usati dal moniker specificano:</span><span class="sxs-lookup"><span data-stu-id="dce76-166">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="dce76-167">L'indirizzo dell'endpoint di scambio di metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-167">The address of the service metadata exchange endpoint.</span></span>  
  
- <span data-ttu-id="dce76-168">L'indirizzo dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-168">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="dce76-169">L'associazione che il client deve usare per connettersi con quell'endpoint e lo spazio dei nomi nel quale viene definita quell'associazione.</span><span class="sxs-lookup"><span data-stu-id="dce76-169">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="dce76-170">In questo caso, viene usata `wsHttpBinding_ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="dce76-170">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="dce76-171">Il nome e lo spazio dei nomi del contratto.</span><span class="sxs-lookup"><span data-stu-id="dce76-171">The name and namespace of the contract.</span></span> <span data-ttu-id="dce76-172">Questa identificazione è richiesta perché il WSDL potrebbe contenere più di un contratto.</span><span class="sxs-lookup"><span data-stu-id="dce76-172">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
 <span data-ttu-id="dce76-173">Una volta costruita l'istanza del proxy con il moniker del servizio, l'applicazione client può chiamare i metodi sul proxy e l'infrastruttura del moniker del servizio può chiamare le operazioni del servizio corrispondenti:</span><span class="sxs-lookup"><span data-stu-id="dce76-173">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 Quando si esegue l'esempio, la risposta dell'operazione viene visualizzata in una finestra di messaggio di Windows Script Host. <span data-ttu-id="dce76-175">Viene illustrato un client COM che esegue chiamate COM usando il moniker con un contratto MEX per comunicare con un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="dce76-175">This demonstrates a COM client making COM calls using the moniker with a MEX contract to communicate with a WCF service.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="dce76-176">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="dce76-176">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="dce76-177">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dce76-177">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="dce76-178">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dce76-178">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="dce76-179">Da un Prompt dei comandi per gli sviluppatori per Visual Studio, aprire la cartella \client\bin\ nella cartella specifica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="dce76-179">From a Developer Command Prompt for Visual Studio, open the \client\bin folder, under the language-specific folder.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="dce76-180">Se si utilizza Windows Vista, [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7 o Windows Server 2008 R2, assicurarsi di eseguire il prompt dei comandi con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="dce76-180">If you are using Windows Vista, [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7, or Windows Server 2008 R2, make sure that you run the command prompt with administrator privileges.</span></span>  
  
4. <span data-ttu-id="dce76-181">Digitare `tlbexp.exe client.dll /out:CalcProxy.tlb` per esportare la dll in un file tlb.</span><span class="sxs-lookup"><span data-stu-id="dce76-181">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="dce76-182">È previsto un "Avviso dell'utilità di esportazione della libreria dei tipi", ma ciò non rappresenta un problema, perché il tipo generico non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dce76-182">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
5. <span data-ttu-id="dce76-183">Digitare `regasm.exe /tlb:CalcProxy.tlb client.dll` per registrare i tipi con COM.</span><span class="sxs-lookup"><span data-stu-id="dce76-183">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="dce76-184">È previsto un "Avviso dell'utilità di esportazione della libreria dei tipi", ma ciò non rappresenta un problema, perché il tipo generico non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dce76-184">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
6. <span data-ttu-id="dce76-185">Digitare `gacutil.exe /i client.dll` per aggiungere l'assembly alla Global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="dce76-185">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="dce76-186">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="dce76-186">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="dce76-187">Verificare che sia possibile accedere al servizio utilizzando un browser digitando l'indirizzo seguente: `http://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="dce76-187">Test that you can access the service using a browser by typing in the following address: `http://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="dce76-188">In risposta, viene visualizzata un pagina di conferma.</span><span class="sxs-lookup"><span data-stu-id="dce76-188">A confirmation page should be displayed in response.</span></span>  
  
2. <span data-ttu-id="dce76-189">Eseguire ComCalcClient.vbs da \client, nella cartella specifica della lingua.</span><span class="sxs-lookup"><span data-stu-id="dce76-189">Run ComCalcClient.vbs from \client, from under the language-specific folder.</span></span> <span data-ttu-id="dce76-190">L'attività del client viene visualizzata nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="dce76-190">Client activity is displayed in message box windows.</span></span>  
  
3. <span data-ttu-id="dce76-191">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="dce76-191">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="dce76-192">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="dce76-192">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="dce76-193">Sul computer del servizio creare una directory virtuale denominata ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="dce76-193">On the service computer, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="dce76-194">Lo script Setupvroot.bat incluso nell'esempio può essere usato per creare la directory del disco e quella virtuale.</span><span class="sxs-lookup"><span data-stu-id="dce76-194">The Setupvroot.bat script included with the sample can be used to create the disk directory and virtual directory.</span></span>  
  
2. <span data-ttu-id="dce76-195">Copiare i file del programma del servizio da %SystemDrive%\Inetpub\wwwroot\servicemodelsamples nella directory virtuale di ServiceModelSamples nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-195">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service computer.</span></span> <span data-ttu-id="dce76-196">Verificare di includere i file nella directory \bin.</span><span class="sxs-lookup"><span data-stu-id="dce76-196">Be sure to include the files in the \bin directory.</span></span>  
  
3. <span data-ttu-id="dce76-197">Copiare il file script del client dalla cartella \client, nella cartella specifica della lingua, ne computer client.</span><span class="sxs-lookup"><span data-stu-id="dce76-197">Copy the client script file from the \client folder, under the language-specific folder, to the client computer.</span></span>  
  
4. <span data-ttu-id="dce76-198">Nel file script modificare il valore dell'indirizzo della definizione dell'endpoint affinché corrisponda al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="dce76-198">In the script file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="dce76-199">Nell'indirizzo sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="dce76-199">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
5. <span data-ttu-id="dce76-200">Copiare il file WSDL nel computer client.</span><span class="sxs-lookup"><span data-stu-id="dce76-200">Copy the WSDL file to the client computer.</span></span> <span data-ttu-id="dce76-201">Nel file WSDL, serviceWsdl.xml, sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo nell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="dce76-201">In the WSDL file, serviceWsdl.xml, replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
6. <span data-ttu-id="dce76-202">Copiare la libreria Client.dll dalla cartella \client\bin\, nella cartella specifica della lingua, a una directory sul computer client.</span><span class="sxs-lookup"><span data-stu-id="dce76-202">Copy the Client.dll library from the \client\bin folder, under the language-specific folder, to a directory on the client computer.</span></span>  
  
7. <span data-ttu-id="dce76-203">Da un prompt dei comandi spostarsi a tale directory di destinazione sul computer client.</span><span class="sxs-lookup"><span data-stu-id="dce76-203">From a command prompt, navigate to that destination directory on the client computer.</span></span> <span data-ttu-id="dce76-204">Se si utilizza Windows Vista o [!INCLUDE[lserver](../../../../includes/lserver-md.md)], assicurarsi di eseguire il prompt dei comandi come amministratore.</span><span class="sxs-lookup"><span data-stu-id="dce76-204">If using Windows Vista or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], make sure to run the command prompt as Administrator.</span></span>  
  
8. <span data-ttu-id="dce76-205">Digitare `tlbexp.exe client.dll /out:CalcProxy.tlb` per esportare la dll in un file tlb.</span><span class="sxs-lookup"><span data-stu-id="dce76-205">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="dce76-206">È previsto un "Avviso dell'utilità di esportazione della libreria dei tipi", ma ciò non rappresenta un problema, perché il tipo generico non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dce76-206">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
9. <span data-ttu-id="dce76-207">Digitare `regasm.exe /tlb:CalcProxy.tlb client.dll` per registrare i tipi con COM.</span><span class="sxs-lookup"><span data-stu-id="dce76-207">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="dce76-208">Verificare che il percorso sia stato impostato sulla cartella che contiene `regasm.exe` prima di eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="dce76-208">Ensure that path has been set to the folder that contains `regasm.exe` before you run the command.</span></span>  
  
10. <span data-ttu-id="dce76-209">Digitare `gacutil.exe /i client.dll` per aggiungere l'assembly alla Global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="dce76-209">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="dce76-210">Verificare che il percorso sia stato impostato sulla cartella che contiene `gacutil.exe` prima di eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="dce76-210">Ensure that path has been set to the folder that contains `gacutil.exe` before you run the command.</span></span>  
  
11. <span data-ttu-id="dce76-211">Verificare che sia possibile accedere al servizio dal computer client usando un browser.</span><span class="sxs-lookup"><span data-stu-id="dce76-211">Test that you can access the service from the client computer using a browser.</span></span>  
  
12. <span data-ttu-id="dce76-212">Sul computer client avviare ComCalcClient.vbs.</span><span class="sxs-lookup"><span data-stu-id="dce76-212">On the client computer, launch ComCalcClient.vbs.</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="dce76-213">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="dce76-213">To clean up after the sample</span></span>  
  
- <span data-ttu-id="dce76-214">Per motivi di sicurezza, rimuovere la definizione della directory virtuale e le autorizzazioni concesse durante l'installazione quando si è finito di lavorare con gli esempi eseguendo il file batch denominato Cleanupvroot.bat.</span><span class="sxs-lookup"><span data-stu-id="dce76-214">For security purposes, remove the virtual directory definition and permissions granted in the setup steps when you are finished with the samples.</span></span>  

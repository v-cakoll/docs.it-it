---
title: 'Procedura dettagliata: accesso a un servizio Web tramite provider di tipi (F #)'
description: 'Informazioni su come utilizzare il provider di tipi di Web Services Description Language (WSDL) disponibile in F # 3.0 per accedere a un servizio WSDL.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 2929198172a4e9f908daa64af19208e07859263f
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a><span data-ttu-id="e10cf-104">Procedura dettagliata: Accesso a un servizio Web tramite provider di tipi</span><span class="sxs-lookup"><span data-stu-id="e10cf-104">Walkthrough: Accessing a Web Service by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="e10cf-105">Questa guida è stata scritta per F # 3.0 e verrà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="e10cf-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="e10cf-106">Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="e10cf-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="e10cf-107">I collegamenti di riferimento API richiederà a MSDN.</span><span class="sxs-lookup"><span data-stu-id="e10cf-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="e10cf-108">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="e10cf-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="e10cf-109">Questa procedura dettagliata viene illustrato come utilizzare il provider di tipi di servizi Web (WSDL, Web Services Description Language) che è disponibile in F # 3.0 per accedere a un servizio WSDL.</span><span class="sxs-lookup"><span data-stu-id="e10cf-109">This walkthrough shows you how to use the Web Services Description Language (WSDL) type provider that is available in F# 3.0 to access a WSDL service.</span></span> <span data-ttu-id="e10cf-110">In altri linguaggi .NET, generare il codice per accedere al servizio web da chiamare svcutil.exe o aggiungendo un riferimento web in, ad esempio, un progetto c# per ottenere Visual Studio chiamare svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="e10cf-110">In other .NET languages, you generate the code to access the web service by calling svcutil.exe, or by adding a web reference in, for example, a C# project to get Visual Studio to call svcutil.exe for you.</span></span> <span data-ttu-id="e10cf-111">In F # è l'opzione aggiuntiva dell'utilizzo del provider di tipo WSDL, pertanto, non appena si scrive il codice che crea il tipo WsdlService, i tipi generati e diventano disponibili.</span><span class="sxs-lookup"><span data-stu-id="e10cf-111">In F#, you have the additional option of using the WSDL type provider, so as soon as you write the code that creates the WsdlService type, the types are generated and become available.</span></span> <span data-ttu-id="e10cf-112">Questo processo si basa sul servizio sia disponibile quando si scrive il codice.</span><span class="sxs-lookup"><span data-stu-id="e10cf-112">This process relies on the service being available when you are writing the code.</span></span>

<span data-ttu-id="e10cf-113">In questa procedura dettagliata vengono illustrate le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="e10cf-113">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="e10cf-114">È necessario completare le in quest'ordine perché la procedura abbia esito positivo:</span><span class="sxs-lookup"><span data-stu-id="e10cf-114">You must complete them in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="e10cf-115">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="e10cf-115">Creating the project</span></span>
<br />

- <span data-ttu-id="e10cf-116">Configurazione del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="e10cf-116">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="e10cf-117">Chiamare il servizio web e l'elaborazione dei risultati</span><span class="sxs-lookup"><span data-stu-id="e10cf-117">Calling the web service, and processing the results</span></span>
<br />


## <a name="creating-the-project"></a><span data-ttu-id="e10cf-118">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="e10cf-118">Creating the project</span></span>
<span data-ttu-id="e10cf-119">Nel passaggio, si crea un progetto e aggiungere i riferimenti appropriati per l'utilizzo di un provider di tipi WSDL.</span><span class="sxs-lookup"><span data-stu-id="e10cf-119">In the step, you create a project and add the appropriate references to use a WSDL type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="e10cf-120">Per creare e configurare un progetto F#</span><span class="sxs-lookup"><span data-stu-id="e10cf-120">To create and set up an F# project</span></span>

1. <span data-ttu-id="e10cf-121">Aprire un nuovo progetto applicazione Console c#.</span><span class="sxs-lookup"><span data-stu-id="e10cf-121">Open a new F# Console Application project.</span></span>
<br />

2. <span data-ttu-id="e10cf-122">In **Esplora**, aprire il menu di scelta rapida per il progetto **riferimento** nodo, quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="e10cf-122">In **Solution Explorer**, open the shortcut menu for the project's **Reference** node, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="e10cf-123">Nel **assembly** area scegliere **Framework**, quindi nell'elenco di assembly disponibili, scegliere **Serialization** e  **System. ServiceModel**.</span><span class="sxs-lookup"><span data-stu-id="e10cf-123">In the **Assemblies** area, choose **Framework**, and then, in the list of available assemblies, choose **System.Runtime.Serialization** and **System.ServiceModel**.</span></span>
<br />

4. <span data-ttu-id="e10cf-124">Nel **assembly** area scegliere **estensioni**.</span><span class="sxs-lookup"><span data-stu-id="e10cf-124">In the **Assemblies** area, choose **Extensions**.</span></span>
<br />

5. <span data-ttu-id="e10cf-125">Nell'elenco di assembly disponibili, scegliere **Typeproviders**, quindi scegliere il **OK** pulsante per aggiungere riferimenti a questi assembly.</span><span class="sxs-lookup"><span data-stu-id="e10cf-125">In the list of available assemblies, choose **FSharp.Data.TypeProviders**, and then choose the **OK** button to add references to these assemblies.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="e10cf-126">Configurazione del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="e10cf-126">Configuring the type provider</span></span>
<span data-ttu-id="e10cf-127">In questo passaggio, utilizzare il provider di tipi WSDL per generare i tipi per il servizio web TerraServer.</span><span class="sxs-lookup"><span data-stu-id="e10cf-127">In this step, you use the WSDL type provider to generate types for the TerraServer web service.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="e10cf-128">Per configurare il provider di tipi e generare i tipi</span><span class="sxs-lookup"><span data-stu-id="e10cf-128">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="e10cf-129">Aggiungere la seguente riga di codice per aprire lo spazio dei nomi del provider di tipo.</span><span class="sxs-lookup"><span data-stu-id="e10cf-129">Add the following line of code to open the type provider namespace.</span></span>
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. <span data-ttu-id="e10cf-130">Aggiungere la seguente riga di codice di richiamare il provider di tipi con un servizio web.</span><span class="sxs-lookup"><span data-stu-id="e10cf-130">Add the following line of code to invoke the type provider with a web service.</span></span> <span data-ttu-id="e10cf-131">In questo esempio, utilizzare il servizio web TerraServer.</span><span class="sxs-lookup"><span data-stu-id="e10cf-131">In this example, use the TerraServer web service.</span></span>
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "https://terraserver-usa.com/TerraService2.asmx?WSDL" https://msrmaps.com/TerraService2.asmx?WSDL">
```

  <span data-ttu-id="e10cf-132">Se l'URI del servizio è errata o se il servizio è inattivo o non sta eseguendo, viene visualizzata una sottolineatura ondulata rossa sotto questa riga di codice.</span><span class="sxs-lookup"><span data-stu-id="e10cf-132">A red squiggle appears under this line of code if the service URI is misspelled or if the service itself is down or isn’t performing.</span></span> <span data-ttu-id="e10cf-133">Se si sceglie il codice, un messaggio di errore viene descritto il problema.</span><span class="sxs-lookup"><span data-stu-id="e10cf-133">If you point to the code, an error message describes the problem.</span></span> <span data-ttu-id="e10cf-134">È possibile trovare le stesse informazioni nel **elenco errori** finestra o nel **finestra di Output** al termine della compilazione.</span><span class="sxs-lookup"><span data-stu-id="e10cf-134">You can find the same information in the **Error List** window or in the **Output Window** after you build.</span></span>
<br />  <span data-ttu-id="e10cf-135">Esistono due modi per specificare le impostazioni di configurazione per una connessione di WSDL, utilizzando il file app. config per il progetto oppure utilizzando i parametri di tipo statico nella dichiarazione del tipo di provider.</span><span class="sxs-lookup"><span data-stu-id="e10cf-135">There are two ways to specify configuration settings for a WSDL connection, by using the app.config file for the project, or by using the static type parameters in the type provider declaration.</span></span> <span data-ttu-id="e10cf-136">È possibile utilizzare svcutil.exe per generare gli elementi di file di configurazione appropriato.</span><span class="sxs-lookup"><span data-stu-id="e10cf-136">You can use svcutil.exe to generate appropriate configuration file elements.</span></span> <span data-ttu-id="e10cf-137">Per ulteriori informazioni sull'utilizzo svcutil.exe per generare informazioni di configurazione per un servizio web, vedere [strumento ServiceModel Metadata Utility &#40;Svcutil.exe&#41;](https://msdn.microsoft.com/library/aa347733.aspx).</span><span class="sxs-lookup"><span data-stu-id="e10cf-137">For more information about using svcutil.exe to generate configuration information for a web service, see [ServiceModel Metadata Utility Tool &#40;Svcutil.exe&#41;](https://msdn.microsoft.com/library/aa347733.aspx).</span></span> <span data-ttu-id="e10cf-138">Per una descrizione completa dei parametri di tipo statico per il provider di tipi WSDL, vedere [Provider di tipi WsdlService](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="e10cf-138">For a full description of the static type parameters for the WSDL type provider, see [WsdlService Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span></span>
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a><span data-ttu-id="e10cf-139">Chiamare il servizio web e l'elaborazione dei risultati</span><span class="sxs-lookup"><span data-stu-id="e10cf-139">Calling the web service, and processing the results</span></span>
<span data-ttu-id="e10cf-140">Ciascun servizio web dispone di un proprio set di tipi che sono usati come parametri per le chiamate di metodo.</span><span class="sxs-lookup"><span data-stu-id="e10cf-140">Each web service has its own set of types that are used as parameters for its method calls.</span></span> <span data-ttu-id="e10cf-141">In questo passaggio, questi parametri per la preparazione, chiama un metodo web e di elaborare le informazioni che viene restituito.</span><span class="sxs-lookup"><span data-stu-id="e10cf-141">In this step, you prepare these parameters, call a web method, and process the information that it returns.</span></span>


#### <a name="to-call-the-web-service-and-process-the-results"></a><span data-ttu-id="e10cf-142">Per chiamare il servizio web e per elaborare i risultati</span><span class="sxs-lookup"><span data-stu-id="e10cf-142">To call the web service, and process the results</span></span>

1. <span data-ttu-id="e10cf-143">Il servizio web potrebbe essere previsto un timeout o smettere di funzionare, pertanto è consigliabile includere una chiamata al servizio web in un blocco di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e10cf-143">The web service might time out or stop functioning, so you should include the web service call in an exception handling block.</span></span> <span data-ttu-id="e10cf-144">Scrivere il codice seguente per tentare di ottenere dati dal servizio web.</span><span class="sxs-lookup"><span data-stu-id="e10cf-144">Write the following code to try to get data from the web service.</span></span>
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

<span data-ttu-id="e10cf-145">Si noti che è creare i tipi di dati che sono necessari per il servizio web, ad esempio **sul posto** e **percorso**, come i tipi annidati di WsdlService digitare **serie**.</span><span class="sxs-lookup"><span data-stu-id="e10cf-145">Notice that you create the data types that are needed for the web service, such as **Place** and **Location**, as nested types under the WsdlService type **TerraService**.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="e10cf-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e10cf-146">See Also</span></span>
[<span data-ttu-id="e10cf-147">Provider di tipi WsdlService</span><span class="sxs-lookup"><span data-stu-id="e10cf-147">WsdlService Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[<span data-ttu-id="e10cf-148">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="e10cf-148">Type Providers</span></span>](index.md)

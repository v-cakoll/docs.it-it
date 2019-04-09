---
title: 'Procedura: Migliorare il tempo di avvio di applicazioni client WCF usando XmlSerializer'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: dfc3dc8247a25442511d422192fea4f49bee5d92
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169806"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="8aab1-102">Procedura: Migliorare il tempo di avvio di applicazioni client WCF usando XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="8aab1-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>
<span data-ttu-id="8aab1-103">I servizi e le applicazioni client che utilizzano tipi di dati serializzabili tramite <xref:System.Xml.Serialization.XmlSerializer> generano e compilano il codice di serializzazione per tali dati in fase di esecuzione, il che può rallentare le prestazioni all'avvio.</span><span class="sxs-lookup"><span data-stu-id="8aab1-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8aab1-104">Un codice di serializzazione pregenerato può essere utilizzato solamente nelle applicazioni client e non nei servizi.</span><span class="sxs-lookup"><span data-stu-id="8aab1-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="8aab1-105">Il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) può migliorare le prestazioni di avvio per queste applicazioni generando il codice di serializzazione necessario dagli assembly compilati per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8aab1-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="8aab1-106">Svcutil.exe genera codice di serializzazione per tutti i tipi di dati utilizzati nei contratti di servizio nell'assembly dell'applicazione compilata che può essere serializzato utilizzando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8aab1-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="8aab1-107">I contratti del servizio e dell'operazione che utilizzano <xref:System.Xml.Serialization.XmlSerializer> sono contrassegnati con <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8aab1-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="8aab1-108">Per generare il codice di serializzazione XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="8aab1-108">To generate XmlSerializer serialization code</span></span>  
  
1.  <span data-ttu-id="8aab1-109">Compilare il codice del servizio o del client in uno o più assembly.</span><span class="sxs-lookup"><span data-stu-id="8aab1-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2.  <span data-ttu-id="8aab1-110">Aprire un prompt dei comandi SDK.</span><span class="sxs-lookup"><span data-stu-id="8aab1-110">Open an SDK command prompt.</span></span>  
  
3.  <span data-ttu-id="8aab1-111">Al prompt dei comandi, avviare lo strumento Svcutil.exe usando il formato seguente.</span><span class="sxs-lookup"><span data-stu-id="8aab1-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="8aab1-112">L'argomento `assemblyPath` specifica il percorso di un assembly che contiene tipi di contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="8aab1-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="8aab1-113">Svcutil.exe genera codice di serializzazione per tutti i tipi di dati utilizzati nei contratti di servizio nell'assembly dell'applicazione compilata che può essere serializzato utilizzando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8aab1-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="8aab1-114">Svcutil.exe può generare solo codice di serializzazione C#.</span><span class="sxs-lookup"><span data-stu-id="8aab1-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="8aab1-115">Viene generato un file di codice sorgente per ogni assembly di input.</span><span class="sxs-lookup"><span data-stu-id="8aab1-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="8aab1-116">Non è possibile usare la **/language** switch per modificare la lingua del codice generato.</span><span class="sxs-lookup"><span data-stu-id="8aab1-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="8aab1-117">Per specificare il percorso agli assembly dipendenti, usare il **/Reference** opzione.</span><span class="sxs-lookup"><span data-stu-id="8aab1-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4.  <span data-ttu-id="8aab1-118">Rendere il codice di serializzazione generato disponibile all'applicazione utilizzando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8aab1-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1.  <span data-ttu-id="8aab1-119">Compilare il codice di serializzazione generato in un assembly separato con il nome [*assembly originale*]. XmlSerializers. dll (ad esempio, XmlSerializers).</span><span class="sxs-lookup"><span data-stu-id="8aab1-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="8aab1-120">L'applicazione deve essere in grado di caricare l'assembly che deve essere firmato con la stessa chiave dell'assembly originale.</span><span class="sxs-lookup"><span data-stu-id="8aab1-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="8aab1-121">Se si ricompila l'assembly originale, è necessario rigenerare l'assembly di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="8aab1-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2.  <span data-ttu-id="8aab1-122">Compilare il codice di serializzazione generato in un assembly separato e utilizzare <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> sul contratto di servizio che utilizza <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8aab1-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="8aab1-123">Impostare le proprietà <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> per puntare all'assembly di serializzazione compilato.</span><span class="sxs-lookup"><span data-stu-id="8aab1-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3.  <span data-ttu-id="8aab1-124">Compilare il codice di serializzazione generato nell'assembly dell'applicazione e aggiungere <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> al contratto di servizio che utilizza <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8aab1-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="8aab1-125">Non impostare le proprietà <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="8aab1-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="8aab1-126">L'assembly corrente viene considerato automaticamente l'assembly di serializzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="8aab1-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="8aab1-127">Per generare il codice di serializzazione XmlSerializer in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8aab1-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1.  <span data-ttu-id="8aab1-128">Creare il servizio WCF e il client progetti in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8aab1-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="8aab1-129">Quindi, aggiungere un riferimento al servizio nel progetto client.</span><span class="sxs-lookup"><span data-stu-id="8aab1-129">Then, add a service reference to the client project.</span></span>  
  
2.  <span data-ttu-id="8aab1-130">Aggiungere un <xref:System.ServiceModel.XmlSerializerFormatAttribute> al contratto di servizio nel *reference.cs* file nel progetto dell'app client sotto **serviceReference** -> **svcmap** .</span><span class="sxs-lookup"><span data-stu-id="8aab1-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="8aab1-131">Si noti che è necessario visualizzare tutti i file in **Esplora soluzioni** per visualizzare questi file.</span><span class="sxs-lookup"><span data-stu-id="8aab1-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3.  <span data-ttu-id="8aab1-132">Compilare l'app client.</span><span class="sxs-lookup"><span data-stu-id="8aab1-132">Build the client app.</span></span>  
  
4.  <span data-ttu-id="8aab1-133">Usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per creare un serializzatore pregenerato *cs* file usando il comando:</span><span class="sxs-lookup"><span data-stu-id="8aab1-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="8aab1-134">L'argomento assemblyPath specifica il percorso dell'assembly client WCF.</span><span class="sxs-lookup"><span data-stu-id="8aab1-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="8aab1-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8aab1-135">Such as:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="8aab1-136">Il *WCFClient.XmlSerializers.dll.cs* verrà generati file.</span><span class="sxs-lookup"><span data-stu-id="8aab1-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5.  <span data-ttu-id="8aab1-137">Compilare l'assembly di serializzazione generato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8aab1-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="8aab1-138">In base all'esempio nel passaggio precedente, il comando di compilazione sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="8aab1-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="8aab1-139">Assicurarsi che il generato *WCFClient.XmlSerializers.dll* è nella stessa directory dell'App client, ovvero *WCFClient.exe* in questo caso.</span><span class="sxs-lookup"><span data-stu-id="8aab1-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6.  <span data-ttu-id="8aab1-140">Eseguire l'app client come di consueto.</span><span class="sxs-lookup"><span data-stu-id="8aab1-140">Run the client app as usual.</span></span> <span data-ttu-id="8aab1-141">Verrà utilizzato l'assembly di serializzazione generato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8aab1-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aab1-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="8aab1-142">Example</span></span>  
 <span data-ttu-id="8aab1-143">Nel comando seguente vengono generati i tipi di serializzazione per i tipi `XmlSerializer` utilizzati da qualsiasi contratto di servizio nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8aab1-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="8aab1-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aab1-144">See also</span></span>

- [<span data-ttu-id="8aab1-145">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="8aab1-145">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)

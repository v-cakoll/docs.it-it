---
title: 'Procedura: registrare e configurare un moniker servizio'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: c68ca0f7c95515a0552b7003454dd87804176d3d
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212208"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a><span data-ttu-id="38644-102">Procedura: registrare e configurare un moniker servizio</span><span class="sxs-lookup"><span data-stu-id="38644-102">How to: Register and Configure a Service Moniker</span></span>
<span data-ttu-id="38644-103">Prima di utilizzare il moniker del servizio Windows Communication Foundation (WCF) in un'applicazione COM con un contratto tipizzato, è necessario registrare i tipi con attributi necessari con COM e configurare l'applicazione COM e il moniker con l'associazione obbligatoria configurazione.</span><span class="sxs-lookup"><span data-stu-id="38644-103">Before using the Windows Communication Foundation (WCF) service moniker within a COM application with a typed contract, you must register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
### <a name="to-register-the-required-attributed-types-with-com"></a><span data-ttu-id="38644-104">Per registrare i tipi con attributi necessari con COM</span><span class="sxs-lookup"><span data-stu-id="38644-104">To register the required attributed types with COM</span></span>  
  
1. <span data-ttu-id="38644-105">Utilizzare lo strumento [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per recuperare il contratto di metadati dal servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="38644-105">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool to retrieve the metadata contract from the WCF service.</span></span> <span data-ttu-id="38644-106">Viene generato il codice sorgente per un assembly client WCF e un file di configurazione dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="38644-106">This generates the source code for a WCF client assembly and a client application configuration file.</span></span>  
  
2. <span data-ttu-id="38644-107">Assicurarsi che i tipi nell'assembly siano contrassegnati come `ComVisible`.</span><span class="sxs-lookup"><span data-stu-id="38644-107">Ensure that the types in the assembly are marked as `ComVisible`.</span></span> <span data-ttu-id="38644-108">A tale scopo, aggiungere l'attributo seguente al file AssemblyInfo.cs nel progetto di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38644-108">To do so, add the following attribute to the AssemblyInfo.cs file in your Visual Studio project.</span></span>  
  
    ```csharp
    [assembly: ComVisible(true)]  
    ```  
  
3. <span data-ttu-id="38644-109">Compilare il client WCF gestito come assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="38644-109">Compile the managed WCF client as a strong-named assembly.</span></span> <span data-ttu-id="38644-110">Ciò richiede una firma con una coppia di chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="38644-110">This requires signing with a cryptographic key pair.</span></span> <span data-ttu-id="38644-111">Per altre informazioni, vedere [Firma di un assembly con un nome sicuro](../../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="38644-111">For more information, see [Signing an Assembly with a Strong Name](../../../standard/assembly/sign-strong-name.md).</span></span>  
  
4. <span data-ttu-id="38644-112">Usare lo strumento di registrazione degli assembly (Regasm.exe) con l'opzione `/tlb`, per registrare i tipi nell'assembly con COM.</span><span class="sxs-lookup"><span data-stu-id="38644-112">Use the Assembly Registration (Regasm.exe) tool with the `/tlb` option to register the types in the assembly with COM.</span></span>  
  
5. <span data-ttu-id="38644-113">Usare lo strumento della cache di assembly globale (Gacutil.exe) per aggiungere l'assembly alla cache di assembly globale.</span><span class="sxs-lookup"><span data-stu-id="38644-113">Use the Global Assembly Cache (Gacutil.exe) tool to add the assembly to the global assembly cache.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="38644-114">La firma e l'aggiunta dell'assembly alla cache di assembly globale sono passaggi facoltativi, che possono però semplificare il processo di caricamento dell'assembly dal percorso corretto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="38644-114">Signing the assembly and adding it to the Global Assembly Cache are optional steps, but they can simplify the process of loading the assembly from the correct location at runtime.</span></span>  
  
### <a name="to-configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a><span data-ttu-id="38644-115">Per configurare l'applicazione COM e il moniker con la configurazione dell'associazione necessaria</span><span class="sxs-lookup"><span data-stu-id="38644-115">To configure the COM application and the moniker with the required binding configuration</span></span>  
  
- <span data-ttu-id="38644-116">Posizionare le definizioni di binding (generate dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) nel file di configurazione dell'applicazione client generato nel file di configurazione dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="38644-116">Place the binding definitions (generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in the generated client application configuration file) in the client application's configuration file.</span></span> <span data-ttu-id="38644-117">Ad esempio, per il file eseguibile di Visual Basic 6.0 denominato CallCenterClient.exe, la configurazione deve essere posizionata in un file denominato CallCenterConfig.exe.config all'interno della stessa directory del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="38644-117">For example, for a Visual Basic 6.0 executable named CallCenterClient.exe, the configuration should be placed in a file named CallCenterConfig.exe.config within the same directory as the executable.</span></span> <span data-ttu-id="38644-118">L'applicazione client può ora usare il moniker.</span><span class="sxs-lookup"><span data-stu-id="38644-118">The client application can now use the moniker.</span></span> <span data-ttu-id="38644-119">Si noti che la configurazione dell'associazione non è necessaria se si utilizza uno dei tipi di binding standard forniti da WCF.</span><span class="sxs-lookup"><span data-stu-id="38644-119">Note that the binding configuration is not required if using one of the standard binding types provided by WCF.</span></span>  
  
     <span data-ttu-id="38644-120">Viene registrato il tipo seguente.</span><span class="sxs-lookup"><span data-stu-id="38644-120">The following type is registered.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
  
    [ServiceContract]   
    public interface IMathService   
    {  
    [OperationContract]  
    public int Add(int x, int y);  
    [OperationContract]  
    public int Subtract(int x, int y);  
    }  
    ```  
  
     <span data-ttu-id="38644-121">L'applicazione viene esposta usando un'associazione `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="38644-121">The application is exposed using a `wsHttpBinding` binding.</span></span> <span data-ttu-id="38644-122">Per il tipo e la configurazione dell'applicazione specificati, vengono usate le stringhe del moniker di esempio seguenti.</span><span class="sxs-lookup"><span data-stu-id="38644-122">For the given type and application configuration, the following example moniker strings are used.</span></span>  
  
    ``` 
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1  
    ```  
  
     `or`  
  
    ``` 
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}  
    ```  
  
     <span data-ttu-id="38644-123">È possibile usare entrambe le stringhe del moniker dall'interno dell'applicazione Visual Basic 6.0, dopo avere aggiunto un riferimento all'assembly contenente i tipi `IMathService`, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="38644-123">You can use either of these moniker strings from within a Visual Basic 6.0 application, after adding a reference to the assembly that contains the `IMathService` types, as shown in the following sample code.</span></span>  
  
    ```vb
    Dim MathProxy As IMathService  
    Dim result As Integer  
  
    Set MathProxy = GetObject( _  
            "service4:address=http://localhost/MathService, _  
            binding=wsHttpBinding, _  
            bindingConfiguration=Binding1")  
  
    result = MathProxy.Add(3, 5)  
    ```  
  
     <span data-ttu-id="38644-124">In questo esempio, la definizione per la configurazione dell'associazione `Binding1` viene archiviata in un file di configurazione adeguatamente denominato per l'applicazione client, ad esempio vb6appname.exe.config.</span><span class="sxs-lookup"><span data-stu-id="38644-124">In this example, the definition for the binding configuration `Binding1` is stored in a suitably named configuration file for the client application, such as vb6appname.exe.config.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="38644-125">È possibile usare codice simile in C#, C++ o in qualsiasi altra applicazione del linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="38644-125">You can use similar code in a C#, a C++, or any other .NET Language application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="38644-126">Se il formato del moniker non è valido o il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.</span><span class="sxs-lookup"><span data-stu-id="38644-126">: If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error of "Invalid Syntax".</span></span> <span data-ttu-id="38644-127">Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="38644-127">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
     <span data-ttu-id="38644-128">Sebbene questo argomento sia incentrato sull'utilizzo del moniker del servizio dal codice Visual Basic 6,0, è possibile utilizzare un moniker di servizio da altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="38644-128">Although this topic focuses on using the service moniker from Visual Basic 6.0 code, you can use a service moniker from other languages.</span></span> <span data-ttu-id="38644-129">Quando si usa un moniker da codice C++, l'assembly generato da Svcutil.exe deve essere importato con "no_namespace named_guids raw_interfaces_only", come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="38644-129">When using a moniker from C++ code the Svcutil.exe generated assembly should be imported with "no_namespace named_guids raw_interfaces_only" as shown in the following code.</span></span>  
  
    ```cpp
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     <span data-ttu-id="38644-130">Ciò modifica le definizioni dell'interfaccia importate, in modo che tutti i metodi restituiscano un `HResult`.</span><span class="sxs-lookup"><span data-stu-id="38644-130">This modifies the imported interface definitions so that all methods return an `HResult`.</span></span> <span data-ttu-id="38644-131">Tutti gli altri valori restituiti vengono convertiti in parametri out.</span><span class="sxs-lookup"><span data-stu-id="38644-131">Any other return values are converted into out parameters.</span></span> <span data-ttu-id="38644-132">L'esecuzione complessiva dei metodi resta la stessa.</span><span class="sxs-lookup"><span data-stu-id="38644-132">The overall execution of the methods remains the same.</span></span> <span data-ttu-id="38644-133">Questo consente di determinare la causa di un'eccezione quando si chiama un metodo sul proxy.</span><span class="sxs-lookup"><span data-stu-id="38644-133">This allows you to determine the cause of an exception when calling a method on the proxy.</span></span> <span data-ttu-id="38644-134">Questa funzionalità è disponibile solo da codice C++.</span><span class="sxs-lookup"><span data-stu-id="38644-134">This functionality is only available from C++ code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38644-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38644-135">See also</span></span>

- [<span data-ttu-id="38644-136">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="38644-136">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)

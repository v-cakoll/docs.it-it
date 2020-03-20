---
title: "Procedura: configurare i componenti COM basati su .NET Framework per l'attivazione senza registrazione"
ms.date: 03/30/2017
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
ms.openlocfilehash: dedf5ab51ab5cf9befb5bd183968388406df4e5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181471"
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a><span data-ttu-id="0f47f-102">Procedura: configurare i componenti COM basati su .NET Framework per l'attivazione senza registrazione</span><span class="sxs-lookup"><span data-stu-id="0f47f-102">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>
<span data-ttu-id="0f47f-103">L'attivazione senza registrazione per i componenti basati su .NET Framework risulta solo leggermente più complessa rispetto a quella per i componenti COM.</span><span class="sxs-lookup"><span data-stu-id="0f47f-103">Registration-free activation for .NET Framework-based components is only slightly more complicated than it is for COM components.</span></span> <span data-ttu-id="0f47f-104">La configurazione richiede due manifesti:</span><span class="sxs-lookup"><span data-stu-id="0f47f-104">The setup requires two manifests:</span></span>  
  
- <span data-ttu-id="0f47f-105">Per identificare il componente gestito, le applicazioni COM devono disporre di un manifesto dell'applicazione di tipo Win32.</span><span class="sxs-lookup"><span data-stu-id="0f47f-105">COM applications must have a Win32-style application manifest to identify the managed component.</span></span>  
  
- <span data-ttu-id="0f47f-106">I componenti basati su .NET Framework devono disporre di un manifesto del componente per le informazioni sull'attivazione necessarie in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0f47f-106">.NET Framework-based components must have a component manifest for activation information needed at run time.</span></span>  
  
 <span data-ttu-id="0f47f-107">Questo argomento descrive come associare un manifesto dell'applicazione a un'applicazione, come associare un manifesto del componente a un componente e come incorporare un manifesto del componente in un assembly.</span><span class="sxs-lookup"><span data-stu-id="0f47f-107">This topic describes how to associate an application manifest with an application; associate a component manifest with a component; and embed a component manifest in an assembly.</span></span>  
  
### <a name="to-create-an-application-manifest"></a><span data-ttu-id="0f47f-108">Per creare un manifesto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0f47f-108">To create an application manifest</span></span>  
  
1. <span data-ttu-id="0f47f-109">Usando un editor XML, creare o modificare il manifesto dell'applicazione di proprietà dell'applicazione COM che interagisce con uno o più componenti gestiti.</span><span class="sxs-lookup"><span data-stu-id="0f47f-109">Using an XML editor, create (or modify) the application manifest owned by the COM application that is interoperating with one or more managed components.</span></span>  
  
2. <span data-ttu-id="0f47f-110">Inserire l'intestazione standard seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="0f47f-110">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     <span data-ttu-id="0f47f-111">Per informazioni sugli elementi del manifesto e sui relativi attributi, vedere [Application Manifests](/windows/desktop/SbsCs/application-manifests) (Manifesti delle applicazioni).</span><span class="sxs-lookup"><span data-stu-id="0f47f-111">For information about manifest elements and their attributes, see [Application Manifests](/windows/desktop/SbsCs/application-manifests).</span></span>  
  
3. <span data-ttu-id="0f47f-112">Identificare il proprietario del manifesto.</span><span class="sxs-lookup"><span data-stu-id="0f47f-112">Identify the owner of the manifest.</span></span> <span data-ttu-id="0f47f-113">Nell'esempio seguente il proprietario del file manifesto è `myComApp` versione 1.</span><span class="sxs-lookup"><span data-stu-id="0f47f-113">In the following example, `myComApp` version 1 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="msil"
      />  
    ```  
  
4. <span data-ttu-id="0f47f-114">Identificare gli assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="0f47f-114">Identify dependent assemblies.</span></span> <span data-ttu-id="0f47f-115">Nell'esempio seguente, `myComApp` dipende da `myManagedComp`.</span><span class="sxs-lookup"><span data-stu-id="0f47f-115">In the following example, `myComApp` depends on `myManagedComp`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="x86"
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myManagedComp"
                        version="6.0.0.0"
                        processorArchitecture="X86"
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5. <span data-ttu-id="0f47f-116">Salvare il file manifesto assegnando un nome a questo.</span><span class="sxs-lookup"><span data-stu-id="0f47f-116">Save and name the manifest file.</span></span> <span data-ttu-id="0f47f-117">Il nome di un manifesto dell'applicazione è costituito dal nome dell'eseguibile dell'assembly seguito dall'estensione manifest.</span><span class="sxs-lookup"><span data-stu-id="0f47f-117">The name of an application manifest is the name of the assembly executable followed by the .manifest extension.</span></span> <span data-ttu-id="0f47f-118">Il nome file del manifesto dell'applicazione per myComApp.exe, ad esempio, è myComApp.exe.manifest.</span><span class="sxs-lookup"><span data-stu-id="0f47f-118">For example, the application manifest file name for myComApp.exe is myComApp.exe.manifest.</span></span>  
  
 <span data-ttu-id="0f47f-119">Un manifesto dell'applicazione può essere installato nella stessa directory dell'applicazione COM.</span><span class="sxs-lookup"><span data-stu-id="0f47f-119">You can install an application manifest in the same directory as the COM application.</span></span> <span data-ttu-id="0f47f-120">In alternativa, può essere aggiunto come risorsa al file EXE dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f47f-120">Alternatively, you can add it as a resource to the application's .exe file.</span></span> <span data-ttu-id="0f47f-121">Per altre informazioni, vedere [About Side-by-Side Assemblies](/windows/desktop/SbsCs/about-side-by-side-assemblies-) (Informazioni sugli assembly side-by-side).</span><span class="sxs-lookup"><span data-stu-id="0f47f-121">For additional information, For more information, see [About Side-by-Side Assemblies](/windows/desktop/SbsCs/about-side-by-side-assemblies-).</span></span>  
  
#### <a name="to-create-a-component-manifest"></a><span data-ttu-id="0f47f-122">Per creare un manifesto del componente</span><span class="sxs-lookup"><span data-stu-id="0f47f-122">To create a component manifest</span></span>  
  
1. <span data-ttu-id="0f47f-123">Tramite un editor XML, creare un manifesto del componente per descrivere l'assembly gestito.</span><span class="sxs-lookup"><span data-stu-id="0f47f-123">Using an XML editor, create a component manifest to describe the managed assembly.</span></span>  
  
2. <span data-ttu-id="0f47f-124">Inserire l'intestazione standard seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="0f47f-124">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3. <span data-ttu-id="0f47f-125">Identificare il proprietario del file.</span><span class="sxs-lookup"><span data-stu-id="0f47f-125">Identify the owner of the file.</span></span> <span data-ttu-id="0f47f-126">L'elemento `<assemblyIdentity>` dell'elemento `<dependentAssembly>` nel file manifesto dell'applicazione deve corrispondere a quello contenuto nel manifesto del componente.</span><span class="sxs-lookup"><span data-stu-id="0f47f-126">The `<assemblyIdentity>` element of the `<dependentAssembly>` element in application manifest file must match the one in the component manifest.</span></span> <span data-ttu-id="0f47f-127">Nell'esempio seguente il proprietario del file manifesto è `myManagedComp` versione 1.2.3.4.</span><span class="sxs-lookup"><span data-stu-id="0f47f-127">In the following example, `myManagedComp` version 1.2.3.4 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4. <span data-ttu-id="0f47f-128">Identificare ogni classe nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0f47f-128">Identify each class in the assembly.</span></span> <span data-ttu-id="0f47f-129">Usare l'elemento `<clrClass>` per identificare in modo univoco ogni classe nell'assembly gestito.</span><span class="sxs-lookup"><span data-stu-id="0f47f-129">Use the `<clrClass>` element to uniquely identify each class in the managed assembly.</span></span> <span data-ttu-id="0f47f-130">L'elemento, che costituisce un sottoelemento di `<assembly>` dispone degli attributi descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0f47f-130">The element, which is a subelement of the `<assembly>` element, has the attributes described in the following table.</span></span>  
  
    |<span data-ttu-id="0f47f-131">Attributo</span><span class="sxs-lookup"><span data-stu-id="0f47f-131">Attribute</span></span>|<span data-ttu-id="0f47f-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f47f-132">Description</span></span>|<span data-ttu-id="0f47f-133">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="0f47f-133">Required</span></span>|  
    |---------------|-----------------|--------------|  
    |`clsid`|<span data-ttu-id="0f47f-134">Identificatore che specifica la classe da attivare.</span><span class="sxs-lookup"><span data-stu-id="0f47f-134">The identifier that specifies the class to be activated.</span></span>|<span data-ttu-id="0f47f-135">Sì</span><span class="sxs-lookup"><span data-stu-id="0f47f-135">Yes</span></span>|  
    |`description`|<span data-ttu-id="0f47f-136">Stringa contenente informazioni sul componente.</span><span class="sxs-lookup"><span data-stu-id="0f47f-136">A string that informs the user about the component.</span></span> <span data-ttu-id="0f47f-137">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="0f47f-137">An empty string is the default.</span></span>|<span data-ttu-id="0f47f-138">No</span><span class="sxs-lookup"><span data-stu-id="0f47f-138">No</span></span>|  
    |`name`|<span data-ttu-id="0f47f-139">Stringa che rappresenta la classe gestita.</span><span class="sxs-lookup"><span data-stu-id="0f47f-139">A string that represents the managed class.</span></span>|<span data-ttu-id="0f47f-140">Sì</span><span class="sxs-lookup"><span data-stu-id="0f47f-140">Yes</span></span>|  
    |`progid`|<span data-ttu-id="0f47f-141">Identificatore da usare per l'attivazione con associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="0f47f-141">The identifier to be used for late-bound activation.</span></span>|<span data-ttu-id="0f47f-142">No</span><span class="sxs-lookup"><span data-stu-id="0f47f-142">No</span></span>|  
    |`threadingModel`|<span data-ttu-id="0f47f-143">Modello di threading COM.</span><span class="sxs-lookup"><span data-stu-id="0f47f-143">The COM threading model.</span></span> <span data-ttu-id="0f47f-144">"Both" è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="0f47f-144">"Both" is the default value.</span></span>|<span data-ttu-id="0f47f-145">No</span><span class="sxs-lookup"><span data-stu-id="0f47f-145">No</span></span>|  
    |`runtimeVersion`|<span data-ttu-id="0f47f-146">Specifica la versione di Common Language Runtime (CLR) da usare.</span><span class="sxs-lookup"><span data-stu-id="0f47f-146">Specifies the common language runtime (CLR) version to use.</span></span> <span data-ttu-id="0f47f-147">Se questo attributo non viene specificato e CLR non è ancora stato caricato, il componente viene caricato con l'ultimo CLR installato prima della versione 4.</span><span class="sxs-lookup"><span data-stu-id="0f47f-147">If you do not specify this attribute, and the CLR is not already loaded, the component is loaded with the latest installed CLR prior to CLR version 4.</span></span> <span data-ttu-id="0f47f-148">Se si specifica v1.0.3705, v1.1.4322 o v2.0.50727, la versione esegue automaticamente il roll forward all'ultima versione di CLR installata prima della versione 4 (di solito v2.0.50727).</span><span class="sxs-lookup"><span data-stu-id="0f47f-148">If you specify v1.0.3705, v1.1.4322, or v2.0.50727, the version automatically rolls forward to the latest installed CLR version prior to CLR version 4 (usually v2.0.50727).</span></span> <span data-ttu-id="0f47f-149">Se è già stata caricata un'altra versione di CLR ed è possibile caricare la versione specificata side-by-side in-process, la versione specificata viene caricata; in caso contrario, viene usato il CLR caricato.</span><span class="sxs-lookup"><span data-stu-id="0f47f-149">If another version of the CLR is already loaded and the specified version can be loaded side-by-side in-process, the specified version is loaded; otherwise, the loaded CLR is used.</span></span> <span data-ttu-id="0f47f-150">Ciò potrebbe causare un errore di caricamento.</span><span class="sxs-lookup"><span data-stu-id="0f47f-150">This might cause a load failure.</span></span>|<span data-ttu-id="0f47f-151">No</span><span class="sxs-lookup"><span data-stu-id="0f47f-151">No</span></span>|  
    |`tlbid`|<span data-ttu-id="0f47f-152">Identificatore della libreria dei tipi che contiene le informazioni sui tipi per la classe.</span><span class="sxs-lookup"><span data-stu-id="0f47f-152">The identifier of the type library that contains type information about the class.</span></span>|<span data-ttu-id="0f47f-153">No</span><span class="sxs-lookup"><span data-stu-id="0f47f-153">No</span></span>|  
  
     <span data-ttu-id="0f47f-154">Tutti i tag di attributo effettuano la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0f47f-154">All attribute tags are case-sensitive.</span></span> <span data-ttu-id="0f47f-155">È possibile ottenere i CLSID, i ProgID, i modelli di threading e la versione del runtime visualizzando la libreria dei tipi esportata per l'assembly con il visualizzatore oggetti OLE/COM (Oleview.exe).</span><span class="sxs-lookup"><span data-stu-id="0f47f-155">You can obtain CLSIDs, ProgIDs, threading models, and the runtime version by viewing the exported type library for the assembly with the OLE/COM ObjectViewer (Oleview.exe).</span></span>  
  
     <span data-ttu-id="0f47f-156">Nel manifesto del componente seguente vengono identificate due classi, `testClass1` e `testClass2`.</span><span class="sxs-lookup"><span data-stu-id="0f47f-156">The following component manifest identifies two classes, `testClass1` and `testClass2`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5. <span data-ttu-id="0f47f-157">Salvare il file manifesto assegnando un nome a questo.</span><span class="sxs-lookup"><span data-stu-id="0f47f-157">Save and name the manifest file.</span></span> <span data-ttu-id="0f47f-158">Il nome di un manifesto del componente è costituito dal nome della libreria dell'assembly seguito dall'estensione manifest.</span><span class="sxs-lookup"><span data-stu-id="0f47f-158">The name of a component manifest is the name of the assembly library followed by the .manifest extension.</span></span> <span data-ttu-id="0f47f-159">La libreria myManagedComp.dll, ad esempio, corrisponde a myManagedComp.manifest.</span><span class="sxs-lookup"><span data-stu-id="0f47f-159">For example, the myManagedComp.dll is myManagedComp.manifest.</span></span>  
  
 <span data-ttu-id="0f47f-160">È necessario incorporare il manifesto del componente come risorsa nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0f47f-160">You must embed the component manifest as a resource in the assembly.</span></span>  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a><span data-ttu-id="0f47f-161">Per incorporare un manifesto del componente in un assembly gestito</span><span class="sxs-lookup"><span data-stu-id="0f47f-161">To embed a component manifest in a managed assembly</span></span>  
  
1. <span data-ttu-id="0f47f-162">Creare uno script di risorse contenente l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="0f47f-162">Create a resource script that contains the following statement:</span></span>  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     <span data-ttu-id="0f47f-163">In questa istruzione `myManagedComp.manifest` rappresenta il nome del manifesto del componente da incorporare.</span><span class="sxs-lookup"><span data-stu-id="0f47f-163">In this statement, `myManagedComp.manifest` is the name of the component manifest being embedded.</span></span> <span data-ttu-id="0f47f-164">Nell'esempio, il nome file dello script è `myresource.rc`.</span><span class="sxs-lookup"><span data-stu-id="0f47f-164">For this example, the script file name is `myresource.rc`.</span></span>  
  
2. <span data-ttu-id="0f47f-165">Compilare lo script tramite il compilatore di risorse di Microsoft Windows (Rc.exe)</span><span class="sxs-lookup"><span data-stu-id="0f47f-165">Compile the script using the Microsoft Windows Resource Compiler (Rc.exe).</span></span> <span data-ttu-id="0f47f-166">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0f47f-166">At the command prompt, type the following command:</span></span>  
  
     `rc myresource.rc`  
  
     <span data-ttu-id="0f47f-167">RC.exe genera il file di risorse `myresource.res`.</span><span class="sxs-lookup"><span data-stu-id="0f47f-167">Rc.exe produces the `myresource.res` resource file.</span></span>  
  
3. <span data-ttu-id="0f47f-168">Compilare di nuovo il file di origine dell'assembly e specificare il file di risorse usando l'opzione **/win32res**:</span><span class="sxs-lookup"><span data-stu-id="0f47f-168">Compile the assembly's source file again and specify the resource file by using the **/win32res** option:</span></span>  
  
    `/win32res:myresource.res`  
  
     <span data-ttu-id="0f47f-169">Anche `myresource.res` in questo caso, è il nome del file di risorse contenente le risorse incorporate.</span><span class="sxs-lookup"><span data-stu-id="0f47f-169">Again, `myresource.res` is the name of the resource file containing embedded resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f47f-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f47f-170">See also</span></span>

- [<span data-ttu-id="0f47f-171">Interoperabilità COM senza registrazione</span><span class="sxs-lookup"><span data-stu-id="0f47f-171">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)
- <span data-ttu-id="0f47f-172">[Requisiti per l'interoperabilità COM senza registrazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0f47f-172">[Requirements for Registration-Free COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))</span></span>
- <span data-ttu-id="0f47f-173">[Configurazione dei componenti COM per l'attivazione senza registrazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0f47f-173">[Configuring COM Components for Registration-Free Activation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))</span></span>
- <span data-ttu-id="0f47f-174">[Registration-Free Activation of .NET-Based Components: A Walkthrough](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973915(v=msdn.10)) (Procedura dettagliata per l'attivazione senza registrazione di componenti basati su .NET)</span><span class="sxs-lookup"><span data-stu-id="0f47f-174">[Registration-Free Activation of .NET-Based Components: A Walkthrough](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973915(v=msdn.10))</span></span>

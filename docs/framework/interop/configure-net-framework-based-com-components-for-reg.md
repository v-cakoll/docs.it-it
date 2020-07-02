---
title: "Procedura: Configurare i componenti COM basati su .NET Framework per l'attivazione senza registrazione"
description: Configurare. Componenti COM basati su rete per l'attivazione senza registrazione. Il programma di installazione richiede un manifesto dell'applicazione di tipo Win32 e un manifesto del componente .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
ms.openlocfilehash: 5263e042bafdb886b313f05751c29de0f5715211
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622198"
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a><span data-ttu-id="bd639-104">Procedura: Configurare i componenti COM basati su .NET Framework per l'attivazione senza registrazione</span><span class="sxs-lookup"><span data-stu-id="bd639-104">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>
<span data-ttu-id="bd639-105">L'attivazione senza registrazione per i componenti basati su .NET Framework risulta solo leggermente più complessa rispetto a quella per i componenti COM.</span><span class="sxs-lookup"><span data-stu-id="bd639-105">Registration-free activation for .NET Framework-based components is only slightly more complicated than it is for COM components.</span></span> <span data-ttu-id="bd639-106">La configurazione richiede due manifesti:</span><span class="sxs-lookup"><span data-stu-id="bd639-106">The setup requires two manifests:</span></span>  
  
- <span data-ttu-id="bd639-107">Per identificare il componente gestito, le applicazioni COM devono disporre di un manifesto dell'applicazione di tipo Win32.</span><span class="sxs-lookup"><span data-stu-id="bd639-107">COM applications must have a Win32-style application manifest to identify the managed component.</span></span>  
  
- <span data-ttu-id="bd639-108">I componenti basati su .NET Framework devono disporre di un manifesto del componente per le informazioni sull'attivazione necessarie in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bd639-108">.NET Framework-based components must have a component manifest for activation information needed at run time.</span></span>  
  
 <span data-ttu-id="bd639-109">Questo argomento descrive come associare un manifesto dell'applicazione a un'applicazione, come associare un manifesto del componente a un componente e come incorporare un manifesto del componente in un assembly.</span><span class="sxs-lookup"><span data-stu-id="bd639-109">This topic describes how to associate an application manifest with an application; associate a component manifest with a component; and embed a component manifest in an assembly.</span></span>  
  
## <a name="create-an-application-manifest"></a><span data-ttu-id="bd639-110">Creare un manifesto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="bd639-110">Create an application manifest</span></span>  
  
1. <span data-ttu-id="bd639-111">Usando un editor XML, creare o modificare il manifesto dell'applicazione di proprietà dell'applicazione COM che interagisce con uno o più componenti gestiti.</span><span class="sxs-lookup"><span data-stu-id="bd639-111">Using an XML editor, create (or modify) the application manifest owned by the COM application that is interoperating with one or more managed components.</span></span>  
  
2. <span data-ttu-id="bd639-112">Inserire l'intestazione standard seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="bd639-112">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
    </assembly>
    ```  
  
     <span data-ttu-id="bd639-113">Per informazioni sugli elementi del manifesto e sui relativi attributi, vedere [Application Manifests](/windows/desktop/SbsCs/application-manifests) (Manifesti delle applicazioni).</span><span class="sxs-lookup"><span data-stu-id="bd639-113">For information about manifest elements and their attributes, see [Application Manifests](/windows/desktop/SbsCs/application-manifests).</span></span>  
  
3. <span data-ttu-id="bd639-114">Identificare il proprietario del manifesto.</span><span class="sxs-lookup"><span data-stu-id="bd639-114">Identify the owner of the manifest.</span></span> <span data-ttu-id="bd639-115">Nell'esempio seguente il proprietario del file manifesto è `myComApp` versione 1.</span><span class="sxs-lookup"><span data-stu-id="bd639-115">In the following example, `myComApp` version 1 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="msil"
      />
    </assembly>  
    ```  
  
4. <span data-ttu-id="bd639-116">Identificare gli assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="bd639-116">Identify dependent assemblies.</span></span> <span data-ttu-id="bd639-117">Nell'esempio seguente, `myComApp` dipende da `myManagedComp`.</span><span class="sxs-lookup"><span data-stu-id="bd639-117">In the following example, `myComApp` depends on `myManagedComp`.</span></span>  
  
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
  
5. <span data-ttu-id="bd639-118">Salvare il file manifesto assegnando un nome a questo.</span><span class="sxs-lookup"><span data-stu-id="bd639-118">Save and name the manifest file.</span></span> <span data-ttu-id="bd639-119">Il nome di un manifesto dell'applicazione è costituito dal nome dell'eseguibile dell'assembly seguito dall'estensione manifest.</span><span class="sxs-lookup"><span data-stu-id="bd639-119">The name of an application manifest is the name of the assembly executable followed by the .manifest extension.</span></span> <span data-ttu-id="bd639-120">Il nome file del manifesto dell'applicazione per myComApp.exe, ad esempio, è myComApp.exe.manifest.</span><span class="sxs-lookup"><span data-stu-id="bd639-120">For example, the application manifest file name for myComApp.exe is myComApp.exe.manifest.</span></span>  
  
<span data-ttu-id="bd639-121">Un manifesto dell'applicazione può essere installato nella stessa directory dell'applicazione COM.</span><span class="sxs-lookup"><span data-stu-id="bd639-121">You can install an application manifest in the same directory as the COM application.</span></span> <span data-ttu-id="bd639-122">In alternativa, può essere aggiunto come risorsa al file EXE dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bd639-122">Alternatively, you can add it as a resource to the application's .exe file.</span></span> <span data-ttu-id="bd639-123">Per ulteriori informazioni, vedere [informazioni sugli assembly affiancati](/windows/desktop/SbsCs/about-side-by-side-assemblies-).</span><span class="sxs-lookup"><span data-stu-id="bd639-123">For more information, see [About Side-by-Side Assemblies](/windows/desktop/SbsCs/about-side-by-side-assemblies-).</span></span>  
  
## <a name="create-a-component-manifest"></a><span data-ttu-id="bd639-124">Creare un manifesto del componente</span><span class="sxs-lookup"><span data-stu-id="bd639-124">Create a component manifest</span></span>  
  
1. <span data-ttu-id="bd639-125">Tramite un editor XML, creare un manifesto del componente per descrivere l'assembly gestito.</span><span class="sxs-lookup"><span data-stu-id="bd639-125">Using an XML editor, create a component manifest to describe the managed assembly.</span></span>  
  
2. <span data-ttu-id="bd639-126">Inserire l'intestazione standard seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="bd639-126">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
    </assembly>
    ```  
  
3. <span data-ttu-id="bd639-127">Identificare il proprietario del file.</span><span class="sxs-lookup"><span data-stu-id="bd639-127">Identify the owner of the file.</span></span> <span data-ttu-id="bd639-128">L'elemento `<assemblyIdentity>` dell'elemento `<dependentAssembly>` nel file manifesto dell'applicazione deve corrispondere a quello contenuto nel manifesto del componente.</span><span class="sxs-lookup"><span data-stu-id="bd639-128">The `<assemblyIdentity>` element of the `<dependentAssembly>` element in application manifest file must match the one in the component manifest.</span></span> <span data-ttu-id="bd639-129">Nell'esempio seguente il proprietario del file manifesto è `myManagedComp` versione 1.2.3.4.</span><span class="sxs-lookup"><span data-stu-id="bd639-129">In the following example, `myManagedComp` version 1.2.3.4 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />
    </assembly>
    ```  
  
4. <span data-ttu-id="bd639-130">Identificare ogni classe nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bd639-130">Identify each class in the assembly.</span></span> <span data-ttu-id="bd639-131">Usare l'elemento `<clrClass>` per identificare in modo univoco ogni classe nell'assembly gestito.</span><span class="sxs-lookup"><span data-stu-id="bd639-131">Use the `<clrClass>` element to uniquely identify each class in the managed assembly.</span></span> <span data-ttu-id="bd639-132">L'elemento, che costituisce un sottoelemento di `<assembly>` dispone degli attributi descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="bd639-132">The element, which is a subelement of the `<assembly>` element, has the attributes described in the following table.</span></span>  
  
    |<span data-ttu-id="bd639-133">Attributo</span><span class="sxs-lookup"><span data-stu-id="bd639-133">Attribute</span></span>|<span data-ttu-id="bd639-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd639-134">Description</span></span>|<span data-ttu-id="bd639-135">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="bd639-135">Required</span></span>|  
    |---------------|-----------------|--------------|  
    |`clsid`|<span data-ttu-id="bd639-136">Identificatore che specifica la classe da attivare.</span><span class="sxs-lookup"><span data-stu-id="bd639-136">The identifier that specifies the class to be activated.</span></span>|<span data-ttu-id="bd639-137">Sì</span><span class="sxs-lookup"><span data-stu-id="bd639-137">Yes</span></span>|  
    |`description`|<span data-ttu-id="bd639-138">Stringa contenente informazioni sul componente.</span><span class="sxs-lookup"><span data-stu-id="bd639-138">A string that informs the user about the component.</span></span> <span data-ttu-id="bd639-139">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="bd639-139">An empty string is the default.</span></span>|<span data-ttu-id="bd639-140">No</span><span class="sxs-lookup"><span data-stu-id="bd639-140">No</span></span>|  
    |`name`|<span data-ttu-id="bd639-141">Stringa che rappresenta la classe gestita.</span><span class="sxs-lookup"><span data-stu-id="bd639-141">A string that represents the managed class.</span></span>|<span data-ttu-id="bd639-142">Sì</span><span class="sxs-lookup"><span data-stu-id="bd639-142">Yes</span></span>|  
    |`progid`|<span data-ttu-id="bd639-143">Identificatore da usare per l'attivazione con associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="bd639-143">The identifier to be used for late-bound activation.</span></span>|<span data-ttu-id="bd639-144">No</span><span class="sxs-lookup"><span data-stu-id="bd639-144">No</span></span>|  
    |`threadingModel`|<span data-ttu-id="bd639-145">Modello di threading COM.</span><span class="sxs-lookup"><span data-stu-id="bd639-145">The COM threading model.</span></span> <span data-ttu-id="bd639-146">"Both" è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="bd639-146">"Both" is the default value.</span></span>|<span data-ttu-id="bd639-147">No</span><span class="sxs-lookup"><span data-stu-id="bd639-147">No</span></span>|  
    |`runtimeVersion`|<span data-ttu-id="bd639-148">Specifica la versione di Common Language Runtime (CLR) da usare.</span><span class="sxs-lookup"><span data-stu-id="bd639-148">Specifies the common language runtime (CLR) version to use.</span></span> <span data-ttu-id="bd639-149">Se questo attributo non viene specificato e CLR non è ancora stato caricato, il componente viene caricato con l'ultimo CLR installato prima della versione 4.</span><span class="sxs-lookup"><span data-stu-id="bd639-149">If you do not specify this attribute, and the CLR is not already loaded, the component is loaded with the latest installed CLR prior to CLR version 4.</span></span> <span data-ttu-id="bd639-150">Se si specifica v1.0.3705, v1.1.4322 o v2.0.50727, la versione esegue automaticamente il roll forward all'ultima versione di CLR installata prima della versione 4 (di solito v2.0.50727).</span><span class="sxs-lookup"><span data-stu-id="bd639-150">If you specify v1.0.3705, v1.1.4322, or v2.0.50727, the version automatically rolls forward to the latest installed CLR version prior to CLR version 4 (usually v2.0.50727).</span></span> <span data-ttu-id="bd639-151">Se è già stata caricata un'altra versione di CLR ed è possibile caricare la versione specificata side-by-side in-process, la versione specificata viene caricata; in caso contrario, viene usato il CLR caricato.</span><span class="sxs-lookup"><span data-stu-id="bd639-151">If another version of the CLR is already loaded and the specified version can be loaded side-by-side in-process, the specified version is loaded; otherwise, the loaded CLR is used.</span></span> <span data-ttu-id="bd639-152">Ciò potrebbe causare un errore di caricamento.</span><span class="sxs-lookup"><span data-stu-id="bd639-152">This might cause a load failure.</span></span>|<span data-ttu-id="bd639-153">No</span><span class="sxs-lookup"><span data-stu-id="bd639-153">No</span></span>|  
    |`tlbid`|<span data-ttu-id="bd639-154">Identificatore della libreria dei tipi che contiene le informazioni sui tipi per la classe.</span><span class="sxs-lookup"><span data-stu-id="bd639-154">The identifier of the type library that contains type information about the class.</span></span>|<span data-ttu-id="bd639-155">No</span><span class="sxs-lookup"><span data-stu-id="bd639-155">No</span></span>|  
  
     <span data-ttu-id="bd639-156">Tutti i tag di attributo effettuano la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="bd639-156">All attribute tags are case-sensitive.</span></span> <span data-ttu-id="bd639-157">È possibile ottenere i CLSID, i ProgID, i modelli di threading e la versione del runtime visualizzando la libreria dei tipi esportata per l'assembly con il visualizzatore oggetti OLE/COM (Oleview.exe).</span><span class="sxs-lookup"><span data-stu-id="bd639-157">You can obtain CLSIDs, ProgIDs, threading models, and the runtime version by viewing the exported type library for the assembly with the OLE/COM ObjectViewer (Oleview.exe).</span></span>  
  
     <span data-ttu-id="bd639-158">Nel manifesto del componente seguente vengono identificate due classi, `testClass1` e `testClass2`.</span><span class="sxs-lookup"><span data-stu-id="bd639-158">The following component manifest identifies two classes, `testClass1` and `testClass2`.</span></span>  
  
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
  
5. <span data-ttu-id="bd639-159">Salvare il file manifesto assegnando un nome a questo.</span><span class="sxs-lookup"><span data-stu-id="bd639-159">Save and name the manifest file.</span></span> <span data-ttu-id="bd639-160">Il nome di un manifesto del componente è costituito dal nome della libreria dell'assembly seguito dall'estensione manifest.</span><span class="sxs-lookup"><span data-stu-id="bd639-160">The name of a component manifest is the name of the assembly library followed by the .manifest extension.</span></span> <span data-ttu-id="bd639-161">La libreria myManagedComp.dll, ad esempio, corrisponde a myManagedComp.manifest.</span><span class="sxs-lookup"><span data-stu-id="bd639-161">For example, the myManagedComp.dll is myManagedComp.manifest.</span></span>  
  
 <span data-ttu-id="bd639-162">È necessario incorporare il manifesto del componente come risorsa nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bd639-162">You must embed the component manifest as a resource in the assembly.</span></span>  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a><span data-ttu-id="bd639-163">Per incorporare un manifesto del componente in un assembly gestito</span><span class="sxs-lookup"><span data-stu-id="bd639-163">To embed a component manifest in a managed assembly</span></span>  
  
1. <span data-ttu-id="bd639-164">Creare uno script di risorse contenente l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="bd639-164">Create a resource script that contains the following statement:</span></span>  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     <span data-ttu-id="bd639-165">In questa istruzione `myManagedComp.manifest` rappresenta il nome del manifesto del componente da incorporare.</span><span class="sxs-lookup"><span data-stu-id="bd639-165">In this statement, `myManagedComp.manifest` is the name of the component manifest being embedded.</span></span> <span data-ttu-id="bd639-166">Nell'esempio, il nome file dello script è `myresource.rc`.</span><span class="sxs-lookup"><span data-stu-id="bd639-166">For this example, the script file name is `myresource.rc`.</span></span>  
  
2. <span data-ttu-id="bd639-167">Compilare lo script tramite il compilatore di risorse di Microsoft Windows (Rc.exe)</span><span class="sxs-lookup"><span data-stu-id="bd639-167">Compile the script using the Microsoft Windows Resource Compiler (Rc.exe).</span></span> <span data-ttu-id="bd639-168">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="bd639-168">At the command prompt, type the following command:</span></span>  
  
     `rc myresource.rc`  
  
     <span data-ttu-id="bd639-169">RC.exe genera il file di risorse `myresource.res`.</span><span class="sxs-lookup"><span data-stu-id="bd639-169">Rc.exe produces the `myresource.res` resource file.</span></span>  
  
3. <span data-ttu-id="bd639-170">Compilare di nuovo il file di origine dell'assembly e specificare il file di risorse usando l'opzione **/win32res**:</span><span class="sxs-lookup"><span data-stu-id="bd639-170">Compile the assembly's source file again and specify the resource file by using the **/win32res** option:</span></span>  
  
    `/win32res:myresource.res`  
  
     <span data-ttu-id="bd639-171">Anche in `myresource.res` questo caso, è il nome del file di risorse contenente le risorse incorporate.</span><span class="sxs-lookup"><span data-stu-id="bd639-171">Again, `myresource.res` is the name of the resource file containing embedded resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd639-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd639-172">See also</span></span>

- [<span data-ttu-id="bd639-173">Interoperabilità COM senza registrazione</span><span class="sxs-lookup"><span data-stu-id="bd639-173">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)
- <span data-ttu-id="bd639-174">[Requisiti per l'interoperabilità COM senza registrazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bd639-174">[Requirements for Registration-Free COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))</span></span>
- <span data-ttu-id="bd639-175">[Configurazione dei componenti COM per l'attivazione senza registrazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bd639-175">[Configuring COM Components for Registration-Free Activation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))</span></span>
- <span data-ttu-id="bd639-176">[Registration-Free Activation of .NET-Based Components: A Walkthrough](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973915(v=msdn.10)) (Procedura dettagliata per l'attivazione senza registrazione di componenti basati su .NET)</span><span class="sxs-lookup"><span data-stu-id="bd639-176">[Registration-Free Activation of .NET-Based Components: A Walkthrough](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973915(v=msdn.10))</span></span>

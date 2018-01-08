---
title: "Procedura: Compilare un assembly su più file"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f77922d08ce17f8b8659eac0dba5a46ca33a7502
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-multifile-assembly"></a><span data-ttu-id="c8346-102">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="c8346-102">How to: Build a Multifile Assembly</span></span>
<span data-ttu-id="c8346-103">In questo articolo viene illustrato come creare un assembly su più file e viene visualizzato il codice che illustra ogni passaggio della procedura.</span><span class="sxs-lookup"><span data-stu-id="c8346-103">This article explains how to create a multifile assembly and provides code that illustrates each step in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8346-104">L'IDE di Visual Studio per C# e Visual Basic può essere utilizzato esclusivamente per creare assembly su singolo file.</span><span class="sxs-lookup"><span data-stu-id="c8346-104">The Visual Studio IDE for C# and Visual Basic can only be used to create single-file assemblies.</span></span> <span data-ttu-id="c8346-105">Per creare assembly su più file, è necessario utilizzare i compilatori della riga di comando o Visual Studio con Visual C++.</span><span class="sxs-lookup"><span data-stu-id="c8346-105">If you want to create multifile assemblies, you must use the command-line compilers or Visual Studio with Visual C++.</span></span>  
  
### <a name="to-create-a-multifile-assembly"></a><span data-ttu-id="c8346-106">Per creare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="c8346-106">To create a multifile assembly</span></span>  
  
1.  <span data-ttu-id="c8346-107">Compilare in moduli di codice tutti i file contenenti spazi dei nomi a cui fanno riferimento altri moduli dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c8346-107">Compile all files that contain namespaces referenced by other modules in the assembly into code modules.</span></span> <span data-ttu-id="c8346-108">L'estensione predefinita per i moduli di codice è .netmodule.</span><span class="sxs-lookup"><span data-stu-id="c8346-108">The default extension for code modules is .netmodule.</span></span>  
  
     <span data-ttu-id="c8346-109">Si supponga, ad esempio, che il file `Stringer` abbia uno spazio dei nomi denominato `myStringer`, che include una classe denominata `Stringer`.</span><span class="sxs-lookup"><span data-stu-id="c8346-109">For example, let's say the `Stringer` file has a namespace called `myStringer`, which includes a class called `Stringer`.</span></span> <span data-ttu-id="c8346-110">Nella classe `Stringer` è disponibile un metodo denominato `StringerMethod`, che consente di scrivere una singola riga nella console.</span><span class="sxs-lookup"><span data-stu-id="c8346-110">The `Stringer` class contains a method called `StringerMethod` that writes a single line to the console.</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]
     [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]
     [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]  
  
     <span data-ttu-id="c8346-111">Per compilare il codice, utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c8346-111">Use the following command to compile this code:</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]
     [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]
     [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]  
  
     <span data-ttu-id="c8346-112">Specificando il parametro *module* con l'opzione del compilatore **/t:** si indica che è necessario compilare il file come modulo anziché come assembly.</span><span class="sxs-lookup"><span data-stu-id="c8346-112">Specifying the *module* parameter with the **/t:** compiler option indicates that the file should be compiled as a module rather than as an assembly.</span></span> <span data-ttu-id="c8346-113">Il compilatore crea un modulo denominato `Stringer.netmodule`, che può essere aggiunto a un assembly.</span><span class="sxs-lookup"><span data-stu-id="c8346-113">The compiler produces a module called `Stringer.netmodule`, which can be added to an assembly.</span></span>  
  
2.  <span data-ttu-id="c8346-114">Compilare tutti gli altri moduli, utilizzando le opzioni di compilatore necessarie per indicare gli altri moduli a cui si fa riferimento nel codice.</span><span class="sxs-lookup"><span data-stu-id="c8346-114">Compile all other modules, using the necessary compiler options to indicate the other modules that are referenced in the code.</span></span> <span data-ttu-id="c8346-115">Questo passaggio usa l'opzione del compilatore **/addmodule**.</span><span class="sxs-lookup"><span data-stu-id="c8346-115">This step uses the **/addmodule** compiler option.</span></span>  
  
     <span data-ttu-id="c8346-116">Nell'esempio riportato di seguito un modulo di codice denominato `Client` contiene un metodo `Main` del punto di ingresso che fa riferimento a un metodo nel modulo `Stringer.dll` creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c8346-116">In the following example, a code module called `Client` has an entry point `Main` method that references a method in the `Stringer.dll` module created in step 1.</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]
     [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]
     [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]  
  
     <span data-ttu-id="c8346-117">Per compilare il codice, utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c8346-117">Use the following command to compile this code:</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]
     [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]
     [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]  
  
     <span data-ttu-id="c8346-118">Specificare l'opzione **/t:module** poiché il modulo verrà aggiunto a un assembly in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="c8346-118">Specify the **/t:module** option because this module will be added to an assembly in a future step.</span></span> <span data-ttu-id="c8346-119">Specificare l'opzione **/addmodule** poiché nel codice di `Client` sono presenti riferimenti allo spazio dei nomi creato dal codice in `Stringer.netmodule`.</span><span class="sxs-lookup"><span data-stu-id="c8346-119">Specify the **/addmodule** option because the code in `Client` references a namespace created by the code in `Stringer.netmodule`.</span></span> <span data-ttu-id="c8346-120">Il compilatore crea un modulo denominato `Client.netmodule` contenente un riferimento a un altro modulo, `Stringer.netmodule`.</span><span class="sxs-lookup"><span data-stu-id="c8346-120">The compiler produces a module called `Client.netmodule` that contains a reference to another module, `Stringer.netmodule`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c8346-121">Nei compilatori di C# e di Visual Basic viene supportata la creazione diretta di assembly su più file utilizzando le due diverse sintassi descritte di seguito.</span><span class="sxs-lookup"><span data-stu-id="c8346-121">The C# and Visual Basic compilers support directly creating multifile assemblies using the following two different syntaxes.</span></span>  
    >   
    >  -   <span data-ttu-id="c8346-122">Un assembly su due file viene creato da due compilazioni:</span><span class="sxs-lookup"><span data-stu-id="c8346-122">Two compilations create a two-file assembly:</span></span>  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]
      [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]
      [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]  
    > -   <span data-ttu-id="c8346-123">Un assembly su due file viene creato da una compilazione:</span><span class="sxs-lookup"><span data-stu-id="c8346-123">One compilation creates a two-file assembly:</span></span>  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]
      [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]
      [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]  
  
3.  <span data-ttu-id="c8346-124">Usare [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) per creare il file di output contenente il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c8346-124">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the output file that contains the assembly manifest.</span></span> <span data-ttu-id="c8346-125">In questo file sono contenute informazioni di riferimento per tutti i moduli o le risorse che fanno parte dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c8346-125">This file contains reference information for all modules or resources that are part of the assembly.</span></span>  
  
     <span data-ttu-id="c8346-126">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="c8346-126">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="c8346-127">**al** \<*nome modulo*> \<*nome modulo*> …</span><span class="sxs-lookup"><span data-stu-id="c8346-127">**al** \<*module name*> \<*module name*> …</span></span> <span data-ttu-id="c8346-128">**/main:**\<*nome metodo*> **/out:**\<*nome file*> **/target:**\<*tipo file di assembly*></span><span class="sxs-lookup"><span data-stu-id="c8346-128">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span></span>  
  
     <span data-ttu-id="c8346-129">In questo comando gli argomenti *nome modulo* specificano il nome di ogni modulo da includere nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c8346-129">In this command, the *module name* arguments specify the name of each module to include in the assembly.</span></span> <span data-ttu-id="c8346-130">L'opzione **/main:** specifica il nome del metodo che corrisponde al punto di ingresso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c8346-130">The **/main:** option specifies the method name that is the assembly's entry point.</span></span> <span data-ttu-id="c8346-131">L'opzione **/out:** specifica il nome del file di output che contiene i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c8346-131">The **/out:** option specifies the name of the output file, which contains assembly metadata.</span></span> <span data-ttu-id="c8346-132">L'opzione **/target:** specifica che l'assembly è un file eseguibile da console (file con estensione exe), un file eseguibile di Windows (file con estensione win) o una libreria (file con estensione lib).</span><span class="sxs-lookup"><span data-stu-id="c8346-132">The **/target:** option specifies that the assembly is a console application executable (.exe) file, a Windows executable (.win) file, or a library (.lib) file.</span></span>  
  
     <span data-ttu-id="c8346-133">Nell'esempio seguente l'utilità Al.exe consente di creare un assembly denominato `myAssembly.exe`, che corrisponde al file eseguibile da console.</span><span class="sxs-lookup"><span data-stu-id="c8346-133">In the following example, Al.exe creates an assembly that is a console application executable called `myAssembly.exe`.</span></span> <span data-ttu-id="c8346-134">L'applicazione è costituita da due moduli denominati `Client.netmodule` e `Stringer.netmodule` e dal file eseguibile denominato `myAssembly.exe,` contenente solo i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c8346-134">The application consists of two modules called `Client.netmodule` and `Stringer.netmodule`, and the executable file called `myAssembly.exe,` which contains only assembly metadata .</span></span> <span data-ttu-id="c8346-135">Il punto di ingresso dell'assembly è costituito dal metodo `Main` della classe `MainClientApp`, situata nel file `Client.dll`.</span><span class="sxs-lookup"><span data-stu-id="c8346-135">The entry point of the assembly is the `Main` method in the class `MainClientApp`, which is located in `Client.dll`.</span></span>  
  
    ```  
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe   
    ```  
  
     <span data-ttu-id="c8346-136">È possibile usare [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per esaminare i contenuti di un assembly o determinare se un file è un assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="c8346-136">You can use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the contents of an assembly, or determine whether a file is an assembly or a module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8346-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8346-137">See Also</span></span>  
 [<span data-ttu-id="c8346-138">Creazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="c8346-138">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="c8346-139">Procedura: Visualizzare il contenuto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="c8346-139">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 [<span data-ttu-id="c8346-140">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="c8346-140">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="c8346-141">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="c8346-141">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)

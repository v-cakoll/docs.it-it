---
title: 'Procedura: firmare un assembly con un nome sicuro'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d46694d772aed7e92f95cc26da86985d4f8b0ff
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50191064"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="32da8-102">Procedura: firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="32da8-102">How to: Sign an Assembly with a Strong Name</span></span>
<span data-ttu-id="32da8-103">Sono disponibili diversi modi per firmare un assembly con un nome sicuro:</span><span class="sxs-lookup"><span data-stu-id="32da8-103">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
-   <span data-ttu-id="32da8-104">Utilizzando la scheda di **Firma** nella finestra di dialogo **Proprietà** di un progetto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="32da8-104">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="32da8-105">Questo è il modo più semplice e più pratico per firmare un assembly con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="32da8-105">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
-   <span data-ttu-id="32da8-106">Usando [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) per collegare un modulo di codice di .NET Framework (un file con estensione netmodule) con un file di chiave.</span><span class="sxs-lookup"><span data-stu-id="32da8-106">By using the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a .netmodule file) with a key file.</span></span>  
  
-   <span data-ttu-id="32da8-107">Utilizzando attributi dell'assembly per inserire le informazioni relative al nome sicuro nel codice.</span><span class="sxs-lookup"><span data-stu-id="32da8-107">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="32da8-108">È possibile utilizzare l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> , a seconda della posizione del file di chiave da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="32da8-108">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
-   <span data-ttu-id="32da8-109">Utilizzando le opzioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="32da8-109">By using compiler options.</span></span>  
  
 <span data-ttu-id="32da8-110">Per firmare un assembly con un nome sicuro, è necessario disporre di una coppia di chiavi crittografiche.</span><span class="sxs-lookup"><span data-stu-id="32da8-110">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="32da8-111">Per altre informazioni sulla creazione di una coppia di chiavi, vedere [Procedura: Creare una coppia di chiavi pubblica/privata](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="32da8-111">For more information about creating a key pair, see [How to: Create a Public-Private Key Pair](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="32da8-112">Per creare e firmare un assembly con un nome sicuro utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="32da8-112">To create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1.  <span data-ttu-id="32da8-113">In **Esplora soluzioni**aprire il menu di scelta rapida per il progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="32da8-113">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="32da8-114">Scegliere la scheda **Firma** .</span><span class="sxs-lookup"><span data-stu-id="32da8-114">Choose the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="32da8-115">Selezionare la casella **Firma assembly** .</span><span class="sxs-lookup"><span data-stu-id="32da8-115">Select the **Sign the assembly** box.</span></span>  
  
4.  <span data-ttu-id="32da8-116">Nella casella **Scegli un file chiave con nome sicuro** scegliere **\<Sfoglia>**, quindi passare al file di chiave.</span><span class="sxs-lookup"><span data-stu-id="32da8-116">In the **Choose a strong name key file** box, choose **\<Browse…>**, and then navigate to the key file.</span></span> <span data-ttu-id="32da8-117">Per creare un nuovo file di chiave, scegliere **\<Nuovo>** e immettere il nome nella finestra di dialogo **Crea chiave con nome sicuro**.</span><span class="sxs-lookup"><span data-stu-id="32da8-117">To create a new key file, choose **\<New…>** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="32da8-118">Per creare e firmare un assembly con un nome sicuro utilizzando Assembly Linker</span><span class="sxs-lookup"><span data-stu-id="32da8-118">To create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
-   <span data-ttu-id="32da8-119">Al [prompt dei comandi di Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="32da8-119">At the [Visual Studio Command Prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="32da8-120">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="32da8-120">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  
  
     <span data-ttu-id="32da8-121">dove:</span><span class="sxs-lookup"><span data-stu-id="32da8-121">where:</span></span>  
  
     <span data-ttu-id="32da8-122">*assemblyName*</span><span class="sxs-lookup"><span data-stu-id="32da8-122">*assemblyName*</span></span>  
     <span data-ttu-id="32da8-123">Nome sicuro di assembly con firma (file .dll o .exe) che verrà generato da Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="32da8-123">The name of the strongly signed assembly (a .dll or .exe file) that Assembly Linker will emit.</span></span>  
  
     <span data-ttu-id="32da8-124">*moduleName*</span><span class="sxs-lookup"><span data-stu-id="32da8-124">*moduleName*</span></span>  
     <span data-ttu-id="32da8-125">Nome di un modulo di codice di .NET Framework (file con estensione netmodule) che include uno o più tipi.</span><span class="sxs-lookup"><span data-stu-id="32da8-125">The name of a .NET Framework code module (a .netmodule file) that includes one or more types.</span></span> <span data-ttu-id="32da8-126">È possibile creare un file .netmodule durante la compilazione del codice con l'opzione `/target:module` in C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="32da8-126">You can create a .netmodule file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>  
  
     <span data-ttu-id="32da8-127">*keyfileName*</span><span class="sxs-lookup"><span data-stu-id="32da8-127">*keyfileName*</span></span>  
     <span data-ttu-id="32da8-128">Nome del contenitore o del file che contiene la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="32da8-128">The name of the container or file that contains the key pair.</span></span> <span data-ttu-id="32da8-129">Assembly Linker interpreta un percorso relativo in relazione alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="32da8-129">Assembly Linker interprets a relative path in relationship to the current directory.</span></span>  
  
 <span data-ttu-id="32da8-130">L'esempio seguente consente di firmare l'assembly `MyAssembly.dll` con un nome sicuro utilizzando il file di chiave `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="32da8-130">The following example signs the assembly `MyAssembly.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
```  
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
 <span data-ttu-id="32da8-131">Per ulteriori informazioni sull'utilizzo di questo strumento, vedere [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="32da8-131">For more information about this tool, see [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span>  
  
#### <a name="to-sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="32da8-132">Per firmare un assembly con un nome sicuro utilizzando attributi</span><span class="sxs-lookup"><span data-stu-id="32da8-132">To sign an assembly with a strong name by using attributes</span></span>  
  
1.  <span data-ttu-id="32da8-133">Aggiungere l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> o <xref:System.Reflection.AssemblyKeyNameAttribute> al file del codice sorgente, specificando il nome del file o del contenitore contenente la coppia di chiavi da utilizzare per la firma dell'assembly con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="32da8-133">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  
  
2.  <span data-ttu-id="32da8-134">Compilare normalmente il file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="32da8-134">Compile the source code file normally.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32da8-135">Nei compilatori C# e Visual Basic vengono pubblicati avvisi del compilatore (rispettivamente CS1699 e BC41008) quando viene rilevato l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="32da8-135">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="32da8-136">È possibile ignorare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="32da8-136">You can ignore the warnings.</span></span>  
  
 <span data-ttu-id="32da8-137">Nell'esempio di codice riportato di seguito viene utilizzato l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> con un file di chiave denominato `keyfile.snk`, che si trova nella directory in cui viene compilato l'assembly.</span><span class="sxs-lookup"><span data-stu-id="32da8-137">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called `keyfile.snk`, which is located in the directory where the assembly is compiled.</span></span>  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
 <span data-ttu-id="32da8-138">È inoltre possibile ritardare la firma di un assembly durante la compilazione del file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="32da8-138">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="32da8-139">Per ulteriori informazioni, vedere [Ritardo della firma di un assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="32da8-139">For more information, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="32da8-140">Per firmare un assembly con un nome sicuro utilizzando il compilatore</span><span class="sxs-lookup"><span data-stu-id="32da8-140">To sign an assembly with a strong name by using the compiler</span></span>  
  
-   <span data-ttu-id="32da8-141">Compilare il file o i file del codice sorgente con l'opzione del compilatore `/keyfile` o `/delaysign` in C# e Visual Basic o con l'opzione del linker `/KEYFILE` o `/DELAYSIGN` in C++.</span><span class="sxs-lookup"><span data-stu-id="32da8-141">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="32da8-142">Dopo il nome di opzione, aggiungere due punti e il nome del file di chiave.</span><span class="sxs-lookup"><span data-stu-id="32da8-142">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="32da8-143">Se si utilizzano compilatori della riga di comando, è possibile copiare il file di chiave nella directory contenente i file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="32da8-143">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  
  
     <span data-ttu-id="32da8-144">Per informazioni sulla firma ritardata, vedere [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="32da8-144">For information on delay signing, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
     <span data-ttu-id="32da8-145">Nell'esempio riportato di seguito viene utilizzato il compilatore C# e viene firmato l'assembly `UtilityLibrary.dll` con un nome sicuro, utilizzando il file di chiave `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="32da8-145">The following example uses the C# compiler and signs the assembly `UtilityLibrary.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
    ```  
    csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="32da8-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32da8-146">See Also</span></span>  
- [<span data-ttu-id="32da8-147">Creazione e utilizzo degli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="32da8-147">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
- [<span data-ttu-id="32da8-148">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="32da8-148">How to: Create a Public-Private Key Pair</span></span>](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)  
- [<span data-ttu-id="32da8-149">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="32da8-149">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)  
- [<span data-ttu-id="32da8-150">Ritardo della firma di un assembly</span><span class="sxs-lookup"><span data-stu-id="32da8-150">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)  
- [<span data-ttu-id="32da8-151">Gestione delle firme di assembly e manifesti</span><span class="sxs-lookup"><span data-stu-id="32da8-151">Managing Assembly and Manifest Signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)  
- [<span data-ttu-id="32da8-152">Pagina Firma, Creazione progetti</span><span class="sxs-lookup"><span data-stu-id="32da8-152">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)

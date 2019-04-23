---
title: 'Procedura: Firmare un assembly con un nome sicuro'
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
ms.openlocfilehash: 5580b6d8af7319397ad7eb6416941c2be0dcdb76
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303432"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="554c0-102">Procedura: Firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="554c0-102">How to: Sign an Assembly with a Strong Name</span></span>
<span data-ttu-id="554c0-103">Sono disponibili diversi modi per firmare un assembly con un nome sicuro:</span><span class="sxs-lookup"><span data-stu-id="554c0-103">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
-   <span data-ttu-id="554c0-104">Utilizzando la scheda di **Firma** nella finestra di dialogo **Proprietà** di un progetto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="554c0-104">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="554c0-105">Questo è il modo più semplice e più pratico per firmare un assembly con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="554c0-105">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
-   <span data-ttu-id="554c0-106">Usando [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) per collegare un modulo di codice di .NET Framework (un file con estensione netmodule) con un file di chiave.</span><span class="sxs-lookup"><span data-stu-id="554c0-106">By using the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a .netmodule file) with a key file.</span></span>  
  
-   <span data-ttu-id="554c0-107">Utilizzando attributi dell'assembly per inserire le informazioni relative al nome sicuro nel codice.</span><span class="sxs-lookup"><span data-stu-id="554c0-107">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="554c0-108">È possibile utilizzare l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> , a seconda della posizione del file di chiave da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="554c0-108">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
-   <span data-ttu-id="554c0-109">Utilizzando le opzioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="554c0-109">By using compiler options.</span></span>  
  
 <span data-ttu-id="554c0-110">Per firmare un assembly con un nome sicuro, è necessario disporre di una coppia di chiavi crittografiche.</span><span class="sxs-lookup"><span data-stu-id="554c0-110">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="554c0-111">Per altre informazioni sulla creazione di una coppia di chiavi, vedere [Procedura: Creare una coppia di chiavi pubblica/privata](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="554c0-111">For more information about creating a key pair, see [How to: Create a Public-Private Key Pair](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="554c0-112">Per creare e firmare un assembly con un nome sicuro utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="554c0-112">To create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1. <span data-ttu-id="554c0-113">In **Esplora soluzioni**aprire il menu di scelta rapida per il progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="554c0-113">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="554c0-114">Scegliere la scheda **Firma** .</span><span class="sxs-lookup"><span data-stu-id="554c0-114">Choose the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="554c0-115">Selezionare la casella **Firma assembly** .</span><span class="sxs-lookup"><span data-stu-id="554c0-115">Select the **Sign the assembly** box.</span></span>  
  
4. <span data-ttu-id="554c0-116">Nella casella **Scegli un file chiave con nome sicuro** scegliere **\<Sfoglia>**, quindi passare al file di chiave.</span><span class="sxs-lookup"><span data-stu-id="554c0-116">In the **Choose a strong name key file** box, choose **\<Browse…>**, and then navigate to the key file.</span></span> <span data-ttu-id="554c0-117">Per creare un nuovo file di chiave, scegliere **\<Nuovo>** e immettere il nome nella finestra di dialogo **Crea chiave con nome sicuro**.</span><span class="sxs-lookup"><span data-stu-id="554c0-117">To create a new key file, choose **\<New…>** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="554c0-118">Per [ritardare la firma di un assembly](../../../docs/framework/app-domains/delay-sign-assembly.md), scegliere un file di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="554c0-118">In order to [delay sign an assembly](../../../docs/framework/app-domains/delay-sign-assembly.md), choose a public key file.</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="554c0-119">Per creare e firmare un assembly con un nome sicuro utilizzando Assembly Linker</span><span class="sxs-lookup"><span data-stu-id="554c0-119">To create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
-   <span data-ttu-id="554c0-120">Al [prompt dei comandi per gli sviluppatori per Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md), digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="554c0-120">At the [Developer Command Prompt for Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="554c0-121">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="554c0-121">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  
  
     <span data-ttu-id="554c0-122">dove:</span><span class="sxs-lookup"><span data-stu-id="554c0-122">where:</span></span>  
  
     *<span data-ttu-id="554c0-123">assemblyName</span><span class="sxs-lookup"><span data-stu-id="554c0-123">assemblyName</span></span>*  
     <span data-ttu-id="554c0-124">Nome sicuro di assembly con firma (file .dll o .exe) che verrà generato da Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="554c0-124">The name of the strongly signed assembly (a .dll or .exe file) that Assembly Linker will emit.</span></span>  
  
     *<span data-ttu-id="554c0-125">moduleName</span><span class="sxs-lookup"><span data-stu-id="554c0-125">moduleName</span></span>*  
     <span data-ttu-id="554c0-126">Nome di un modulo di codice di .NET Framework (file con estensione netmodule) che include uno o più tipi.</span><span class="sxs-lookup"><span data-stu-id="554c0-126">The name of a .NET Framework code module (a .netmodule file) that includes one or more types.</span></span> <span data-ttu-id="554c0-127">È possibile creare un file .netmodule durante la compilazione del codice con l'opzione `/target:module` in C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="554c0-127">You can create a .netmodule file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>  
  
     *<span data-ttu-id="554c0-128">keyfileName</span><span class="sxs-lookup"><span data-stu-id="554c0-128">keyfileName</span></span>*  
     <span data-ttu-id="554c0-129">Nome del contenitore o del file che contiene la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="554c0-129">The name of the container or file that contains the key pair.</span></span> <span data-ttu-id="554c0-130">Assembly Linker interpreta un percorso relativo in relazione alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="554c0-130">Assembly Linker interprets a relative path in relationship to the current directory.</span></span>  
  
 <span data-ttu-id="554c0-131">L'esempio seguente consente di firmare l'assembly `MyAssembly.dll` con un nome sicuro utilizzando il file di chiave `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="554c0-131">The following example signs the assembly `MyAssembly.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
```  
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
 <span data-ttu-id="554c0-132">Per ulteriori informazioni sull'utilizzo di questo strumento, vedere [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="554c0-132">For more information about this tool, see [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span>  
  
#### <a name="to-sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="554c0-133">Per firmare un assembly con un nome sicuro utilizzando attributi</span><span class="sxs-lookup"><span data-stu-id="554c0-133">To sign an assembly with a strong name by using attributes</span></span>  
  
1. <span data-ttu-id="554c0-134">Aggiungere l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> o <xref:System.Reflection.AssemblyKeyNameAttribute> al file del codice sorgente, specificando il nome del file o del contenitore contenente la coppia di chiavi da utilizzare per la firma dell'assembly con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="554c0-134">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  
  
2. <span data-ttu-id="554c0-135">Compilare normalmente il file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="554c0-135">Compile the source code file normally.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="554c0-136">Nei compilatori C# e Visual Basic vengono pubblicati avvisi del compilatore (rispettivamente CS1699 e BC41008) quando viene rilevato l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="554c0-136">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="554c0-137">È possibile ignorare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="554c0-137">You can ignore the warnings.</span></span>  
  
 <span data-ttu-id="554c0-138">Nell'esempio di codice riportato di seguito viene utilizzato l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> con un file di chiave denominato `keyfile.snk`, che si trova nella directory in cui viene compilato l'assembly.</span><span class="sxs-lookup"><span data-stu-id="554c0-138">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called `keyfile.snk`, which is located in the directory where the assembly is compiled.</span></span>  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
 <span data-ttu-id="554c0-139">È inoltre possibile ritardare la firma di un assembly durante la compilazione del file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="554c0-139">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="554c0-140">Per ulteriori informazioni, vedere [Ritardo della firma di un assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="554c0-140">For more information, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="554c0-141">Per firmare un assembly con un nome sicuro utilizzando il compilatore</span><span class="sxs-lookup"><span data-stu-id="554c0-141">To sign an assembly with a strong name by using the compiler</span></span>  
  
-   <span data-ttu-id="554c0-142">Compilare il file o i file del codice sorgente con l'opzione del compilatore `/keyfile` o `/delaysign` in C# e Visual Basic o con l'opzione del linker `/KEYFILE` o `/DELAYSIGN` in C++.</span><span class="sxs-lookup"><span data-stu-id="554c0-142">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="554c0-143">Dopo il nome di opzione, aggiungere due punti e il nome del file di chiave.</span><span class="sxs-lookup"><span data-stu-id="554c0-143">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="554c0-144">Se si utilizzano compilatori della riga di comando, è possibile copiare il file di chiave nella directory contenente i file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="554c0-144">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  
  
     <span data-ttu-id="554c0-145">Per informazioni sulla firma ritardata, vedere [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="554c0-145">For information on delay signing, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
     <span data-ttu-id="554c0-146">Nell'esempio riportato di seguito viene utilizzato il compilatore C# e viene firmato l'assembly `UtilityLibrary.dll` con un nome sicuro, utilizzando il file di chiave `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="554c0-146">The following example uses the C# compiler and signs the assembly `UtilityLibrary.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
    ```  
    csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="554c0-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="554c0-147">See also</span></span>

- [<span data-ttu-id="554c0-148">Creazione e utilizzo degli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="554c0-148">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="554c0-149">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="554c0-149">How to: Create a Public-Private Key Pair</span></span>](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [<span data-ttu-id="554c0-150">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="554c0-150">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="554c0-151">Ritardo della firma di un assembly</span><span class="sxs-lookup"><span data-stu-id="554c0-151">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)
- [<span data-ttu-id="554c0-152">Gestione delle firme di assembly e manifesti</span><span class="sxs-lookup"><span data-stu-id="554c0-152">Managing Assembly and Manifest Signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [<span data-ttu-id="554c0-153">Pagina Firma, Progettazione progetti</span><span class="sxs-lookup"><span data-stu-id="554c0-153">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)

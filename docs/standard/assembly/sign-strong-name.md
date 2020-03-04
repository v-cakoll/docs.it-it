---
title: 'Procedura: firmare un assembly con un nome sicuro'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 9998e69e8bf1505bcfc7a9103e9d89616dad9633
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160313"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="5c2f4-102">Procedura: firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="5c2f4-102">How to: Sign an assembly with a strong name</span></span>

> [!NOTE]
> <span data-ttu-id="5c2f4-103">Sebbene .NET Core supporti assembly con nome sicuro e tutti gli assembly nella libreria .NET Core siano firmati, la maggior parte degli assembly di terze parti non necessita di nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-103">Although .NET Core supports strong-named assemblies, and all assemblies in the .NET Core library are signed, the majority of third-party assemblies do not need strong names.</span></span> <span data-ttu-id="5c2f4-104">Per altre informazioni, vedere [firma con nome sicuro](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-104">For more information, see [Strong Name Signing](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) on GitHub.</span></span>

<span data-ttu-id="5c2f4-105">Sono disponibili diversi modi per firmare un assembly con un nome sicuro:</span><span class="sxs-lookup"><span data-stu-id="5c2f4-105">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
- <span data-ttu-id="5c2f4-106">Utilizzando la scheda di **Firma** nella finestra di dialogo **Proprietà** di un progetto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-106">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="5c2f4-107">Questo è il modo più semplice e più pratico per firmare un assembly con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-107">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
- <span data-ttu-id="5c2f4-108">Usando [assembly linker (al. exe)](../../framework/tools/al-exe-assembly-linker.md) per collegare un modulo di codice .NET Framework (un file con estensione *netmodule* ) con un file di chiave.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-108">By using the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a *.netmodule* file) with a key file.</span></span>  
  
- <span data-ttu-id="5c2f4-109">Utilizzando attributi dell'assembly per inserire le informazioni relative al nome sicuro nel codice.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-109">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="5c2f4-110">È possibile utilizzare l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> , a seconda della posizione del file di chiave da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-110">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
- <span data-ttu-id="5c2f4-111">Utilizzando le opzioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-111">By using compiler options.</span></span>  
  
 <span data-ttu-id="5c2f4-112">Per firmare un assembly con un nome sicuro, è necessario disporre di una coppia di chiavi crittografiche.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-112">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="5c2f4-113">Per ulteriori informazioni sulla creazione di una coppia di chiavi, vedere [procedura: creare una coppia di chiavi pubblica/privata](create-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="5c2f4-113">For more information about creating a key pair, see [How to: Create a public-private key pair](create-public-private-key-pair.md).</span></span>  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="5c2f4-114">Creare e firmare un assembly con un nome sicuro usando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5c2f4-114">Create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1. <span data-ttu-id="5c2f4-115">In **Esplora soluzioni**aprire il menu di scelta rapida per il progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-115">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="5c2f4-116">Scegliere la scheda **Firma** .</span><span class="sxs-lookup"><span data-stu-id="5c2f4-116">Choose the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="5c2f4-117">Selezionare la casella **Firma assembly** .</span><span class="sxs-lookup"><span data-stu-id="5c2f4-117">Select the **Sign the assembly** box.</span></span>  
  
4. <span data-ttu-id="5c2f4-118">Nella casella **Scegli un file chiave con nome sicuro** scegliere **Sfoglia**e quindi passare al file di chiave.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-118">In the **Choose a strong name key file** box, choose **Browse**, and then navigate to the key file.</span></span> <span data-ttu-id="5c2f4-119">Per creare un nuovo file di chiave, scegliere **nuovo** e immettere il nome nella finestra di dialogo **Crea chiave con nome sicuro** .</span><span class="sxs-lookup"><span data-stu-id="5c2f4-119">To create a new key file, choose **New** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c2f4-120">Per [ritardare la firma di un assembly](delay-sign.md), scegliere un file di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-120">In order to [delay sign an assembly](delay-sign.md), choose a public key file.</span></span>  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="5c2f4-121">Creare e firmare un assembly con un nome sicuro usando assembly linker</span><span class="sxs-lookup"><span data-stu-id="5c2f4-121">Create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
<span data-ttu-id="5c2f4-122">Nel [prompt dei comandi per gli sviluppatori per Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5c2f4-122">At the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), enter the following command:</span></span>  

<span data-ttu-id="5c2f4-123">**al** **/out:**\<*assemblyName*> *\<ModuleName >* **/keyfile:**\<*fileFileName*></span><span class="sxs-lookup"><span data-stu-id="5c2f4-123">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  

<span data-ttu-id="5c2f4-124">Dove:</span><span class="sxs-lookup"><span data-stu-id="5c2f4-124">Where:</span></span>  

- <span data-ttu-id="5c2f4-125">*AssemblyName* è il nome dell'assembly fortemente firmato (un file con estensione *dll* o *exe* ) che verrà generato da assembly linker.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-125">*assemblyName* is the name of the strongly signed assembly (a *.dll* or *.exe* file) that Assembly Linker will emit.</span></span>  
  
- <span data-ttu-id="5c2f4-126">*ModuleName* è il nome di un modulo di codice .NET Framework (un file con estensione *netmodule* ) che include uno o più tipi.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-126">*moduleName* is the name of a .NET Framework code module (a *.netmodule* file) that includes one or more types.</span></span> <span data-ttu-id="5c2f4-127">È possibile creare un file con *estensione netmodule* compilando il codice con l'opzione C# `/target:module` in o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-127">You can create a *.netmodule* file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>
  
- <span data-ttu-id="5c2f4-128">*fileFileName* è il nome del contenitore o del file che contiene la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-128">*keyfileName* is the name of the container or file that contains the key pair.</span></span> <span data-ttu-id="5c2f4-129">Assembly linker interpreta un percorso relativo in relazione alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-129">Assembly Linker interprets a relative path in relation to the current directory.</span></span>  

<span data-ttu-id="5c2f4-130">Nell'esempio seguente l'assembly MyAssembly *. dll* viene firmato con un nome sicuro utilizzando il file di chiave *sgKey. snk*.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-130">The following example signs the assembly *MyAssembly.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
<span data-ttu-id="5c2f4-131">Per ulteriori informazioni sull'utilizzo di questo strumento, vedere [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="5c2f4-131">For more information about this tool, see [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).</span></span>  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="5c2f4-132">Firmare un assembly con un nome sicuro usando gli attributi</span><span class="sxs-lookup"><span data-stu-id="5c2f4-132">Sign an assembly with a strong name by using attributes</span></span>  
  
1. <span data-ttu-id="5c2f4-133">Aggiungere l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> o <xref:System.Reflection.AssemblyKeyNameAttribute> al file del codice sorgente, specificando il nome del file o del contenitore contenente la coppia di chiavi da utilizzare per la firma dell'assembly con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-133">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  

2. <span data-ttu-id="5c2f4-134">Compilare normalmente il file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-134">Compile the source code file normally.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="5c2f4-135">Nei compilatori C# e Visual Basic vengono pubblicati avvisi del compilatore (rispettivamente CS1699 e BC41008) quando viene rilevato l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-135">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="5c2f4-136">È possibile ignorare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-136">You can ignore the warnings.</span></span>  

<span data-ttu-id="5c2f4-137">Nell'esempio seguente viene usato l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> con un file di chiave denominato Key *file. snk*, che si trova nella directory in cui viene compilato l'assembly.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-137">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called *keyfile.snk*, which is located in the directory where the assembly is compiled.</span></span>  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

<span data-ttu-id="5c2f4-138">È inoltre possibile ritardare la firma di un assembly durante la compilazione del file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-138">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="5c2f4-139">Per altre informazioni, vedere [ritardare la firma di un assembly](delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="5c2f4-139">For more information, see [Delay-sign an assembly](delay-sign.md).</span></span>  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="5c2f4-140">Firmare un assembly con un nome sicuro utilizzando il compilatore</span><span class="sxs-lookup"><span data-stu-id="5c2f4-140">Sign an assembly with a strong name by using the compiler</span></span>  

<span data-ttu-id="5c2f4-141">Compilare il file o i file del codice sorgente con l'opzione del compilatore `/keyfile` o `/delaysign` in C# e Visual Basic o con l'opzione del linker `/KEYFILE` o `/DELAYSIGN` in C++.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-141">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="5c2f4-142">Dopo il nome di opzione, aggiungere due punti e il nome del file di chiave.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-142">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="5c2f4-143">Se si utilizzano compilatori della riga di comando, è possibile copiare il file di chiave nella directory contenente i file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-143">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  

<span data-ttu-id="5c2f4-144">Per informazioni sulla firma ritardata, vedere [ritardare la firma di un assembly](delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="5c2f4-144">For information on delay signing, see [Delay-sign an assembly](delay-sign.md).</span></span>  

<span data-ttu-id="5c2f4-145">Nell'esempio seguente viene usato C# il compilatore e viene firmato l'assembly *UtilityLibrary. dll* con un nome sicuro usando il file di chiave *sgKey. snk*.</span><span class="sxs-lookup"><span data-stu-id="5c2f4-145">The following example uses the C# compiler and signs the assembly *UtilityLibrary.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a><span data-ttu-id="5c2f4-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c2f4-146">See also</span></span>

- [<span data-ttu-id="5c2f4-147">Creazione e utilizzo di assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="5c2f4-147">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="5c2f4-148">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="5c2f4-148">How to: Create a public-private key pair</span></span>](create-public-private-key-pair.md)
- [<span data-ttu-id="5c2f4-149">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="5c2f4-149">Al.exe (Assembly Linker)</span></span>](../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="5c2f4-150">Ritardare la firma di un assembly</span><span class="sxs-lookup"><span data-stu-id="5c2f4-150">Delay-sign an assembly</span></span>](delay-sign.md)
- [<span data-ttu-id="5c2f4-151">Gestire le firme di assembly e manifesti</span><span class="sxs-lookup"><span data-stu-id="5c2f4-151">Manage assembly and manifest signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [<span data-ttu-id="5c2f4-152">Pagina Firma, Creazione progetti</span><span class="sxs-lookup"><span data-stu-id="5c2f4-152">Signing page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)

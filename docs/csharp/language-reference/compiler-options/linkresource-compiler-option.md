---
title: -linkresource (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7da5a55fa96c11d79f8c616cf0f1f4e0ed109bfa
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="-linkresource-c-compiler-options"></a><span data-ttu-id="0aa05-102">-linkresource (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="0aa05-102">-linkresource (C# Compiler Options)</span></span>
<span data-ttu-id="0aa05-103">Crea un collegamento a una risorsa di .NET Framework nel file di output.</span><span class="sxs-lookup"><span data-stu-id="0aa05-103">Creates a link to a .NET Framework resource in the output file.</span></span> <span data-ttu-id="0aa05-104">Il file di risorse non viene aggiunto al file di output.</span><span class="sxs-lookup"><span data-stu-id="0aa05-104">The resource file is not added to the output file.</span></span> <span data-ttu-id="0aa05-105">Questa opzione è diversa dall'opzione [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md), che invece incorpora un file di risorse nel file di output.</span><span class="sxs-lookup"><span data-stu-id="0aa05-105">This differs from the [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aa05-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0aa05-106">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0aa05-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0aa05-107">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="0aa05-108">File di risorse .NET Framework a cui si vuole stabilire un collegamento dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="0aa05-108">The .NET Framework resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="0aa05-109">`identifier` (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0aa05-109">`identifier` (optional)</span></span>  
 <span data-ttu-id="0aa05-110">Nome logico della risorsa, usato per caricare la risorsa stessa.</span><span class="sxs-lookup"><span data-stu-id="0aa05-110">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="0aa05-111">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="0aa05-111">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="0aa05-112">`accessibility-modifier` (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0aa05-112">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="0aa05-113">Accessibilità della risorsa: public o private.</span><span class="sxs-lookup"><span data-stu-id="0aa05-113">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="0aa05-114">L'impostazione predefinita è public.</span><span class="sxs-lookup"><span data-stu-id="0aa05-114">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0aa05-115">Note</span><span class="sxs-lookup"><span data-stu-id="0aa05-115">Remarks</span></span>  
 <span data-ttu-id="0aa05-116">Per impostazione predefinita, le risorse collegate sono pubbliche nell'assembly quando vengono create con il compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="0aa05-116">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="0aa05-117">Per renderle private, specificare `private` come modificatore di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="0aa05-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="0aa05-118">Non è consentito alcun modificatore diverso da `public` o `private`.</span><span class="sxs-lookup"><span data-stu-id="0aa05-118">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="0aa05-119">Per **-linkresource** è necessaria un'opzione [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) diversa da **-target:module**.</span><span class="sxs-lookup"><span data-stu-id="0aa05-119">**-linkresource** requires one of the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) options other than **-target:module**.</span></span>  
  
 <span data-ttu-id="0aa05-120">Se `filename` è un file di risorse .NET Framework creato ad esempio da [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri dello spazio dei nomi <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="0aa05-120">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="0aa05-121">Per altre informazioni, vedere <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0aa05-121">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0aa05-122">Per tutte le altre risorse, per accedere alla risorsa in fase di esecuzione usare i metodi `GetManifestResource` della classe <xref:System.Reflection.Assembly>.</span><span class="sxs-lookup"><span data-stu-id="0aa05-122">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="0aa05-123">Il file specificato in `filename` può avere qualsiasi formato.</span><span class="sxs-lookup"><span data-stu-id="0aa05-123">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="0aa05-124">Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0aa05-124">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="0aa05-125">Nel secondo degli esempi seguenti viene illustrato come effettuare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="0aa05-125">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="0aa05-126">È possibile eseguire la stessa operazione in Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="0aa05-126">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="0aa05-127">Nel terzo degli esempi seguenti viene illustrato come effettuare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="0aa05-127">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="0aa05-128">Per altre informazioni, vedere [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) e [Uso di assembly e della Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="0aa05-128">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="0aa05-129">**-linkres** rappresenta la versione abbreviata di **-linkresource**.</span><span class="sxs-lookup"><span data-stu-id="0aa05-129">**-linkres** is the short form of **-linkresource**.</span></span>  
  
 <span data-ttu-id="0aa05-130">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="0aa05-130">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0aa05-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="0aa05-131">Example</span></span>  
 <span data-ttu-id="0aa05-132">Compilare `in.cs` e stabilire il collegamento al file di risorse `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="0aa05-132">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="0aa05-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="0aa05-133">Example</span></span>  
 <span data-ttu-id="0aa05-134">Compilare `A.cs` in una DLL, creare un collegamento a una DLL N.dll nativa e inserire l'output nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="0aa05-134">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="0aa05-135">In questo esempio i file A.dll e N.dll verranno memorizzati entrambi nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="0aa05-135">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="0aa05-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="0aa05-136">Example</span></span>  
 <span data-ttu-id="0aa05-137">In questo esempio viene eseguita la stessa operazione descritta in precedenza, ma vengono usate le opzioni di Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="0aa05-137">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="0aa05-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0aa05-138">See Also</span></span>  
 [<span data-ttu-id="0aa05-139">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="0aa05-139">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="0aa05-140">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="0aa05-140">Al.exe (Assembly Linker)</span></span>](../../../framework/tools/al-exe-assembly-linker.md)  
 [<span data-ttu-id="0aa05-141">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="0aa05-141">Working with Assemblies and the Global Assembly Cache</span></span>](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="0aa05-142">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="0aa05-142">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

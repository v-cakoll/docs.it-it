---
title: -resource (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: e14bf59f5922a918b627af22c052c8efd9081e84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602520"
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="cca60-102">-resource (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="cca60-102">-resource (C# Compiler Options)</span></span>
<span data-ttu-id="cca60-103">Incorpora la risorsa specificata nel file di output.</span><span class="sxs-lookup"><span data-stu-id="cca60-103">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cca60-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cca60-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cca60-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="cca60-106">File di risorse .NET Framework da incorporare nel file di output.</span><span class="sxs-lookup"><span data-stu-id="cca60-106">The .NET Framework resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="cca60-107">`identifier` (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="cca60-107">`identifier` (optional)</span></span>  
 <span data-ttu-id="cca60-108">Nome logico della risorsa, usato per caricare la risorsa stessa.</span><span class="sxs-lookup"><span data-stu-id="cca60-108">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="cca60-109">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="cca60-109">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="cca60-110">`accessibility-modifier` (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="cca60-110">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="cca60-111">Accessibilità della risorsa: public o private.</span><span class="sxs-lookup"><span data-stu-id="cca60-111">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="cca60-112">Il valore predefinito è public.</span><span class="sxs-lookup"><span data-stu-id="cca60-112">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cca60-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cca60-113">Remarks</span></span>  
 <span data-ttu-id="cca60-114">Usare [-linkresource](./linkresource-compiler-option.md) per collegare una risorsa a un assembly senza aggiungere il file di risorse al file di output.</span><span class="sxs-lookup"><span data-stu-id="cca60-114">Use [-linkresource](./linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="cca60-115">Per impostazione predefinita, le risorse sono pubbliche nell'assembly quando vengono create tramite il compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="cca60-115">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="cca60-116">Per renderle private, specificare `private` come modificatore di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="cca60-116">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="cca60-117">Non è consentita alcuna accessibilità diversa da `public` o `private`.</span><span class="sxs-lookup"><span data-stu-id="cca60-117">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="cca60-118">Se `filename` è un file di risorse .NET Framework creato ad esempio da [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri dello spazio dei nomi <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="cca60-118">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="cca60-119">Per altre informazioni, vedere <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cca60-119">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cca60-120">Per tutte le altre risorse, per accedere alla risorsa in fase di esecuzione usare i metodi `GetManifestResource` della classe <xref:System.Reflection.Assembly>.</span><span class="sxs-lookup"><span data-stu-id="cca60-120">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="cca60-121">**-res** rappresenta la versione abbreviata di **-resource**.</span><span class="sxs-lookup"><span data-stu-id="cca60-121">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="cca60-122">L'ordine delle risorse nel file di output è determinato dall'ordine specificato nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="cca60-122">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="cca60-123">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cca60-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="cca60-124">Aggiungere un file di risorse al progetto.</span><span class="sxs-lookup"><span data-stu-id="cca60-124">Add a resource file to your project.</span></span>  
  
2. <span data-ttu-id="cca60-125">Selezionare il file che si vuole incorporare in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="cca60-125">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3. <span data-ttu-id="cca60-126">Selezionare **Azione di compilazione** per il file nella finestra **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cca60-126">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="cca60-127">Impostare **Azione di compilazione** su **Risorsa incorporata**.</span><span class="sxs-lookup"><span data-stu-id="cca60-127">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="cca60-128">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span><span class="sxs-lookup"><span data-stu-id="cca60-128">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cca60-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="cca60-129">Example</span></span>  
 <span data-ttu-id="cca60-130">Compilare `in.cs` e associare il file di risorse `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="cca60-130">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cca60-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cca60-131">See also</span></span>

- [<span data-ttu-id="cca60-132">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="cca60-132">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="cca60-133">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="cca60-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

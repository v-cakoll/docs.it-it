---
title: -resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 2d7da572ecc8d7d20917eaa244eefbcd7abe61f0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589519"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="93714-102">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93714-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="93714-103">Incorpora una risorsa gestita in un assembly.</span><span class="sxs-lookup"><span data-stu-id="93714-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93714-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93714-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="93714-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="93714-105">Arguments</span></span>  
  
|<span data-ttu-id="93714-106">Termine</span><span class="sxs-lookup"><span data-stu-id="93714-106">Term</span></span>|<span data-ttu-id="93714-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="93714-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="93714-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="93714-108">Required.</span></span> <span data-ttu-id="93714-109">Il nome del file di risorse da incorporare nel file di output.</span><span class="sxs-lookup"><span data-stu-id="93714-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="93714-110">Per impostazione predefinita, `filename` è pubblico nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="93714-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="93714-111">Racchiudere il nome file racchiuso tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="93714-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="93714-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="93714-112">Optional.</span></span> <span data-ttu-id="93714-113">Il nome logico della risorsa nome utilizzato per caricarlo.</span><span class="sxs-lookup"><span data-stu-id="93714-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="93714-114">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="93714-114">The default is the name of the file.</span></span> <span data-ttu-id="93714-115">Facoltativamente, è possibile specificare se la risorsa è pubblica o privata nel manifesto dell'assembly, come con il codice seguente: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="93714-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93714-116">Note</span><span class="sxs-lookup"><span data-stu-id="93714-116">Remarks</span></span>  
 <span data-ttu-id="93714-117">Usare `-linkresource` per collegare una risorsa a un assembly senza inserire il file di risorse nel file di output.</span><span class="sxs-lookup"><span data-stu-id="93714-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="93714-118">Se `filename` è un file di risorse .NET Framework creato ad esempio, dal [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri di <xref:System.Resources> dello spazio dei nomi (vedere <xref:System.Resources.ResourceManager> per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="93714-118">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="93714-119">Per accedere a tutte le altre risorse in fase di esecuzione, usare uno dei seguenti metodi: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="93714-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="93714-120">La forma breve di `-resource` è `-res`.</span><span class="sxs-lookup"><span data-stu-id="93714-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="93714-121">Per informazioni su come impostare `-resource` nell'IDE di Visual Studio, vedere [gestione delle applicazioni alle risorse (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="93714-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="93714-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="93714-122">Example</span></span>  
 <span data-ttu-id="93714-123">Il codice seguente Compila `In.vb` e il file di risorse consente di collegare `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="93714-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="93714-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93714-124">See also</span></span>

- [<span data-ttu-id="93714-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93714-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="93714-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="93714-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="93714-127">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93714-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="93714-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93714-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="93714-129">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="93714-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 0315645eccdc899ac9cf4d0be105297e1fa2a4c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335487"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="4a5b4-102">-linkresource ((Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a5b4-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="4a5b4-103">Crea un collegamento a una risorsa gestita.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a5b4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a5b4-104">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="4a5b4-105">oppure</span><span class="sxs-lookup"><span data-stu-id="4a5b4-105">or</span></span>  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4a5b4-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4a5b4-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="4a5b4-107">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-107">Required.</span></span> <span data-ttu-id="4a5b4-108">File di risorse da collegare all'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-108">The resource file to link to the assembly.</span></span> <span data-ttu-id="4a5b4-109">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="4a5b4-109">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="4a5b4-110">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-110">Optional.</span></span> <span data-ttu-id="4a5b4-111">Nome logico della risorsa.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-111">The logical name for the resource.</span></span> <span data-ttu-id="4a5b4-112">Nome usato per caricare la risorsa.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-112">The name that is used to load the resource.</span></span> <span data-ttu-id="4a5b4-113">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-113">The default is the name of the file.</span></span> <span data-ttu-id="4a5b4-114">Facoltativamente, è possibile specificare se il file è pubblico o privato nel manifesto dell'assembly, ad esempio: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-114">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="4a5b4-115">Per impostazione predefinita `filename` , è Public nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-115">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a5b4-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4a5b4-116">Remarks</span></span>  
 <span data-ttu-id="4a5b4-117">L' `-linkresource` opzione non incorpora il file di risorse nel file di output. usare l' `-resource` opzione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-117">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="4a5b4-118">L' `-linkresource` opzione richiede una delle `-target` opzioni diverse da. `-target:module`</span><span class="sxs-lookup"><span data-stu-id="4a5b4-118">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="4a5b4-119">Se `filename` è un file di risorse .NET Framework creato, ad esempio da [Resgen. exe (Generatore di file di risorse)](../../../framework/tools/resgen-exe-resource-file-generator.md) o nell'ambiente di sviluppo, è possibile accedervi con i membri <xref:System.Resources> nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="4a5b4-120">Per ulteriori informazioni, vedere <xref:System.Resources.ResourceManager>. Per accedere a tutte le altre risorse in fase di esecuzione, usare i metodi `GetManifestResource` che iniziano <xref:System.Reflection.Assembly> con nella classe.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-120">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="4a5b4-121">Il nome del file può essere qualsiasi formato di file.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-121">The file name can be any file format.</span></span> <span data-ttu-id="4a5b4-122">Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-122">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="4a5b4-123">La forma breve di `-linkresource` è `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-123">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a5b4-124">L' `-linkresource` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-124">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a5b4-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a5b4-125">Example</span></span>  
 <span data-ttu-id="4a5b4-126">Il codice seguente compila `in.vb` e collega a un file `rf.resource`di risorse.</span><span class="sxs-lookup"><span data-stu-id="4a5b4-126">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a5b4-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4a5b4-127">See also</span></span>

- [<span data-ttu-id="4a5b4-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a5b4-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4a5b4-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a5b4-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="4a5b4-130">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a5b4-130">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="4a5b4-131">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="4a5b4-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

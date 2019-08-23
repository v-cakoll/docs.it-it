---
title: -linkresource ((Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924866"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="127c3-102">-linkresource ((Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="127c3-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="127c3-103">Crea un collegamento a una risorsa gestita.</span><span class="sxs-lookup"><span data-stu-id="127c3-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="127c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="127c3-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="127c3-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="127c3-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="127c3-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="127c3-106">Required.</span></span> <span data-ttu-id="127c3-107">File di risorse da collegare all'assembly.</span><span class="sxs-lookup"><span data-stu-id="127c3-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="127c3-108">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="127c3-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="127c3-109">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="127c3-109">Optional.</span></span> <span data-ttu-id="127c3-110">Nome logico della risorsa.</span><span class="sxs-lookup"><span data-stu-id="127c3-110">The logical name for the resource.</span></span> <span data-ttu-id="127c3-111">Nome usato per caricare la risorsa.</span><span class="sxs-lookup"><span data-stu-id="127c3-111">The name that is used to load the resource.</span></span> <span data-ttu-id="127c3-112">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="127c3-112">The default is the name of the file.</span></span> <span data-ttu-id="127c3-113">Facoltativamente, è possibile specificare se il file è pubblico o privato nel manifesto dell'assembly, ad esempio: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="127c3-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="127c3-114">Per impostazione predefinita `filename` , è Public nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="127c3-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="127c3-115">Note</span><span class="sxs-lookup"><span data-stu-id="127c3-115">Remarks</span></span>  
 <span data-ttu-id="127c3-116">L' `-linkresource` opzione non incorpora il file di risorse nel file di output. utilizzare l' `-resource` opzione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="127c3-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="127c3-117">L' `-linkresource` opzione richiede una `-target` delle opzioni diverse da `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="127c3-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="127c3-118">Se `filename` è un file di risorse .NET Framework creato, ad esempio da [Resgen. exe (Generatore di file di risorse)](../../../framework/tools/resgen-exe-resource-file-generator.md) o nell'ambiente di sviluppo, è possibile accedervi <xref:System.Resources> con i membri nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="127c3-118">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="127c3-119">Per altre informazioni, vedere <xref:System.Resources.ResourceManager>. Per accedere a tutte le altre risorse in fase di esecuzione, usare i metodi `GetManifestResource` che iniziano <xref:System.Reflection.Assembly> con nella classe.</span><span class="sxs-lookup"><span data-stu-id="127c3-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="127c3-120">Il nome del file può essere qualsiasi formato di file.</span><span class="sxs-lookup"><span data-stu-id="127c3-120">The file name can be any file format.</span></span> <span data-ttu-id="127c3-121">Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="127c3-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="127c3-122">La forma breve di `-linkresource` è `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="127c3-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="127c3-123">L' `-linkresource` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="127c3-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="127c3-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="127c3-124">Example</span></span>  
 <span data-ttu-id="127c3-125">Il codice seguente compila `in.vb` e collega a un file `rf.resource`di risorse.</span><span class="sxs-lookup"><span data-stu-id="127c3-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="127c3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="127c3-126">See also</span></span>

- [<span data-ttu-id="127c3-127">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="127c3-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="127c3-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="127c3-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="127c3-129">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="127c3-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="127c3-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="127c3-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 97e0ccd46f413cc05b659731436bb141ee178419
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47237462"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="914c0-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="914c0-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="914c0-103">Crea un collegamento a una risorsa gestita.</span><span class="sxs-lookup"><span data-stu-id="914c0-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="914c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="914c0-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="914c0-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="914c0-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="914c0-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="914c0-106">Required.</span></span> <span data-ttu-id="914c0-107">Il file di risorse da collegare all'assembly.</span><span class="sxs-lookup"><span data-stu-id="914c0-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="914c0-108">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="914c0-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="914c0-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="914c0-109">Optional.</span></span> <span data-ttu-id="914c0-110">Il nome logico per la risorsa.</span><span class="sxs-lookup"><span data-stu-id="914c0-110">The logical name for the resource.</span></span> <span data-ttu-id="914c0-111">Il nome usato per caricare la risorsa.</span><span class="sxs-lookup"><span data-stu-id="914c0-111">The name that is used to load the resource.</span></span> <span data-ttu-id="914c0-112">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="914c0-112">The default is the name of the file.</span></span> <span data-ttu-id="914c0-113">Facoltativamente, è possibile specificare se il file è pubblica o privata nel manifesto dell'assembly, ad esempio: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="914c0-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="914c0-114">Per impostazione predefinita, `filename` è pubblico nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="914c0-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="914c0-115">Note</span><span class="sxs-lookup"><span data-stu-id="914c0-115">Remarks</span></span>  
 <span data-ttu-id="914c0-116">Il `-linkresource` opzione consente di incorporare il file di risorse nel file di output, usare il `-resource` opzione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="914c0-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="914c0-117">Il `-linkresource` necessaria un'opzione il `-target` diversa da `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="914c0-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="914c0-118">Se `filename` è un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse creato, ad esempio, mediante il [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri di <xref:System.Resources> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="914c0-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="914c0-119">Per altre informazioni, vedere <xref:System.Resources.ResourceManager>. Per accedere a tutte le altre risorse in fase di esecuzione, usare i metodi che iniziano con `GetManifestResource` nella <xref:System.Reflection.Assembly> classe.</span><span class="sxs-lookup"><span data-stu-id="914c0-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="914c0-120">Il nome del file può avere qualsiasi formato di file.</span><span class="sxs-lookup"><span data-stu-id="914c0-120">The file name can be any file format.</span></span> <span data-ttu-id="914c0-121">Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="914c0-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="914c0-122">La forma breve di `-linkresource` è `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="914c0-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="914c0-123">Il `-linkresource` opzione non è disponibile dall'ambiente di sviluppo Visual Studio, è disponibile solo quando esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="914c0-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="914c0-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="914c0-124">Example</span></span>  
 <span data-ttu-id="914c0-125">Il codice seguente Compila `in.vb` e i collegamenti al file di risorse `rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="914c0-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="914c0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="914c0-126">See also</span></span>

- [<span data-ttu-id="914c0-127">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="914c0-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
- [<span data-ttu-id="914c0-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="914c0-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
- [<span data-ttu-id="914c0-129">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="914c0-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
- [<span data-ttu-id="914c0-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="914c0-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

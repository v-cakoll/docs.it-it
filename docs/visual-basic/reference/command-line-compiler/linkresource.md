---
title: /linkresource (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e51f844695985485210a1e4bedfef7ac968326c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-visual-basic"></a><span data-ttu-id="a1be1-102">/linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1be1-102">/linkresource (Visual Basic)</span></span>
<span data-ttu-id="a1be1-103">Crea un collegamento a una risorsa gestita.</span><span class="sxs-lookup"><span data-stu-id="a1be1-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1be1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1be1-104">Syntax</span></span>  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a1be1-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a1be1-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="a1be1-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a1be1-106">Required.</span></span> <span data-ttu-id="a1be1-107">File di risorse da collegare all'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1be1-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="a1be1-108">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="a1be1-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="a1be1-109">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a1be1-109">Optional.</span></span> <span data-ttu-id="a1be1-110">Il nome logico per la risorsa.</span><span class="sxs-lookup"><span data-stu-id="a1be1-110">The logical name for the resource.</span></span> <span data-ttu-id="a1be1-111">Il nome utilizzato per caricare la risorsa.</span><span class="sxs-lookup"><span data-stu-id="a1be1-111">The name that is used to load the resource.</span></span> <span data-ttu-id="a1be1-112">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="a1be1-112">The default is the name of the file.</span></span> <span data-ttu-id="a1be1-113">Facoltativamente, è possibile specificare se il file è pubblica o privata nel manifesto dell'assembly, ad esempio: `/linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="a1be1-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `/linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="a1be1-114">Per impostazione predefinita, `filename` è pubblico nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1be1-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1be1-115">Note</span><span class="sxs-lookup"><span data-stu-id="a1be1-115">Remarks</span></span>  
 <span data-ttu-id="a1be1-116">Il `/linkresource` opzione consente di incorporare il file di risorse nel file di output, utilizzare il `/resource` opzione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="a1be1-116">The `/linkresource` option does not embed the resource file in the output file; use the `/resource` option to do this.</span></span>  
  
 <span data-ttu-id="a1be1-117">Il `/linkresource` necessaria un'opzione di `/target` diversa da `/target:module`.</span><span class="sxs-lookup"><span data-stu-id="a1be1-117">The `/linkresource` option requires one of the `/target` options other than `/target:module`.</span></span>  
  
 <span data-ttu-id="a1be1-118">Se `filename` è un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse creato, ad esempio, mediante il [Resgen.exe (Generatore di File di risorse)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oppure nell'ambiente di sviluppo, è possibile accedervi con i membri il <xref:System.Resources> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a1be1-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="a1be1-119">Per altre informazioni, vedere <xref:System.Resources.ResourceManager>. Per accedere a tutte le altre risorse in fase di esecuzione, utilizzare i metodi che iniziano con `GetManifestResource` nel <xref:System.Reflection.Assembly> classe.</span><span class="sxs-lookup"><span data-stu-id="a1be1-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="a1be1-120">Il nome del file può essere qualsiasi formato di file.</span><span class="sxs-lookup"><span data-stu-id="a1be1-120">The file name can be any file format.</span></span> <span data-ttu-id="a1be1-121">Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1be1-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="a1be1-122">La forma breve di `/linkresource` è `/linkres`.</span><span class="sxs-lookup"><span data-stu-id="a1be1-122">The short form of `/linkresource` is `/linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1be1-123">Il `/linkresource` opzione non è disponibile dall'ambiente di sviluppo di Visual Studio; è disponibile solo quando esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a1be1-123">The `/linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1be1-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1be1-124">Example</span></span>  
 <span data-ttu-id="a1be1-125">Il codice seguente Compila `In.vb` e collegamenti a file di risorse `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="a1be1-125">The following code compiles `In.vb` and links to resource file `Rf.resource`.</span></span>  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1be1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1be1-126">See Also</span></span>  
 [<span data-ttu-id="a1be1-127">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a1be1-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a1be1-128">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1be1-128">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="a1be1-129">/Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1be1-129">/resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [<span data-ttu-id="a1be1-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="a1be1-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: /linkresource (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8d4d2d2fdacef0c830414790efa544a96c35fd3c
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="linkresource-visual-basic"></a><span data-ttu-id="c2385-102">/linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2385-102">/linkresource (Visual Basic)</span></span>
<span data-ttu-id="c2385-103">Crea un collegamento a una risorsa gestita.</span><span class="sxs-lookup"><span data-stu-id="c2385-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2385-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2385-104">Syntax</span></span>  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2385-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c2385-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="c2385-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c2385-106">Required.</span></span> <span data-ttu-id="c2385-107">File di risorse da collegare all'assembly.</span><span class="sxs-lookup"><span data-stu-id="c2385-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="c2385-108">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="c2385-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="c2385-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c2385-109">Optional.</span></span> <span data-ttu-id="c2385-110">Nome logico per la risorsa.</span><span class="sxs-lookup"><span data-stu-id="c2385-110">The logical name for the resource.</span></span> <span data-ttu-id="c2385-111">Il nome utilizzato per caricare la risorsa.</span><span class="sxs-lookup"><span data-stu-id="c2385-111">The name that is used to load the resource.</span></span> <span data-ttu-id="c2385-112">Il valore predefinito è il nome del file.</span><span class="sxs-lookup"><span data-stu-id="c2385-112">The default is the name of the file.</span></span> <span data-ttu-id="c2385-113">Facoltativamente, è possibile specificare se il file è pubblico o privato nel manifesto dell'assembly, ad esempio: `/linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="c2385-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `/linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="c2385-114">Per impostazione predefinita, `filename` è pubblico nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c2385-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2385-115">Note</span><span class="sxs-lookup"><span data-stu-id="c2385-115">Remarks</span></span>  
 <span data-ttu-id="c2385-116">Il `/linkresource` opzione consente di incorporare il file di risorse nel file di output, utilizzare il `/resource` opzione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="c2385-116">The `/linkresource` option does not embed the resource file in the output file; use the `/resource` option to do this.</span></span>  
  
 <span data-ttu-id="c2385-117">Il `/linkresource` necessaria un'opzione di `/target` diversa da `/target:module`.</span><span class="sxs-lookup"><span data-stu-id="c2385-117">The `/linkresource` option requires one of the `/target` options other than `/target:module`.</span></span>  
  
 <span data-ttu-id="c2385-118">Se `filename` è un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] file di risorse creato, ad esempio, mediante il [Resgen.exe (Generatore di File di risorse)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) o nell'ambiente di sviluppo, sono accessibili tramite i membri di <xref:System.Resources>dello spazio dei nomi.</xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="c2385-118">If `filename` is a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="c2385-119">(Per ulteriori informazioni, vedere <xref:System.Resources.ResourceManager>.)</xref:System.Resources.ResourceManager> Per accedere a tutte le altre risorse in fase di esecuzione, utilizzare i metodi che iniziano con `GetManifestResource` nella <xref:System.Reflection.Assembly>classe.</xref:System.Reflection.Assembly></span><span class="sxs-lookup"><span data-stu-id="c2385-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="c2385-120">Il nome del file può avere qualsiasi formato di file.</span><span class="sxs-lookup"><span data-stu-id="c2385-120">The file name can be any file format.</span></span> <span data-ttu-id="c2385-121">Ad esempio, è consigliabile includere una DLL nativa dell'assembly, in modo che possa essere installato nella global assembly cache e accedervi dal codice gestito nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c2385-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="c2385-122">La versione abbreviata di `/linkresource` è `/linkres`.</span><span class="sxs-lookup"><span data-stu-id="c2385-122">The short form of `/linkresource` is `/linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2385-123">Il `/linkresource` opzione non è disponibile dall'ambiente di sviluppo Visual Studio, è disponibile solo quando si compila dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c2385-123">The `/linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2385-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2385-124">Example</span></span>  
 <span data-ttu-id="c2385-125">Il codice seguente Compila `In.vb` e collegamenti a file di risorse `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="c2385-125">The following code compiles `In.vb` and links to resource file `Rf.resource`.</span></span>  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2385-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2385-126">See Also</span></span>  
 <span data-ttu-id="c2385-127">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="c2385-127">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="c2385-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="c2385-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="c2385-129"> [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) </span><span class="sxs-lookup"><span data-stu-id="c2385-129"> [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) </span></span>  
<span data-ttu-id="c2385-130"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="c2385-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

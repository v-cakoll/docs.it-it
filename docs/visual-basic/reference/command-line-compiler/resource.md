---
title: /resource (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 858a216873ad9999722388e45d5de28398b27fbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="resource-visual-basic"></a><span data-ttu-id="c194e-102">/resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c194e-102">/resource (Visual Basic)</span></span>
<span data-ttu-id="c194e-103">Incorpora una risorsa gestita in un assembly.</span><span class="sxs-lookup"><span data-stu-id="c194e-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c194e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c194e-104">Syntax</span></span>  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c194e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c194e-105">Arguments</span></span>  
  
|<span data-ttu-id="c194e-106">Termine</span><span class="sxs-lookup"><span data-stu-id="c194e-106">Term</span></span>|<span data-ttu-id="c194e-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="c194e-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="c194e-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c194e-108">Required.</span></span> <span data-ttu-id="c194e-109">Il nome del file di risorse da incorporare nel file di output.</span><span class="sxs-lookup"><span data-stu-id="c194e-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="c194e-110">Per impostazione predefinita, `filename` è pubblico nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c194e-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="c194e-111">Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="c194e-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="c194e-112">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c194e-112">Optional.</span></span> <span data-ttu-id="c194e-113">Il nome logico per la risorsa. il nome utilizzato per caricarla.</span><span class="sxs-lookup"><span data-stu-id="c194e-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="c194e-114">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="c194e-114">The default is the name of the file.</span></span> <span data-ttu-id="c194e-115">Facoltativamente, è possibile specificare se la risorsa è pubblica o privata nel manifesto dell'assembly, come le operazioni seguenti: `/res:``filename.res`,`myname.res`,`public`</span><span class="sxs-lookup"><span data-stu-id="c194e-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `/res:``filename.res`,`myname.res`,`public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c194e-116">Note</span><span class="sxs-lookup"><span data-stu-id="c194e-116">Remarks</span></span>  
 <span data-ttu-id="c194e-117">Utilizzare `/linkresource` per collegare una risorsa a un assembly senza inserire il file di risorse nel file di output.</span><span class="sxs-lookup"><span data-stu-id="c194e-117">Use `/linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="c194e-118">Se `filename` è un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse creato, ad esempio, mediante il [Resgen.exe (Generatore di File di risorse)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oppure nell'ambiente di sviluppo, è possibile accedervi con i membri il <xref:System.Resources> dello spazio dei nomi (vedere <xref:System.Resources.ResourceManager> per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="c194e-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="c194e-119">Per accedere a tutte le altre risorse in fase di esecuzione, utilizzare uno dei metodi seguenti: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="c194e-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="c194e-120">La forma breve di `/resource` è `/res`.</span><span class="sxs-lookup"><span data-stu-id="c194e-120">The short form of `/resource` is `/res`.</span></span>  
  
 <span data-ttu-id="c194e-121">Per informazioni su come impostare `/resource` nell'IDE di Visual Studio, vedere [risorse dell'applicazione di gestione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="c194e-121">For information about how to set `/resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c194e-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="c194e-122">Example</span></span>  
 <span data-ttu-id="c194e-123">Il codice seguente Compila `In.vb` Associa file di risorse e `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="c194e-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c194e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c194e-124">See Also</span></span>  
 [<span data-ttu-id="c194e-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c194e-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c194e-126">/win32resource</span><span class="sxs-lookup"><span data-stu-id="c194e-126">/win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [<span data-ttu-id="c194e-127">/linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c194e-127">/linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [<span data-ttu-id="c194e-128">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c194e-128">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="c194e-129">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="c194e-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

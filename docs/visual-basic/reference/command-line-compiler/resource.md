---
title: /Resource (Visual Basic) | Documenti di Microsoft
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
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2278902f96f7b6349e91a9803f58c3caa89f4f33
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="resource-visual-basic"></a><span data-ttu-id="9a4e2-102">/resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a4e2-102">/resource (Visual Basic)</span></span>
<span data-ttu-id="9a4e2-103">Incorpora una risorsa gestita in un assembly.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a4e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a4e2-104">Syntax</span></span>  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9a4e2-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9a4e2-105">Arguments</span></span>  
  
|<span data-ttu-id="9a4e2-106">Termine</span><span class="sxs-lookup"><span data-stu-id="9a4e2-106">Term</span></span>|<span data-ttu-id="9a4e2-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="9a4e2-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="9a4e2-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-108">Required.</span></span> <span data-ttu-id="9a4e2-109">Il nome del file di risorse da incorporare nel file di output.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="9a4e2-110">Per impostazione predefinita, `filename` è pubblico nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="9a4e2-111">Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="9a4e2-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-112">Optional.</span></span> <span data-ttu-id="9a4e2-113">Il nome logico per la risorsa. il nome utilizzato per caricarla.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="9a4e2-114">Il valore predefinito è il nome del file.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-114">The default is the name of the file.</span></span> <span data-ttu-id="9a4e2-115">Facoltativamente, è possibile specificare se la risorsa è pubblica o privata nel manifesto dell'assembly, come le operazioni seguenti: `/res:``filename.res`,`myname.res`,`public`</span><span class="sxs-lookup"><span data-stu-id="9a4e2-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `/res:``filename.res`,`myname.res`,`public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a4e2-116">Note</span><span class="sxs-lookup"><span data-stu-id="9a4e2-116">Remarks</span></span>  
 <span data-ttu-id="9a4e2-117">Utilizzare `/linkresource` per collegare una risorsa a un assembly senza inserire il file di risorse nel file di output.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-117">Use `/linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="9a4e2-118">Se `filename` è un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] file di risorse creato, ad esempio, mediante il [Resgen.exe (Generatore di File di risorse)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) o nell'ambiente di sviluppo, sono accessibili tramite i membri di <xref:System.Resources>dello spazio dei nomi (vedere <xref:System.Resources.ResourceManager>Per ulteriori informazioni).</xref:System.Resources.ResourceManager> </xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="9a4e2-118">If `filename` is a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="9a4e2-119">Per accedere a tutte le altre risorse in fase di esecuzione, utilizzare uno dei metodi seguenti: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</xref:System.Reflection.Assembly.GetManifestResourceStream%2A> </xref:System.Reflection.Assembly.GetManifestResourceNames%2A> </xref:System.Reflection.Assembly.GetManifestResourceInfo%2A></span><span class="sxs-lookup"><span data-stu-id="9a4e2-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="9a4e2-120">La versione abbreviata di `/resource` è `/res`.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-120">The short form of `/resource` is `/res`.</span></span>  
  
 <span data-ttu-id="9a4e2-121">Per informazioni su come impostare `/resource` nell'IDE di Visual Studio, vedere [risorse dell'applicazione di gestione (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="9a4e2-121">For information about how to set `/resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a4e2-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a4e2-122">Example</span></span>  
 <span data-ttu-id="9a4e2-123">Il codice seguente Compila `In.vb` e consente di collegare file di risorse `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="9a4e2-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a4e2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a4e2-124">See Also</span></span>  
 <span data-ttu-id="9a4e2-125">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a4e2-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="9a4e2-126"> [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) </span><span class="sxs-lookup"><span data-stu-id="9a4e2-126"> [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) </span></span>  
<span data-ttu-id="9a4e2-127"> [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) </span><span class="sxs-lookup"><span data-stu-id="9a4e2-127"> [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) </span></span>  
<span data-ttu-id="9a4e2-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="9a4e2-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="9a4e2-129"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="9a4e2-129"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

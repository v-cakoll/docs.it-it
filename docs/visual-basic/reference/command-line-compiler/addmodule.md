---
title: /addmodule | Documenti di Microsoft
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
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
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
ms.openlocfilehash: 2db0db5b5dd94f03e67d8680624e2a4ad23587f7
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="addmodule"></a><span data-ttu-id="2b180-102">/addmodule</span><span class="sxs-lookup"><span data-stu-id="2b180-102">/addmodule</span></span>
<span data-ttu-id="2b180-103">Fa sì che il compilatore renda disponibili per il progetto in compilazione tutte le informazioni sui tipi presenti nei file specificati.</span><span class="sxs-lookup"><span data-stu-id="2b180-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b180-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b180-104">Syntax</span></span>  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b180-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2b180-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="2b180-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2b180-106">Required.</span></span> <span data-ttu-id="2b180-107">Elenco delimitato da virgole di file che contengono metadati ma non contengono manifesti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2b180-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="2b180-108">I nomi di file contenenti spazi devono essere racchiusi tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="2b180-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b180-109">Note</span><span class="sxs-lookup"><span data-stu-id="2b180-109">Remarks</span></span>  
 <span data-ttu-id="2b180-110">I file elencati mediante il `fileList` parametro deve essere creato con il `/target:module` opzione o con equivalente del compilatore `/target:module`.</span><span class="sxs-lookup"><span data-stu-id="2b180-110">The files listed by the `fileList` parameter must be created with the `/target:module` option, or with another compiler's equivalent to `/target:module`.</span></span>  
  
 <span data-ttu-id="2b180-111">Tutti i moduli aggiunti con `/addmodule` deve essere nella stessa directory del file di output in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2b180-111">All modules added with `/addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="2b180-112">Ovvero, è possibile specificare un modulo in una directory in fase di compilazione, ma il modulo deve essere nella directory dell'applicazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2b180-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="2b180-113">In caso contrario, si ottiene un <xref:System.TypeLoadException>errore.</xref:System.TypeLoadException></span><span class="sxs-lookup"><span data-stu-id="2b180-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="2b180-114">Se si specifica, in modo implicito o esplicito, qualsiasi[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) opzione diversa da `/target:module` con `/addmodule`, i file si passa a `/addmodule` diventano parte dell'assembly del progetto.</span><span class="sxs-lookup"><span data-stu-id="2b180-114">If you specify (implicitly or explicitly) any[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `/target:module` with `/addmodule`, the files you pass to `/addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="2b180-115">Un assembly è necessario per eseguire un file di output che contiene uno o più file aggiunti con `/addmodule`.</span><span class="sxs-lookup"><span data-stu-id="2b180-115">An assembly is required to run an output file that has one or more files added with `/addmodule`.</span></span>  
  
 <span data-ttu-id="2b180-116">Utilizzare [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) per importare i metadati da un file contenente un assembly.</span><span class="sxs-lookup"><span data-stu-id="2b180-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b180-117">Il `/addmodule` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2b180-117">The `/addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b180-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b180-118">Example</span></span>  
 <span data-ttu-id="2b180-119">Il codice seguente crea un modulo.</span><span class="sxs-lookup"><span data-stu-id="2b180-119">The following code creates a module.</span></span>  
  
 <span data-ttu-id="2b180-120">[!code-vb[VbVbalrCompiler&#47;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b180-120">[!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]</span></span>  
  
 <span data-ttu-id="2b180-121">Il codice seguente consente di importare i tipi del modulo.</span><span class="sxs-lookup"><span data-stu-id="2b180-121">The following code imports the module's types.</span></span>  
  
 <span data-ttu-id="2b180-122">[!code-vb[VbVbalrCompiler n.&48;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b180-122">[!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]</span></span>  
  
 <span data-ttu-id="2b180-123">Quando si esegue `t1`, viene restituito `802`.</span><span class="sxs-lookup"><span data-stu-id="2b180-123">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b180-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b180-124">See Also</span></span>  
 <span data-ttu-id="2b180-125">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b180-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2b180-126"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="2b180-126"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="2b180-127"> [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="2b180-127"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="2b180-128"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="2b180-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

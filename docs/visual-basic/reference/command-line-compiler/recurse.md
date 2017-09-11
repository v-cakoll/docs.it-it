---
title: /recurse | Documenti di Microsoft
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
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
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
ms.openlocfilehash: 9ceb2f3bc9e4d0f1088258f504b7a49c58a29e35
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="recurse"></a><span data-ttu-id="27485-102">/recurse</span><span class="sxs-lookup"><span data-stu-id="27485-102">/recurse</span></span>
<span data-ttu-id="27485-103">Compila i file di codice sorgente in tutte le directory figlio della directory specificata o della directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="27485-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27485-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27485-104">Syntax</span></span>  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="27485-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="27485-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="27485-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27485-106">Optional.</span></span> <span data-ttu-id="27485-107">La directory in cui si desidera eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="27485-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="27485-108">Se non specificato, la ricerca inizia nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="27485-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="27485-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="27485-109">Required.</span></span> <span data-ttu-id="27485-110">I file da cercare.</span><span class="sxs-lookup"><span data-stu-id="27485-110">The file(s) to search for.</span></span> <span data-ttu-id="27485-111">Caratteri jolly sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="27485-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27485-112">Note</span><span class="sxs-lookup"><span data-stu-id="27485-112">Remarks</span></span>  
 <span data-ttu-id="27485-113">È possibile utilizzare caratteri jolly in un nome file per compilare tutti i file corrispondenti nella directory del progetto senza utilizzare `/recurse`.</span><span class="sxs-lookup"><span data-stu-id="27485-113">You can use wildcards in a file name to compile all matching files in the project directory without using `/recurse`.</span></span> <span data-ttu-id="27485-114">Se viene specificato alcun nome di file di output, il compilatore si basa il nome del file di output nel primo file di input elaborato.</span><span class="sxs-lookup"><span data-stu-id="27485-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="27485-115">Si tratta in genere il primo file nell'elenco dei file compilati ordinati alfabeticamente.</span><span class="sxs-lookup"><span data-stu-id="27485-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="27485-116">Per questo motivo, è consigliabile specificare un file di output utilizzando il `/out` (opzione).</span><span class="sxs-lookup"><span data-stu-id="27485-116">For this reason, it is best to specify an output file using the `/out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27485-117">Il `/recurse` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="27485-117">The `/recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27485-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="27485-118">Example</span></span>  
 <span data-ttu-id="27485-119">Il codice seguente consente di compilare tutti [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] file nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="27485-119">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory.</span></span>  
  
```  
vbc *.vb  
```  
  
 <span data-ttu-id="27485-120">Il codice seguente consente di compilare tutti [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] file di `Test\ABC` directory e delle directory sottostanti, quindi genera `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="27485-120">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="27485-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27485-121">See Also</span></span>  
 <span data-ttu-id="27485-122">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="27485-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="27485-123"> [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span><span class="sxs-lookup"><span data-stu-id="27485-123"> [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span></span>  
<span data-ttu-id="27485-124"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="27485-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

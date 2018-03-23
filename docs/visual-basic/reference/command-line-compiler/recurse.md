---
title: -recurse
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb1cc114c2882aa82787f94a271dd7684c716b01
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-recurse"></a><span data-ttu-id="d15c2-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="d15c2-102">-recurse</span></span>
<span data-ttu-id="d15c2-103">Compila i file di codice sorgente in tutte le directory figlio della directory specificata o della directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="d15c2-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d15c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d15c2-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d15c2-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d15c2-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="d15c2-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d15c2-106">Optional.</span></span> <span data-ttu-id="d15c2-107">La directory in cui si vuole che abbia inizio la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d15c2-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="d15c2-108">Se non specificato, la ricerca inizia nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="d15c2-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="d15c2-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d15c2-109">Required.</span></span> <span data-ttu-id="d15c2-110">I file da cercare.</span><span class="sxs-lookup"><span data-stu-id="d15c2-110">The file(s) to search for.</span></span> <span data-ttu-id="d15c2-111">È consentito l'utilizzo di caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="d15c2-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d15c2-112">Note</span><span class="sxs-lookup"><span data-stu-id="d15c2-112">Remarks</span></span>  
 <span data-ttu-id="d15c2-113">È possibile utilizzare caratteri jolly in un nome file per compilare tutti i file corrispondenti nella directory del progetto senza utilizzare `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="d15c2-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="d15c2-114">Se non viene specificato alcun nome di file di output, il compilatore si basa il nome del file di output nel primo file di input elaborato.</span><span class="sxs-lookup"><span data-stu-id="d15c2-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="d15c2-115">Si tratta in genere il primo file nell'elenco dei file compilati quando vengono visualizzati in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="d15c2-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="d15c2-116">Per questo motivo, è consigliabile specificare un file di output utilizzando il `-out` opzione.</span><span class="sxs-lookup"><span data-stu-id="d15c2-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d15c2-117">Il `-recurse` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d15c2-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d15c2-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d15c2-118">Example</span></span>  
 <span data-ttu-id="d15c2-119">Il comando seguente consente di compilare tutti [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] file nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d15c2-119">The following command compiles all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="d15c2-120">Il comando seguente consente di compilare tutti [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] file il `Test\ABC` directory e delle directory di sotto di esso, quindi genera `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="d15c2-120">The following command compiles all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d15c2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d15c2-121">See Also</span></span>  
 [<span data-ttu-id="d15c2-122">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d15c2-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d15c2-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d15c2-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)  
 [<span data-ttu-id="d15c2-124">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="d15c2-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

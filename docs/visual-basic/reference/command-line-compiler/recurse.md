---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 4281c7bf5a7972d323e1e649aaef437c7ee901ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956270"
---
# <a name="-recurse"></a><span data-ttu-id="d85ff-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="d85ff-102">-recurse</span></span>
<span data-ttu-id="d85ff-103">Compila i file del codice sorgente in tutte le directory figlio della directory specificata o della directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="d85ff-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d85ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d85ff-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d85ff-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d85ff-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="d85ff-106">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d85ff-106">Optional.</span></span> <span data-ttu-id="d85ff-107">La directory in cui si vuole che abbia inizio la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d85ff-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="d85ff-108">Se non specificato, la ricerca inizia nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="d85ff-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="d85ff-109">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="d85ff-109">Required.</span></span> <span data-ttu-id="d85ff-110">I file da cercare.</span><span class="sxs-lookup"><span data-stu-id="d85ff-110">The file(s) to search for.</span></span> <span data-ttu-id="d85ff-111">È consentito l'utilizzo di caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="d85ff-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d85ff-112">Note</span><span class="sxs-lookup"><span data-stu-id="d85ff-112">Remarks</span></span>  
 <span data-ttu-id="d85ff-113">È possibile usare caratteri jolly in un nome file per compilare tutti i file corrispondenti nella directory del progetto senza `-recurse`usare.</span><span class="sxs-lookup"><span data-stu-id="d85ff-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="d85ff-114">Se non viene specificato alcun nome file di output, il compilatore basa il nome del file di output sul primo file di input elaborato.</span><span class="sxs-lookup"><span data-stu-id="d85ff-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="d85ff-115">Si tratta in genere del primo file nell'elenco di file compilato quando viene visualizzato in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="d85ff-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="d85ff-116">Per questo motivo, è preferibile specificare un file di output usando `-out` l'opzione.</span><span class="sxs-lookup"><span data-stu-id="d85ff-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d85ff-117">L' `-recurse` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d85ff-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d85ff-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d85ff-118">Example</span></span>  
 <span data-ttu-id="d85ff-119">Il comando seguente compila tutti i file di Visual Basic nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d85ff-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="d85ff-120">Il comando seguente compila tutti i file di Visual Basic nella `Test\ABC` directory e in tutte le directory sottostanti, quindi `Test.ABC.dll`genera.</span><span class="sxs-lookup"><span data-stu-id="d85ff-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d85ff-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d85ff-121">See also</span></span>

- [<span data-ttu-id="d85ff-122">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d85ff-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d85ff-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d85ff-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="d85ff-124">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="d85ff-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

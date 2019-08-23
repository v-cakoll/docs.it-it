---
title: '@ (specificare il file di risposta) (Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: b84d50334e56305c27c5c0bc54578ba871a28365
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937289"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="d062e-102">@ (specificare il file di risposta) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d062e-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="d062e-103">Specifica un file che contiene le opzioni del compilatore e i file del codice sorgente da compilare.</span><span class="sxs-lookup"><span data-stu-id="d062e-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d062e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d062e-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d062e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d062e-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="d062e-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="d062e-106">Required.</span></span> <span data-ttu-id="d062e-107">File che elenca le opzioni del compilatore o i file del codice sorgente da compilare.</span><span class="sxs-lookup"><span data-stu-id="d062e-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="d062e-108">Racchiudere il nome file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="d062e-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d062e-109">Note</span><span class="sxs-lookup"><span data-stu-id="d062e-109">Remarks</span></span>  
 <span data-ttu-id="d062e-110">Il compilatore elabora le opzioni del compilatore e i file del codice sorgente specificati in un file di risposta come se fossero stati specificati nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d062e-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="d062e-111">Per specificare più di un file di risposta in una compilazione, specificare più opzioni del file di risposta, ad esempio la seguente.</span><span class="sxs-lookup"><span data-stu-id="d062e-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="d062e-112">In un file di risposta, più opzioni del compilatore e file del codice sorgente possono essere visualizzati in una sola riga.</span><span class="sxs-lookup"><span data-stu-id="d062e-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="d062e-113">Una singola specifica dell'opzione del compilatore deve essere visualizzata su una riga (non può estendersi su più righe).</span><span class="sxs-lookup"><span data-stu-id="d062e-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="d062e-114">I file di risposta possono avere commenti che iniziano `#` con il simbolo.</span><span class="sxs-lookup"><span data-stu-id="d062e-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="d062e-115">È possibile combinare le opzioni specificate nella riga di comando con le opzioni specificate in uno o più file di risposta.</span><span class="sxs-lookup"><span data-stu-id="d062e-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="d062e-116">Il compilatore elabora le opzioni del comando mentre le rileva.</span><span class="sxs-lookup"><span data-stu-id="d062e-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="d062e-117">Pertanto, gli argomenti della riga di comando possono eseguire l'override delle opzioni elencate in precedenza nei file di risposta.</span><span class="sxs-lookup"><span data-stu-id="d062e-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="d062e-118">Viceversa, le opzioni in un file di risposta sostituiscono le opzioni elencate in precedenza nella riga di comando o in altri file di risposta.</span><span class="sxs-lookup"><span data-stu-id="d062e-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="d062e-119">Visual Basic fornisce il file Vbc. rsp, che si trova nella stessa directory del file Vbc. exe.</span><span class="sxs-lookup"><span data-stu-id="d062e-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="d062e-120">Il file Vbc. RSP è incluso per impostazione predefinita, a `-noconfig` meno che non venga utilizzata l'opzione.</span><span class="sxs-lookup"><span data-stu-id="d062e-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="d062e-121">Per ulteriori informazioni, vedere [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="d062e-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d062e-122">L' `@` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d062e-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d062e-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="d062e-123">Example</span></span>  
 <span data-ttu-id="d062e-124">Le righe seguenti sono riportate in un file di risposta di esempio.</span><span class="sxs-lookup"><span data-stu-id="d062e-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="d062e-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="d062e-125">Example</span></span>  
 <span data-ttu-id="d062e-126">Nell'esempio seguente viene illustrato come utilizzare l' `@` opzione con il file di risposta `File1.rsp`denominato.</span><span class="sxs-lookup"><span data-stu-id="d062e-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="d062e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d062e-127">See also</span></span>

- [<span data-ttu-id="d062e-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d062e-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d062e-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="d062e-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="d062e-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="d062e-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

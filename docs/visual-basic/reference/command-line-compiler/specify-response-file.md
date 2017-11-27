---
title: '@ (specificare il file di risposta) (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ced258713983ded06fa70cb65d56071b41cdc75b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="dd64a-102">@ (specificare il file di risposta) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd64a-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="dd64a-103">Specifica un file che contiene le opzioni del compilatore e il file di codice sorgente da compilare.</span><span class="sxs-lookup"><span data-stu-id="dd64a-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd64a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd64a-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="dd64a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="dd64a-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="dd64a-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd64a-106">Required.</span></span> <span data-ttu-id="dd64a-107">Un file che elenca le opzioni del compilatore o file di codice sorgente da compilare.</span><span class="sxs-lookup"><span data-stu-id="dd64a-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="dd64a-108">Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="dd64a-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd64a-109">Note</span><span class="sxs-lookup"><span data-stu-id="dd64a-109">Remarks</span></span>  
 <span data-ttu-id="dd64a-110">Il compilatore elabora le opzioni del compilatore e i file del codice sorgente specificati in un file di risposta come se fossero stati specificati nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dd64a-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="dd64a-111">Per specificare più di un file di risposta in una compilazione, è possibile specificare più opzioni di file di risposta, ad esempio le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dd64a-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="dd64a-112">In una risposta file, più opzioni del compilatore e i file del codice sorgente possono essere visualizzati in una sola riga.</span><span class="sxs-lookup"><span data-stu-id="dd64a-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="dd64a-113">Specifica una singola opzione del compilatore deve essere presente una riga (non può estendersi su più righe).</span><span class="sxs-lookup"><span data-stu-id="dd64a-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="dd64a-114">File di risposta possono contenere commenti che iniziano con la `#` simbolo.</span><span class="sxs-lookup"><span data-stu-id="dd64a-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="dd64a-115">È possibile combinare le opzioni specificate nella riga di comando con le opzioni specificate in uno o più file di risposta.</span><span class="sxs-lookup"><span data-stu-id="dd64a-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="dd64a-116">Il compilatore elabora le opzioni di comando quando vengono rilevate.</span><span class="sxs-lookup"><span data-stu-id="dd64a-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="dd64a-117">Di conseguenza, gli argomenti della riga di comando possono eseguire l'override opzioni elencate in precedenza nel file di risposta.</span><span class="sxs-lookup"><span data-stu-id="dd64a-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="dd64a-118">Al contrario, le opzioni in un file di risposta ignorano le opzioni elencate in precedenza nella riga di comando o in altri file di risposta.</span><span class="sxs-lookup"><span data-stu-id="dd64a-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="dd64a-119">Visual Basic fornisce tale file si trova nella stessa directory del file Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="dd64a-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="dd64a-120">Tale file è incluso per impostazione predefinita, a meno che il `/noconfig` viene utilizzata l'opzione.</span><span class="sxs-lookup"><span data-stu-id="dd64a-120">The Vbc.rsp file is included by default, unless the `/noconfig` option is used.</span></span> <span data-ttu-id="dd64a-121">Per ulteriori informazioni, vedere [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="dd64a-121">For more information, see [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd64a-122">Il `@` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dd64a-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd64a-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd64a-123">Example</span></span>  
 <span data-ttu-id="dd64a-124">Le righe seguenti sono da un file di risposta di esempio.</span><span class="sxs-lookup"><span data-stu-id="dd64a-124">The following lines are from a sample response file.</span></span>  
  
```  
# build the first output file  
/target:exe   
/out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="dd64a-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd64a-125">Example</span></span>  
 <span data-ttu-id="dd64a-126">Nell'esempio seguente viene illustrato come utilizzare il `@` opzione con il file di risposta denominato `File1.rsp`.</span><span class="sxs-lookup"><span data-stu-id="dd64a-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```  
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd64a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd64a-127">See Also</span></span>  
 [<span data-ttu-id="dd64a-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd64a-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="dd64a-129">/noconfig</span><span class="sxs-lookup"><span data-stu-id="dd64a-129">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="dd64a-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="dd64a-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

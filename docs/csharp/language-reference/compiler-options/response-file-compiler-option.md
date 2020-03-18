---
title: '@ (opzioni del compilatore C#)'
ms.date: 07/20/2015
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
ms.openlocfilehash: d8e5c0ec148754c3e4cebfa32ad9f44a0bb0119e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70202905"
---
# <a name="-c-compiler-options"></a><span data-ttu-id="5d73b-102">@ (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="5d73b-102">@ (C# Compiler Options)</span></span>
<span data-ttu-id="5d73b-103">L'opzione @ consente di specificare un file che contiene le opzioni del compilatore e i file di codice sorgente da compilare.</span><span class="sxs-lookup"><span data-stu-id="5d73b-103">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d73b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d73b-104">Syntax</span></span>  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="5d73b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5d73b-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="5d73b-106">File che elenca le opzioni del compilatore o i file di codice sorgente da compilare.</span><span class="sxs-lookup"><span data-stu-id="5d73b-106">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d73b-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5d73b-107">Remarks</span></span>  
 <span data-ttu-id="5d73b-108">Le opzioni del compilatore e i file di codice sorgente verranno elaborati dal compilatore come se fossero stati specificati nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="5d73b-108">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="5d73b-109">Per specificare più di un file di risposta in una compilazione, specificare più opzioni di file di risposta.</span><span class="sxs-lookup"><span data-stu-id="5d73b-109">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="5d73b-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5d73b-110">For example:</span></span>  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="5d73b-111">In un file di risposta, più opzioni del compilatore e file di codice sorgente possono essere contenuti in una sola riga.</span><span class="sxs-lookup"><span data-stu-id="5d73b-111">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="5d73b-112">La specificazione di una singola opzione del compilatore deve essere contenuta in una sola riga (non può estendersi su più righe).</span><span class="sxs-lookup"><span data-stu-id="5d73b-112">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="5d73b-113">I file di risposta possono contenere commenti che iniziano con il simbolo #.</span><span class="sxs-lookup"><span data-stu-id="5d73b-113">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="5d73b-114">Specificare le opzioni del compilatore da un file di risposta equivale a eseguire tali comandi dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="5d73b-114">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="5d73b-115">Per altre informazioni, vedere [Compilazione dalla riga di comando](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="5d73b-115">See [Building from the Command Line](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="5d73b-116">Il compilatore elabora le opzioni di comando quando vengono rilevate.</span><span class="sxs-lookup"><span data-stu-id="5d73b-116">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="5d73b-117">Di conseguenza, gli argomenti della riga di comando possono eseguire l'override di opzioni elencate in precedenza nei file di risposta.</span><span class="sxs-lookup"><span data-stu-id="5d73b-117">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="5d73b-118">Viceversa, le opzioni in un file di risposta eseguiranno l'override delle opzioni elencate in precedenza nella riga di comando o in altri file di risposta.</span><span class="sxs-lookup"><span data-stu-id="5d73b-118">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="5d73b-119">In C# è disponibile il file csc.rsp, che si trova nella stessa directory del file csc.exe.</span><span class="sxs-lookup"><span data-stu-id="5d73b-119">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="5d73b-120">Vedere [-noconfig](./noconfig-compiler-option.md) per ulteriori informazioni su csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="5d73b-120">See [-noconfig](./noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="5d73b-121">Questa opzione del compilatore non può essere impostata nell'ambiente di sviluppo di Visual Studio, né modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="5d73b-121">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d73b-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d73b-122">Example</span></span>  
 <span data-ttu-id="5d73b-123">Di seguito sono riportate alcune righe da un file di risposta di esempio:</span><span class="sxs-lookup"><span data-stu-id="5d73b-123">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d73b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d73b-124">See also</span></span>

- [<span data-ttu-id="5d73b-125">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="5d73b-125">C# Compiler Options</span></span>](./index.md)

---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: fbe3634d1fbc03acd56ef7276d65fd54493b9806
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002410"
---
# <a name="-addmodule"></a><span data-ttu-id="33ccc-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="33ccc-102">-addmodule</span></span>
<span data-ttu-id="33ccc-103">Fa sì che il compilatore renda disponibili per il progetto in compilazione tutte le informazioni sui tipi presenti nei file specificati.</span><span class="sxs-lookup"><span data-stu-id="33ccc-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33ccc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33ccc-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="33ccc-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="33ccc-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="33ccc-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="33ccc-106">Required.</span></span> <span data-ttu-id="33ccc-107">Elenco delimitato da virgole di file che contengono metadati ma che non contengono manifesti di assembly.</span><span class="sxs-lookup"><span data-stu-id="33ccc-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="33ccc-108">I nomi di file contenenti spazi devono essere racchiusi tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="33ccc-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33ccc-109">Note</span><span class="sxs-lookup"><span data-stu-id="33ccc-109">Remarks</span></span>  
 <span data-ttu-id="33ccc-110">I file elencati dal parametro `fileList` devono essere creati con l'opzione `-target:module` o con un altro compilatore equivalente a `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="33ccc-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="33ccc-111">Tutti i moduli aggiunti con `-addmodule` devono trovarsi nella stessa directory del file di output in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="33ccc-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="33ccc-112">In altre termini, è possibile specificare un modulo in qualsiasi directory in fase di compilazione, ma il modulo deve trovarsi nella directory dell'applicazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="33ccc-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="33ccc-113">In caso contrario, viene ricevuto un errore <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="33ccc-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="33ccc-114">Se si specifica (in modo implicito o esplicito) qualsiasi opzione di[destinazione (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) diversa da `-target:module` con `-addmodule`, i file passati a `-addmodule` diventano parte dell'assembly del progetto.</span><span class="sxs-lookup"><span data-stu-id="33ccc-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="33ccc-115">Per eseguire un file di output con uno o più file aggiunti con `-addmodule`, è necessario un assembly.</span><span class="sxs-lookup"><span data-stu-id="33ccc-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="33ccc-116">Usare [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) per importare metadati da un file che contiene un assembly.</span><span class="sxs-lookup"><span data-stu-id="33ccc-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33ccc-117">L'opzione `-addmodule` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="33ccc-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33ccc-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="33ccc-118">Example</span></span>  
 <span data-ttu-id="33ccc-119">Il codice seguente crea un modulo.</span><span class="sxs-lookup"><span data-stu-id="33ccc-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="33ccc-120">Il codice seguente importa i tipi del modulo.</span><span class="sxs-lookup"><span data-stu-id="33ccc-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="33ccc-121">Quando si esegue `t1`, viene restituito `802`.</span><span class="sxs-lookup"><span data-stu-id="33ccc-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ccc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33ccc-122">See also</span></span>

- [<span data-ttu-id="33ccc-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33ccc-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="33ccc-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33ccc-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="33ccc-125">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33ccc-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="33ccc-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="33ccc-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

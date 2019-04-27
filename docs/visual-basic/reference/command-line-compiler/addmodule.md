---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2de5fe82f1969a2fdb305d45951d7d698252c0c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61839218"
---
# <a name="-addmodule"></a><span data-ttu-id="20adb-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="20adb-102">-addmodule</span></span>
<span data-ttu-id="20adb-103">Fa sì che il compilatore renda disponibili per il progetto in compilazione tutte le informazioni sui tipi presenti nei file specificati.</span><span class="sxs-lookup"><span data-stu-id="20adb-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20adb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20adb-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="20adb-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="20adb-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="20adb-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="20adb-106">Required.</span></span> <span data-ttu-id="20adb-107">Elenco delimitato da virgole di file che contengono i metadati, ma non contengono manifesti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="20adb-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="20adb-108">I nomi di file contenenti spazi devono essere racchiusi tra virgolette doppie ("").</span><span class="sxs-lookup"><span data-stu-id="20adb-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20adb-109">Note</span><span class="sxs-lookup"><span data-stu-id="20adb-109">Remarks</span></span>  
 <span data-ttu-id="20adb-110">I file elencati in base al `fileList` parametro deve essere creato con il `-target:module` opzione, o con equivalente un'altra del compilatore `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="20adb-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="20adb-111">Tutti i moduli aggiunti con `-addmodule` deve essere nella stessa directory del file di output in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="20adb-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="20adb-112">Vale a dire, è possibile specificare un modulo in qualsiasi directory in fase di compilazione, ma il modulo deve essere nella directory dell'applicazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="20adb-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="20adb-113">In caso contrario, otterrai un <xref:System.TypeLoadException> errore.</span><span class="sxs-lookup"><span data-stu-id="20adb-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="20adb-114">Se si specificano (in modo implicito o esplicito) eventuali[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) opzione diverso da `-target:module` con `-addmodule`, i file passati alla `-addmodule` diventano parte dell'assembly del progetto.</span><span class="sxs-lookup"><span data-stu-id="20adb-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="20adb-115">Un assembly è necessario per eseguire un file di output che contiene uno o più file aggiunti con `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="20adb-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="20adb-116">Uso [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) per importare metadati da un file contenente un assembly.</span><span class="sxs-lookup"><span data-stu-id="20adb-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20adb-117">Il `-addmodule` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="20adb-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20adb-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="20adb-118">Example</span></span>  
 <span data-ttu-id="20adb-119">Il codice seguente crea un modulo.</span><span class="sxs-lookup"><span data-stu-id="20adb-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="20adb-120">Il codice seguente importa i tipi del modulo.</span><span class="sxs-lookup"><span data-stu-id="20adb-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="20adb-121">Quando si esegue `t1`, restituisce come output `802`.</span><span class="sxs-lookup"><span data-stu-id="20adb-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20adb-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20adb-122">See also</span></span>

- [<span data-ttu-id="20adb-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20adb-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="20adb-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20adb-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="20adb-125">-riferimenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20adb-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="20adb-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="20adb-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

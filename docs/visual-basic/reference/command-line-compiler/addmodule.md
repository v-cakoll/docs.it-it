---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2fefdf81ab25d2e109f265f0c895a3415ad5673d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656006"
---
# <a name="-addmodule"></a><span data-ttu-id="b996a-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="b996a-102">-addmodule</span></span>
<span data-ttu-id="b996a-103">Fa sì che il compilatore renda disponibili per il progetto in compilazione tutte le informazioni sui tipi presenti nei file specificati.</span><span class="sxs-lookup"><span data-stu-id="b996a-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b996a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b996a-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="b996a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b996a-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="b996a-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b996a-106">Required.</span></span> <span data-ttu-id="b996a-107">Elenco delimitato da virgole dei file che contengono i metadati, ma non contengono manifesti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b996a-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="b996a-108">I nomi di file contenenti spazi devono essere racchiusi tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="b996a-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b996a-109">Note</span><span class="sxs-lookup"><span data-stu-id="b996a-109">Remarks</span></span>  
 <span data-ttu-id="b996a-110">I file elencati mediante il `fileList` parametro deve essere creato con il `-target:module` opzione o con equivalente del compilatore `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="b996a-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="b996a-111">Tutti i moduli aggiunti con `-addmodule` deve essere nella stessa directory del file di output in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b996a-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="b996a-112">Ovvero, è possibile specificare un modulo in qualsiasi directory in fase di compilazione, ma il modulo deve essere nella directory dell'applicazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b996a-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="b996a-113">In caso contrario, viene visualizzato un <xref:System.TypeLoadException> errore.</span><span class="sxs-lookup"><span data-stu-id="b996a-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="b996a-114">Se si specifica, in modo implicito o esplicito, qualsiasi[-destinazione (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) opzione diverso `-target:module` con `-addmodule`, i file passati a `-addmodule` diventano parte dell'assembly del progetto.</span><span class="sxs-lookup"><span data-stu-id="b996a-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="b996a-115">È necessario un assembly per l'esecuzione di un file di output che contiene uno o più file aggiunti con `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="b996a-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="b996a-116">Utilizzare [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) per importare i metadati da un file contenente un assembly.</span><span class="sxs-lookup"><span data-stu-id="b996a-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b996a-117">Il `-addmodule` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b996a-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b996a-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="b996a-118">Example</span></span>  
 <span data-ttu-id="b996a-119">Il codice seguente crea un modulo.</span><span class="sxs-lookup"><span data-stu-id="b996a-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 <span data-ttu-id="b996a-120">Il codice riportato di seguito Importa i tipi del modulo.</span><span class="sxs-lookup"><span data-stu-id="b996a-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 <span data-ttu-id="b996a-121">Quando si esegue `t1`, restituisce come output `802`.</span><span class="sxs-lookup"><span data-stu-id="b996a-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b996a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b996a-122">See Also</span></span>  
 [<span data-ttu-id="b996a-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b996a-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b996a-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b996a-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="b996a-125">-riferimenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b996a-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="b996a-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="b996a-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

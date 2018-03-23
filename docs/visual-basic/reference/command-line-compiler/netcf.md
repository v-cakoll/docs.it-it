---
title: -netcf
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82a0adc9e821df3a789cf19e798d4bad9e9a69e3
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-netcf"></a><span data-ttu-id="6e07e-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="6e07e-102">-netcf</span></span>
<span data-ttu-id="6e07e-103">Imposta il compilatore in modo che punti a [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e07e-103">Sets the compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e07e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e07e-104">Syntax</span></span>  
  
```  
-netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e07e-105">Note</span><span class="sxs-lookup"><span data-stu-id="6e07e-105">Remarks</span></span>  
 <span data-ttu-id="6e07e-106">Il `-netcf` opzione cause di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore di destinazione di [!INCLUDE[Compact](~/includes/compact-md.md)] anziché la versione completa [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e07e-106">The `-netcf` option causes the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)] rather than the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="6e07e-107">Funzionalità di linguaggio che è presente solo nella versione completa [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="6e07e-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="6e07e-108">Il `-netcf` opzione è progettata per essere utilizzato con [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="6e07e-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="6e07e-109">Le funzionalità del linguaggio per disabilitato `-netcf` sono le stesse funzionalità di linguaggio non presente nel file di destinazione con `-sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="6e07e-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e07e-110">Il `-netcf` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6e07e-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="6e07e-111">Il `-netcf` opzione viene impostata quando un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] viene caricato il progetto di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6e07e-111">The `-netcf` option is set when a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="6e07e-112">Il `-netcf` opzione consente di modificare le funzionalità del linguaggio seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e07e-112">The `-netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="6e07e-113">Il [fine \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) (parola chiave), che termina l'esecuzione di un programma, è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="6e07e-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="6e07e-114">Il seguente programma compilato ed eseguito senza `-netcf` ma non riesce in fase di compilazione con `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="6e07e-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   <span data-ttu-id="6e07e-115">L'associazione tardiva, in tutti i form, è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="6e07e-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="6e07e-116">Quando si verificano gli scenari di associazione tardiva riconosciuti, vengono generati errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6e07e-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="6e07e-117">Il seguente programma compilato ed eseguito senza `-netcf` ma non riesce in fase di compilazione con `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="6e07e-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   <span data-ttu-id="6e07e-118">Il [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), e [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificatori sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="6e07e-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="6e07e-119">La sintassi del [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) istruzione viene modificata anche a `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="6e07e-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="6e07e-120">Il codice seguente viene illustrato l'effetto di `-netcf` su una compilazione.</span><span class="sxs-lookup"><span data-stu-id="6e07e-120">The following code shows the effect of `-netcf` on a compilation.</span></span>  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   <span data-ttu-id="6e07e-121">Utilizzo delle parole chiave di Visual Basic 6.0 che sono stati rimossi da [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] genera un errore diverso quando `-netcf` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6e07e-121">Using Visual Basic 6.0 keywords that were removed from [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="6e07e-122">Questo riguarda i messaggi di errore per le parole chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e07e-122">This affects the error messages for the following keywords:</span></span>  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a><span data-ttu-id="6e07e-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e07e-123">Example</span></span>  
 <span data-ttu-id="6e07e-124">Il codice seguente Compila `Myfile.vb` con il [!INCLUDE[Compact](~/includes/compact-md.md)], usando le versioni dei file mscorlib.dll e Microsoft.VisualBasic.dll trovato nella directory di installazione predefinita di [!INCLUDE[Compact](~/includes/compact-md.md)] nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="6e07e-124">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="6e07e-125">In genere, si utilizzerà la versione più recente di [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e07e-125">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e07e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e07e-126">See Also</span></span>  
 [<span data-ttu-id="6e07e-127">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e07e-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="6e07e-128">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="6e07e-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="6e07e-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="6e07e-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)

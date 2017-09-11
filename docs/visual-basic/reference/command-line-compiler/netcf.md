---
title: /netcf | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- netcf
dev_langs:
- VB
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: 18
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
ms.openlocfilehash: 375ec79fe2bf63bc03988ecaad877eb27f43d55b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="netcf"></a><span data-ttu-id="f3de6-102">/netcf</span><span class="sxs-lookup"><span data-stu-id="f3de6-102">/netcf</span></span>
<span data-ttu-id="f3de6-103">Imposta il compilatore in modo che punti a [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3de6-103">Sets the compiler to target the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3de6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3de6-104">Syntax</span></span>  
  
```  
/netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="f3de6-105">Note</span><span class="sxs-lookup"><span data-stu-id="f3de6-105">Remarks</span></span>  
 <span data-ttu-id="f3de6-106">Il `/netcf` opzione il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore alla destinazione di [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] anziché l'intero [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3de6-106">The `/netcf` option causes the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to target the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] rather than the full [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="f3de6-107">Funzionalità di linguaggio che è presente solo nella versione completa [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="f3de6-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="f3de6-108">Il `/netcf` opzione è progettata per essere utilizzato con [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="f3de6-108">The `/netcf` option is designed to be used with [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="f3de6-109">Le funzionalità di linguaggio disabilitate da `/netcf` sono le stesse funzionalità di linguaggio non presenti nel file di destinazione con `/sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="f3de6-109">The language features disabled by `/netcf` are the same language features not present in the files targeted with `/sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3de6-110">Il `/netcf` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f3de6-110">The `/netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="f3de6-111">Il `/netcf` opzione viene impostata quando un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] dispositivo progetto viene caricato.</span><span class="sxs-lookup"><span data-stu-id="f3de6-111">The `/netcf` option is set when a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="f3de6-112">Il `/netcf` opzione consente di modificare le funzionalità del linguaggio seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3de6-112">The `/netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="f3de6-113">Il [End \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) (parola chiave), che termina l'esecuzione di un programma, è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="f3de6-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="f3de6-114">Il seguente programma compilato ed eseguito senza `/netcf` ma non riesce in fase di compilazione con `/netcf`.</span><span class="sxs-lookup"><span data-stu-id="f3de6-114">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     <span data-ttu-id="f3de6-115">[!code-vb[VbVbalrCompiler&#34;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3de6-115">[!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]</span></span>  
  
-   <span data-ttu-id="f3de6-116">L'associazione tardiva, in tutti i form, è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f3de6-116">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="f3de6-117">Quando vengono rilevati gli scenari di associazione tardiva riconosciuti, vengono generati errori in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f3de6-117">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="f3de6-118">Il seguente programma compilato ed eseguito senza `/netcf` ma non riesce in fase di compilazione con `/netcf`.</span><span class="sxs-lookup"><span data-stu-id="f3de6-118">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     <span data-ttu-id="f3de6-119">[!code-vb[VbVbalrCompiler&#35;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3de6-119">[!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]</span></span>  
  
-   <span data-ttu-id="f3de6-120">Il [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), e [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificatori sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="f3de6-120">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="f3de6-121">La sintassi di [l'istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) istruzione viene inoltre modificata in `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="f3de6-121">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="f3de6-122">Il codice seguente viene illustrato l'effetto di `/netcf` su una compilazione.</span><span class="sxs-lookup"><span data-stu-id="f3de6-122">The following code shows the effect of `/netcf` on a compilation.</span></span>  
  
     <span data-ttu-id="f3de6-123">[!code-vb[VbVbalrCompiler&#36;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3de6-123">[!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]</span></span>  
  
-   <span data-ttu-id="f3de6-124">Utilizzando le parole chiave Visual Basic 6.0 che sono stati rimossi dalla [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] genera un errore diverso quando `/netcf` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="f3de6-124">Using Visual Basic 6.0 keywords that were removed from [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generates a different error when `/netcf` is used.</span></span> <span data-ttu-id="f3de6-125">Ciò influisce sui messaggi di errore per le parole chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3de6-125">This affects the error messages for the following keywords:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="f3de6-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3de6-126">Example</span></span>  
 <span data-ttu-id="f3de6-127">Il codice seguente Compila `Myfile.vb` con il [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], con le versioni di mscorlib. dll e Microsoft.VisualBasic.dll trovato nella directory di installazione predefinita di [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="f3de6-127">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] on the C drive.</span></span> <span data-ttu-id="f3de6-128">In genere, si utilizzerà la versione più recente di [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3de6-128">Typically, you would use the most recent version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3de6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3de6-129">See Also</span></span>  
 <span data-ttu-id="f3de6-130">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3de6-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f3de6-131"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="f3de6-131"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="f3de6-132"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span><span class="sxs-lookup"><span data-stu-id="f3de6-132"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span></span>

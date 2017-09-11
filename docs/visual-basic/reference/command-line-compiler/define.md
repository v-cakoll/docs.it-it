---
title: /define (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: 15
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
ms.openlocfilehash: e4eac32b4ab7259b9d3fd2ec37e21406c4cec326
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="define-visual-basic"></a><span data-ttu-id="aaa9f-102">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aaa9f-102">/define (Visual Basic)</span></span>
<span data-ttu-id="aaa9f-103">Definisce le costanti del compilatore condizionali.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa9f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aaa9f-104">Syntax</span></span>  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="aaa9f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="aaa9f-105">Arguments</span></span>  
  
|<span data-ttu-id="aaa9f-106">Termine</span><span class="sxs-lookup"><span data-stu-id="aaa9f-106">Term</span></span>|<span data-ttu-id="aaa9f-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="aaa9f-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="aaa9f-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-108">Required.</span></span> <span data-ttu-id="aaa9f-109">Il simbolo da definire.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="aaa9f-110">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-110">Optional.</span></span> <span data-ttu-id="aaa9f-111">Il valore da assegnare a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-111">The value to assign `symbol`.</span></span> <span data-ttu-id="aaa9f-112">Se `value` è una stringa, deve essere racchiuso tra sequenze di barre rovesciate/virgolette (\\") anziché tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="aaa9f-113">Se non è specificato un valore, è considerato True.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaa9f-114">Note</span><span class="sxs-lookup"><span data-stu-id="aaa9f-114">Remarks</span></span>  
 <span data-ttu-id="aaa9f-115">L'opzione `/define` ha un effetto analogo all'uso di una direttiva per il preprocessore `#Const` nel file di origine, ad eccezione del fatto che le costanti definite con `/define` sono pubbliche e si applicano a tutti i file del progetto.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-115">The `/define` option has an effect  similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `/define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="aaa9f-116">È possibile usare i simboli creati mediante questa opzione con la direttiva `#If`...`Then`...`#Else` per eseguire la compilazione condizionale dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="aaa9f-117">`/d` è la versione abbreviata di `/define`.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-117">`/d` is the short form of `/define`.</span></span>  
  
 <span data-ttu-id="aaa9f-118">È possibile definire più simboli con `/define`, separando le definizioni dei simboli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-118">You can define multiple symbols with `/define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="aaa9f-119">Per impostare /define nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aaa9f-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="aaa9f-120">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="aaa9f-121">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-121">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="aaa9f-122">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="aaa9f-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="aaa9f-123">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="aaa9f-124">3.  Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="aaa9f-125">4.  Modificare il valore di **costanti personalizzate** casella.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="aaa9f-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="aaa9f-126">Example</span></span>  
 <span data-ttu-id="aaa9f-127">Nel codice seguente sono definite e usate due costanti di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="aaa9f-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 <span data-ttu-id="aaa9f-128">[!code-vb[N. VbVbalrCompiler&45;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="aaa9f-128">[!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa9f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaa9f-129">See Also</span></span>  
 <span data-ttu-id="aaa9f-130">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="aaa9f-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="aaa9f-131"> [#If... Then... #Else direttive](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="aaa9f-131"> [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="aaa9f-132"> [#Const (direttiva)](../../../visual-basic/language-reference/directives/const-directive.md) </span><span class="sxs-lookup"><span data-stu-id="aaa9f-132"> [#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) </span></span>  
<span data-ttu-id="aaa9f-133"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="aaa9f-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

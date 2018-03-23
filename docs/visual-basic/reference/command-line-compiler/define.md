---
title: -definire (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 136339c84ce80bff790c6683eef76065fb6d71ef
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-define-visual-basic"></a><span data-ttu-id="94265-102">-definire (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94265-102">-define (Visual Basic)</span></span>
<span data-ttu-id="94265-103">Definisce le costanti del compilatore condizionali.</span><span class="sxs-lookup"><span data-stu-id="94265-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94265-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94265-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="94265-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="94265-105">Arguments</span></span>  
  
|<span data-ttu-id="94265-106">Termine</span><span class="sxs-lookup"><span data-stu-id="94265-106">Term</span></span>|<span data-ttu-id="94265-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="94265-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="94265-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="94265-108">Required.</span></span> <span data-ttu-id="94265-109">Il simbolo da definire.</span><span class="sxs-lookup"><span data-stu-id="94265-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="94265-110">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="94265-110">Optional.</span></span> <span data-ttu-id="94265-111">Il valore da assegnare a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="94265-111">The value to assign `symbol`.</span></span> <span data-ttu-id="94265-112">Se `value` è una stringa, deve essere racchiuso tra sequenze di barre rovesciate/virgolette (\\") anziché tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="94265-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="94265-113">Se non è specificato un valore, è considerato True.</span><span class="sxs-lookup"><span data-stu-id="94265-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94265-114">Note</span><span class="sxs-lookup"><span data-stu-id="94265-114">Remarks</span></span>  
 <span data-ttu-id="94265-115">Il `-define` opzione ha un effetto analogo all'utilizzo di un `#Const` direttiva per il preprocessore nel file di origine, ad eccezione che le costanti definite con `-define` sono pubblici e si applicano a tutti i file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="94265-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="94265-116">È possibile usare i simboli creati mediante questa opzione con la direttiva `#If`...`Then`...`#Else` per eseguire la compilazione condizionale dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="94265-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="94265-117">`-d` è la versione abbreviata di `-define`.</span><span class="sxs-lookup"><span data-stu-id="94265-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="94265-118">È possibile definire più simboli con `-define`, separando le definizioni dei simboli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="94265-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="94265-119">Per impostare /define nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94265-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="94265-120">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="94265-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="94265-121">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="94265-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="94265-122">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="94265-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="94265-123">3.  Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="94265-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="94265-124">4.  Modificare il valore di **costanti personalizzate** casella.</span><span class="sxs-lookup"><span data-stu-id="94265-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94265-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="94265-125">Example</span></span>  
 <span data-ttu-id="94265-126">Nel codice seguente sono definite e usate due costanti di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="94265-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="94265-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94265-127">See Also</span></span>  
 [<span data-ttu-id="94265-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94265-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="94265-129">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="94265-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="94265-130">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="94265-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="94265-131">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="94265-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

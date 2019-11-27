---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: fd0875f09bf3ba7211ede500aa0da45f8b7cd2c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344769"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="45db4-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45db4-102">-define (Visual Basic)</span></span>
<span data-ttu-id="45db4-103">Definisce le costanti del compilatore condizionali.</span><span class="sxs-lookup"><span data-stu-id="45db4-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45db4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45db4-104">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="45db4-105">oppure</span><span class="sxs-lookup"><span data-stu-id="45db4-105">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="45db4-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="45db4-106">Arguments</span></span>  
  
|<span data-ttu-id="45db4-107">Termine</span><span class="sxs-lookup"><span data-stu-id="45db4-107">Term</span></span>|<span data-ttu-id="45db4-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="45db4-108">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="45db4-109">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="45db4-109">Required.</span></span> <span data-ttu-id="45db4-110">Il simbolo da definire.</span><span class="sxs-lookup"><span data-stu-id="45db4-110">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="45db4-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="45db4-111">Optional.</span></span> <span data-ttu-id="45db4-112">Il valore da assegnare a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="45db4-112">The value to assign `symbol`.</span></span> <span data-ttu-id="45db4-113">Se `value` è una stringa, deve essere racchiusa tra sequenze di barra rovesciata/virgolette (\\") anziché virgolette.</span><span class="sxs-lookup"><span data-stu-id="45db4-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="45db4-114">Se non è specificato un valore, è considerato True.</span><span class="sxs-lookup"><span data-stu-id="45db4-114">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45db4-115">Note</span><span class="sxs-lookup"><span data-stu-id="45db4-115">Remarks</span></span>  
 <span data-ttu-id="45db4-116">L'opzione `-define` ha un effetto simile all'uso di una direttiva per il preprocessore `#Const` nel file di origine, ad eccezione del fatto che le costanti definite con `-define` sono pubbliche e si applicano a tutti i file del progetto.</span><span class="sxs-lookup"><span data-stu-id="45db4-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="45db4-117">È possibile usare i simboli creati mediante questa opzione con la direttiva `#If`...`Then`...`#Else` per eseguire la compilazione condizionale dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="45db4-117">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="45db4-118">`-d` è la forma abbreviata di `-define`.</span><span class="sxs-lookup"><span data-stu-id="45db4-118">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="45db4-119">È possibile definire più simboli con `-define`, separando le definizioni dei simboli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="45db4-119">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="45db4-120">Per impostare /define nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="45db4-120">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="45db4-121">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="45db4-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="45db4-122">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="45db4-122">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="45db4-123">2. fare clic sulla scheda **Compila** .</span><span class="sxs-lookup"><span data-stu-id="45db4-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="45db4-124">3. fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="45db4-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="45db4-125">4. modificare il valore nella casella **costanti personalizzate** .</span><span class="sxs-lookup"><span data-stu-id="45db4-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="45db4-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="45db4-126">Example</span></span>  
 <span data-ttu-id="45db4-127">Nel codice seguente sono definite e usate due costanti di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="45db4-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="45db4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45db4-128">See also</span></span>

- [<span data-ttu-id="45db4-129">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45db4-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="45db4-130">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="45db4-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="45db4-131">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="45db4-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="45db4-132">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="45db4-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

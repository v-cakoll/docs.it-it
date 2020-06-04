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
ms.openlocfilehash: d0d1b03d9ab98f28a0112198f1ecc1e928d6d4a7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408712"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="425ca-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="425ca-102">-define (Visual Basic)</span></span>
<span data-ttu-id="425ca-103">Definisce le costanti del compilatore condizionali.</span><span class="sxs-lookup"><span data-stu-id="425ca-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="425ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="425ca-104">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="425ca-105">Oppure</span><span class="sxs-lookup"><span data-stu-id="425ca-105">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="425ca-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="425ca-106">Arguments</span></span>  
  
|<span data-ttu-id="425ca-107">Termine</span><span class="sxs-lookup"><span data-stu-id="425ca-107">Term</span></span>|<span data-ttu-id="425ca-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="425ca-108">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="425ca-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="425ca-109">Required.</span></span> <span data-ttu-id="425ca-110">Il simbolo da definire.</span><span class="sxs-lookup"><span data-stu-id="425ca-110">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="425ca-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="425ca-111">Optional.</span></span> <span data-ttu-id="425ca-112">Il valore da assegnare a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="425ca-112">The value to assign `symbol`.</span></span> <span data-ttu-id="425ca-113">Se `value` è una stringa, deve essere racchiusa tra sequenze di barre rovesciate o virgolette ( \\ ") anziché virgolette.</span><span class="sxs-lookup"><span data-stu-id="425ca-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="425ca-114">Se non è specificato un valore, è considerato True.</span><span class="sxs-lookup"><span data-stu-id="425ca-114">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="425ca-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="425ca-115">Remarks</span></span>  
 <span data-ttu-id="425ca-116">L' `-define` opzione ha un effetto simile all'uso di una `#Const` direttiva per il preprocessore nel file di origine, ad eccezione del fatto che le costanti definite con `-define` sono pubbliche e si applicano a tutti i file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="425ca-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="425ca-117">È possibile usare i simboli creati mediante questa opzione con la direttiva `#If`...`Then`...`#Else` per eseguire la compilazione condizionale dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="425ca-117">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="425ca-118">`-d` è la versione abbreviata di `-define`.</span><span class="sxs-lookup"><span data-stu-id="425ca-118">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="425ca-119">È possibile definire più simboli con `-define`, separando le definizioni dei simboli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="425ca-119">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="425ca-120">Per impostare-define in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="425ca-120">To set -define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="425ca-121">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="425ca-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="425ca-122">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="425ca-122">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="425ca-123">2. fare clic sulla scheda **Compila** .</span><span class="sxs-lookup"><span data-stu-id="425ca-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="425ca-124">3. fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="425ca-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="425ca-125">4. modificare il valore nella casella **costanti personalizzate** .</span><span class="sxs-lookup"><span data-stu-id="425ca-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="425ca-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="425ca-126">Example</span></span>  
 <span data-ttu-id="425ca-127">Nel codice seguente sono definite e usate due costanti di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="425ca-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="425ca-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="425ca-128">See also</span></span>

- [<span data-ttu-id="425ca-129">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="425ca-129">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="425ca-130">#If... Direttive then... #Else</span><span class="sxs-lookup"><span data-stu-id="425ca-130">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="425ca-131">#Const (direttiva)</span><span class="sxs-lookup"><span data-stu-id="425ca-131">#Const Directive</span></span>](../../language-reference/directives/const-directive.md)
- [<span data-ttu-id="425ca-132">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="425ca-132">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)

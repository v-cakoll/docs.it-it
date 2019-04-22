---
title: -define (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: d0a483e7a3c9e9863db39e89d655cf172c1e8c81
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834309"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="eefde-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eefde-102">-define (Visual Basic)</span></span>
<span data-ttu-id="eefde-103">Definisce le costanti del compilatore condizionali.</span><span class="sxs-lookup"><span data-stu-id="eefde-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eefde-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eefde-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="eefde-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="eefde-105">Arguments</span></span>  
  
|<span data-ttu-id="eefde-106">Termine</span><span class="sxs-lookup"><span data-stu-id="eefde-106">Term</span></span>|<span data-ttu-id="eefde-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="eefde-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="eefde-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eefde-108">Required.</span></span> <span data-ttu-id="eefde-109">Il simbolo da definire.</span><span class="sxs-lookup"><span data-stu-id="eefde-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="eefde-110">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="eefde-110">Optional.</span></span> <span data-ttu-id="eefde-111">Il valore da assegnare a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="eefde-111">The value to assign `symbol`.</span></span> <span data-ttu-id="eefde-112">Se `value` è una stringa, deve essere racchiuso tra sequenze di barre rovesciate/virgolette (\\") anziché le virgolette.</span><span class="sxs-lookup"><span data-stu-id="eefde-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="eefde-113">Se non è specificato un valore, è considerato True.</span><span class="sxs-lookup"><span data-stu-id="eefde-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eefde-114">Note</span><span class="sxs-lookup"><span data-stu-id="eefde-114">Remarks</span></span>  
 <span data-ttu-id="eefde-115">Il `-define` opzione ha un effetto simile all'uso di un `#Const` direttiva per il preprocessore nel file di origine, ad eccezione che le costanti definite con `-define` sono pubblici e si applicano a tutti i file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="eefde-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="eefde-116">È possibile usare i simboli creati mediante questa opzione con la direttiva `#If`...`Then`...`#Else` per eseguire la compilazione condizionale dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="eefde-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="eefde-117">`-d` è la versione abbreviata di `-define`.</span><span class="sxs-lookup"><span data-stu-id="eefde-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="eefde-118">È possibile definire più simboli con `-define`, separando le definizioni dei simboli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="eefde-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="eefde-119">Per impostare /define nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eefde-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="eefde-120">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="eefde-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="eefde-121">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="eefde-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="eefde-122">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="eefde-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="eefde-123">3.  Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="eefde-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="eefde-124">4.  Modificare il valore di **stanti personalizzate** casella.</span><span class="sxs-lookup"><span data-stu-id="eefde-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eefde-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="eefde-125">Example</span></span>  
 <span data-ttu-id="eefde-126">Nel codice seguente sono definite e usate due costanti di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="eefde-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="eefde-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eefde-127">See also</span></span>

- [<span data-ttu-id="eefde-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eefde-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="eefde-129">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="eefde-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="eefde-130">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="eefde-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="eefde-131">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="eefde-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

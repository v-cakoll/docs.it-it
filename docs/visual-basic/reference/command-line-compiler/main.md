---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: fd6240faf702ccb5e543bfd6a7779284f38d8850
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337240"
---
# <a name="-main"></a><span data-ttu-id="7f7ee-102">-main</span><span class="sxs-lookup"><span data-stu-id="7f7ee-102">-main</span></span>
<span data-ttu-id="7f7ee-103">Specifica la classe o il modulo che contiene la procedura `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f7ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f7ee-104">Syntax</span></span>  
  
```  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="7f7ee-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7f7ee-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="7f7ee-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-106">Required.</span></span> <span data-ttu-id="7f7ee-107">Il nome della classe o modulo che contiene il `Sub Main` procedure da chiamare all'avvio del programma.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="7f7ee-108">Ciò potrebbe essere nel formato **-/Main: module** oppure **-main:namespace.module**.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f7ee-109">Note</span><span class="sxs-lookup"><span data-stu-id="7f7ee-109">Remarks</span></span>  
 <span data-ttu-id="7f7ee-110">Usare questa opzione quando si crea un file eseguibile o un programma eseguibile Windows.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="7f7ee-111">Se il **-principale** opzione viene omessa, il compilatore cerca condiviso valido `Sub Main` in tutte le classi pubbliche e moduli.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="7f7ee-112">Visualizzare [routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) per una descrizione delle varie forme del `Main` procedure.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="7f7ee-113">Quando `location` è una classe che eredita da <xref:System.Windows.Forms.Form>, il compilatore fornisce un valore predefinito `Main` routine che avvia l'applicazione se la classe non ha alcun `Main` procedure.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="7f7ee-114">Ciò consente di compilare il codice nella riga di comando che è stata creata nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="7f7ee-115">Per impostare - principale nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7f7ee-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="7f7ee-116">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7f7ee-117">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="7f7ee-118">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="7f7ee-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="7f7ee-119">Assicurarsi che il **Abilita framework applicazione** casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="7f7ee-120">Modificare il valore di **oggetto di avvio** casella.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f7ee-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f7ee-121">Example</span></span>  
 <span data-ttu-id="7f7ee-122">Il codice seguente Compila `T2.vb` e `T3.vb`, specificando che il `Sub Main` sarà disponibili nella procedura di `Test2` classe.</span><span class="sxs-lookup"><span data-stu-id="7f7ee-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f7ee-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f7ee-123">See also</span></span>

- [<span data-ttu-id="7f7ee-124">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f7ee-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7f7ee-125">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f7ee-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="7f7ee-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="7f7ee-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="7f7ee-127">Routine Main in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f7ee-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)

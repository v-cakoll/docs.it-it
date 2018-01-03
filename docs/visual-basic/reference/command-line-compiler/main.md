---
title: /main
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5bb11bc62e951339113f4b48e98e05362490ca1
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="main"></a><span data-ttu-id="b8446-102">/main</span><span class="sxs-lookup"><span data-stu-id="b8446-102">/main</span></span>
<span data-ttu-id="b8446-103">Specifica la classe o il modulo che contiene la procedura `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="b8446-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8446-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8446-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="b8446-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b8446-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="b8446-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8446-106">Required.</span></span> <span data-ttu-id="b8446-107">Nome completo per la classe o modulo che contiene il `Sub Main` procedure da chiamare all'avvio del programma.</span><span class="sxs-lookup"><span data-stu-id="b8446-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="b8446-108">Può essere nel formato **/main:module** o **/Main**.</span><span class="sxs-lookup"><span data-stu-id="b8446-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8446-109">Note</span><span class="sxs-lookup"><span data-stu-id="b8446-109">Remarks</span></span>  
 <span data-ttu-id="b8446-110">Utilizzare questa opzione quando si crea un file eseguibile o un programma eseguibile.</span><span class="sxs-lookup"><span data-stu-id="b8446-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="b8446-111">Se il **/Main** opzione viene omessa, il compilatore cerca una routine condivisa valida `Sub Main` in tutti i moduli e le classi pubbliche.</span><span class="sxs-lookup"><span data-stu-id="b8446-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="b8446-112">Vedere [routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) per una descrizione delle varie forme del `Main` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="b8446-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="b8446-113">Quando `location` è una classe che eredita da <xref:System.Windows.Forms.Form>, il compilatore fornisce un valore predefinito `Main` routine che avvia l'applicazione se la classe non ha alcun `Main` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="b8446-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="b8446-114">Ciò consente di compilare il codice nella riga di comando che è stata creata nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b8446-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="b8446-115">Per impostare /main in Visual Studio ambiente di sviluppo integrato.</span><span class="sxs-lookup"><span data-stu-id="b8446-115">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="b8446-116">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="b8446-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b8446-117">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="b8446-117">On the **Project** menu, click **Properties**.</span></span>  
  
       
  
2.  <span data-ttu-id="b8446-118">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="b8446-118">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="b8446-119">Verificare che il **Attiva framework applicazione** casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="b8446-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="b8446-120">Modificare il valore di **oggetto di avvio** casella.</span><span class="sxs-lookup"><span data-stu-id="b8446-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8446-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8446-121">Example</span></span>  
 <span data-ttu-id="b8446-122">Il codice seguente Compila `T2.vb` e `T3.vb`, specificando che il `Sub Main` sarà disponibili nella procedura di `Test2` classe.</span><span class="sxs-lookup"><span data-stu-id="b8446-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8446-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8446-123">See Also</span></span>  
 [<span data-ttu-id="b8446-124">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8446-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b8446-125">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8446-125">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="b8446-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="b8446-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="b8446-127">Routine Main in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8446-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)

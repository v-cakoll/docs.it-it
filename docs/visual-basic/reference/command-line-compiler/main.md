---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005497"
---
# <a name="-main"></a><span data-ttu-id="4ef47-102">-main</span><span class="sxs-lookup"><span data-stu-id="4ef47-102">-main</span></span>
<span data-ttu-id="4ef47-103">Specifica la classe o il modulo che contiene la procedura `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="4ef47-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ef47-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ef47-104">Syntax</span></span>  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="4ef47-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4ef47-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="4ef47-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4ef47-106">Required.</span></span> <span data-ttu-id="4ef47-107">Nome della classe o del modulo che contiene la procedura `Sub Main` da chiamare all'avvio del programma.</span><span class="sxs-lookup"><span data-stu-id="4ef47-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="4ef47-108">Il formato può essere **Main: module** o **-Main: Namespace. Module**.</span><span class="sxs-lookup"><span data-stu-id="4ef47-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ef47-109">Note</span><span class="sxs-lookup"><span data-stu-id="4ef47-109">Remarks</span></span>  
 <span data-ttu-id="4ef47-110">Usare questa opzione quando si crea un file eseguibile o un programma eseguibile di Windows.</span><span class="sxs-lookup"><span data-stu-id="4ef47-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="4ef47-111">Se l'opzione **-Main** viene omessa, il compilatore cerca un @no__t condiviso valido-1 in tutti i moduli e le classi pubbliche.</span><span class="sxs-lookup"><span data-stu-id="4ef47-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="4ef47-112">Per una descrizione delle diverse forme della procedura `Main`, vedere la [procedura principale in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) .</span><span class="sxs-lookup"><span data-stu-id="4ef47-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="4ef47-113">Quando `location` è una classe che eredita da <xref:System.Windows.Forms.Form>, il compilatore fornisce una routine `Main` predefinita che avvia l'applicazione se la classe non dispone di una procedura `Main`.</span><span class="sxs-lookup"><span data-stu-id="4ef47-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="4ef47-114">In questo modo è possibile compilare il codice dalla riga di comando creata nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4ef47-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="4ef47-115">Per impostare-Main in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="4ef47-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="4ef47-116">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="4ef47-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4ef47-117">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="4ef47-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="4ef47-118">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="4ef47-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="4ef47-119">Verificare che la casella di controllo **Abilita framework applicazione** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="4ef47-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="4ef47-120">Modificare il valore nella casella **oggetto di avvio** .</span><span class="sxs-lookup"><span data-stu-id="4ef47-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ef47-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ef47-121">Example</span></span>  
 <span data-ttu-id="4ef47-122">Il codice seguente compila `T2.vb` e `T3.vb`, specificando che la procedura `Sub Main` sarà disponibile nella classe `Test2`.</span><span class="sxs-lookup"><span data-stu-id="4ef47-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ef47-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ef47-123">See also</span></span>

- [<span data-ttu-id="4ef47-124">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ef47-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4ef47-125">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ef47-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="4ef47-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="4ef47-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="4ef47-127">Procedura principale in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ef47-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)

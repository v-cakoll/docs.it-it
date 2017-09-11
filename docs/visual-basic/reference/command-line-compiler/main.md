---
title: /Main | Documenti di Microsoft
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
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
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
ms.openlocfilehash: 61aa78e131ba8903035f630a540f49848f1acd3f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="main"></a><span data-ttu-id="0cc4b-102">/main</span><span class="sxs-lookup"><span data-stu-id="0cc4b-102">/main</span></span>
<span data-ttu-id="0cc4b-103">Specifica la classe o un modulo che contiene il `Sub Main` procedura.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cc4b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cc4b-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="0cc4b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0cc4b-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="0cc4b-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-106">Required.</span></span> <span data-ttu-id="0cc4b-107">Nome completo della classe o del modulo che contiene il `Sub Main` routine da chiamare all'avvio del programma.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="0cc4b-108">Può essere nel formato **/main:module** o **/Main**.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cc4b-109">Note</span><span class="sxs-lookup"><span data-stu-id="0cc4b-109">Remarks</span></span>  
 <span data-ttu-id="0cc4b-110">Utilizzare questa opzione quando si crea un file eseguibile o un programma eseguibile di Windows.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="0cc4b-111">Se il **/principale** opzione viene omessa, il compilatore cerca condiviso valido `Sub Main` in tutte le classi pubbliche e moduli.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="0cc4b-112">Vedere [routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) per una descrizione delle varie forme di `Main` procedura.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="0cc4b-113">Quando `location` è una classe che eredita da <xref:System.Windows.Forms.Form>, il compilatore fornisce un valore predefinito `Main` routine che avvia l'applicazione se la classe non ha `Main` procedura.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="0cc4b-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="0cc4b-114">Ciò consente di compilare il codice dalla riga di comando che è stata creata nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 <span data-ttu-id="0cc4b-115">[!code-vb[VbVbalrCompiler&#16;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0cc4b-115">[!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span></span>  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="0cc4b-116">Per impostare /main in Visual Studio ambiente di sviluppo integrato</span><span class="sxs-lookup"><span data-stu-id="0cc4b-116">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="0cc4b-117">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0cc4b-118">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-118">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="0cc4b-119">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="0cc4b-119">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="0cc4b-120">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="0cc4b-120">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="0cc4b-121">Assicurarsi che il **Attiva framework applicazione** casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-121">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="0cc4b-122">Modificare il valore di **oggetto di avvio** casella.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-122">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cc4b-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="0cc4b-123">Example</span></span>  
 <span data-ttu-id="0cc4b-124">Il codice seguente Compila `T2.vb` e `T3.vb`, specificando che il `Sub Main` routine è reperibile nella `Test2` classe.</span><span class="sxs-lookup"><span data-stu-id="0cc4b-124">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="0cc4b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cc4b-125">See Also</span></span>  
 <span data-ttu-id="0cc4b-126">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="0cc4b-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="0cc4b-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="0cc4b-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="0cc4b-128"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="0cc4b-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="0cc4b-129"> [NIB: versione di Visual Basic di Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span><span class="sxs-lookup"><span data-stu-id="0cc4b-129"> [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span></span>  
<span data-ttu-id="0cc4b-130"> [Routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span><span class="sxs-lookup"><span data-stu-id="0cc4b-130"> [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span></span>

---
title: Parole chiave come nomi di elementi nel codice (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f410a0eaac0dcc034d406a89ed1d01a8f228a583
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="8c4c2-102">Parole chiave come nomi di elementi nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c4c2-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="8c4c2-103">Qualsiasi elemento del programma, ad esempio una variabile, una classe o membro, può avere lo stesso nome di una parola chiave riservata.</span><span class="sxs-lookup"><span data-stu-id="8c4c2-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="8c4c2-104">Ad esempio, è possibile creare una variabile denominata `Loop`.</span><span class="sxs-lookup"><span data-stu-id="8c4c2-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="8c4c2-105">Tuttavia, per fare riferimento alla versione di esso, che ha lo stesso nome con restrizioni `Loop` (parola chiave), è necessario farlo precedere da una stringa di qualificazione completo o racchiuderlo tra parentesi quadre (`[ ]`), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8c4c2-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 <span data-ttu-id="8c4c2-106">Se questa non uno di questi, Visual Basic si presuppone l'uso dell'intrinseco `Loop` (parola chiave) e genera un errore, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8c4c2-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="8c4c2-107">È possibile utilizzare le parentesi quadre quando si fa riferimento al form e controlli e quando si dichiara una variabile o la definizione di una routine con lo stesso nome di una parola chiave riservata.</span><span class="sxs-lookup"><span data-stu-id="8c4c2-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="8c4c2-108">Può essere facile dimenticare di qualificare i nomi o includere le parentesi quadre e pertanto introdurre errori nel codice e rendere più difficile la lettura.</span><span class="sxs-lookup"><span data-stu-id="8c4c2-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="8c4c2-109">Per questo motivo, è consigliabile non utilizzare parole chiave riservate come nomi di elementi del programma.</span><span class="sxs-lookup"><span data-stu-id="8c4c2-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="8c4c2-110">Tuttavia, se una versione futura di Visual Basic definisce una nuova parola chiave in conflitto con un nome di controllo o un modulo esistente, quindi è possibile utilizzare questa tecnica quando si aggiorna il codice per funzionare con la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="8c4c2-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c4c2-111">Il programma, inoltre, può includere nomi di elementi forniti da altri assembly a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="8c4c2-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="8c4c2-112">Se questi nomi in conflitto con le parole chiave riservate, quindi se le parentesi quadre attorno a esse, Visual Basic e interpretati come elementi definiti.</span><span class="sxs-lookup"><span data-stu-id="8c4c2-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c4c2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c4c2-113">See Also</span></span>  
 [<span data-ttu-id="8c4c2-114">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c4c2-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="8c4c2-115">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="8c4c2-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="8c4c2-116">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8c4c2-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)

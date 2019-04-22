---
title: Parole chiave come nomi di elementi nel codice (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: c247ada67f6554362f287cf252dd49856c4995da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841147"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="45ebf-102">Parole chiave come nomi di elementi nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45ebf-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="45ebf-103">Qualsiasi elemento del programma, ad esempio una variabile, una classe o un membro, ovvero può avere lo stesso nome di una parola chiave riservata.</span><span class="sxs-lookup"><span data-stu-id="45ebf-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="45ebf-104">Ad esempio, è possibile creare una variabile denominata `Loop`.</span><span class="sxs-lookup"><span data-stu-id="45ebf-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="45ebf-105">Tuttavia, per fare riferimento alla propria versione della variabile, ovvero che ha lo stesso nome di area con restrizioni `Loop` parola chiave, è necessario anteporre una stringa di qualificazione completo o racchiuderlo tra parentesi quadre (`[ ]`), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="45ebf-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 <span data-ttu-id="45ebf-106">Se si manifesta uno di questi, il Visual Basic presuppone l'uso di intrinseci `Loop` (parola chiave) e genera un errore, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="45ebf-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="45ebf-107">È possibile usare le parentesi quadre quando si fa riferimento al form e controlli e, quando si dichiara una variabile o la definizione di una routine con lo stesso nome di una parola chiave riservata.</span><span class="sxs-lookup"><span data-stu-id="45ebf-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="45ebf-108">Può essere facile dimenticare di qualificare i nomi o includere le parentesi quadre, quindi introdurre errori nel codice e rendono più difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="45ebf-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="45ebf-109">Per questo motivo, è consigliabile non utilizzare le parole chiave riservate come nomi di elementi del programma.</span><span class="sxs-lookup"><span data-stu-id="45ebf-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="45ebf-110">Tuttavia, se una versione futura di Visual Basic definisce una nuova parola chiave in conflitto con un modulo esistente o nome del controllo, quindi è possibile utilizzare questa tecnica quando l'aggiornamento del codice per lavorare con la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="45ebf-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45ebf-111">Il programma potrebbe includere anche i nomi degli elementi forniti da altri assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="45ebf-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="45ebf-112">Se questi nomi sono in conflitto con le parole chiave riservate, quindi inserire le parentesi quadre attorno a esse fa sì che Visual Basic per interpretarli come elementi definiti.</span><span class="sxs-lookup"><span data-stu-id="45ebf-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ebf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45ebf-113">See also</span></span>

- [<span data-ttu-id="45ebf-114">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45ebf-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="45ebf-115">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="45ebf-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="45ebf-116">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="45ebf-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)

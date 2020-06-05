---
title: Parole chiave come nomi di elementi nel codice
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: a98f0b027700717b414d58e1284ddec655eb25f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403226"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="75d53-102">Parole chiave come nomi di elementi nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75d53-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="75d53-103">Qualsiasi elemento del programma, ad esempio una variabile, una classe o un membro, può avere lo stesso nome di una parola chiave con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="75d53-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="75d53-104">Ad esempio, è possibile creare una variabile denominata `Loop` .</span><span class="sxs-lookup"><span data-stu-id="75d53-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="75d53-105">Tuttavia, per fare riferimento alla relativa versione, che ha lo stesso nome della parola chiave Restricted, `Loop` è necessario precederla con una stringa di qualificazione completa o racchiuderla tra parentesi quadre ( `[ ]` ), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="75d53-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 <span data-ttu-id="75d53-106">Se non si esegue una di queste operazioni, Visual Basic presuppone l'uso della `Loop` parola chiave intrinseca e genera un errore, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="75d53-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="75d53-107">È possibile utilizzare le parentesi quadre per fare riferimento a form e controlli e quando si dichiara una variabile o si definisce una routine con lo stesso nome di una parola chiave con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="75d53-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="75d53-108">Può essere facile dimenticare di qualificare i nomi o includere le parentesi quadre e quindi introdurre errori nel codice e renderlo più difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="75d53-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="75d53-109">Per questo motivo, è consigliabile non usare parole chiave con restrizioni come nomi degli elementi del programma.</span><span class="sxs-lookup"><span data-stu-id="75d53-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="75d53-110">Tuttavia, se una versione futura di Visual Basic definisce una parola chiave nuova che è in conflitto con un modulo o un nome di controllo esistente, è possibile utilizzare questa tecnica quando si aggiorna il codice per utilizzare la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="75d53-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75d53-111">Il programma può inoltre includere i nomi degli elementi forniti da altri assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="75d53-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="75d53-112">Se questi nomi sono in conflitto con parole chiave con restrizioni, l'inserimento di parentesi quadre attorno ad essi causa la Visual Basic di interpretarli come elementi definiti.</span><span class="sxs-lookup"><span data-stu-id="75d53-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d53-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75d53-113">See also</span></span>

- [<span data-ttu-id="75d53-114">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75d53-114">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
- [<span data-ttu-id="75d53-115">Struttura del programma e convenzioni del codice</span><span class="sxs-lookup"><span data-stu-id="75d53-115">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="75d53-116">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="75d53-116">Keywords</span></span>](../../language-reference/keywords/index.md)

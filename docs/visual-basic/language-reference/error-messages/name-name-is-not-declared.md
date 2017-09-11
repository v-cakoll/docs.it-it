---
title: "Nome &quot;&lt;nome&gt;&quot; non è dichiarato | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
dev_langs:
- VB
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
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
ms.openlocfilehash: 1396f24a34a37db064e73d7e259c04050f409ad2
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="f2705-102">Nome '&lt;nome&gt;' non è dichiarato</span><span class="sxs-lookup"><span data-stu-id="f2705-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="f2705-103">Un'istruzione fa riferimento a un elemento di programmazione, ma il compilatore non trova un elemento con il nome esatto.</span><span class="sxs-lookup"><span data-stu-id="f2705-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="f2705-104">**ID errore:** BC30451</span><span class="sxs-lookup"><span data-stu-id="f2705-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2705-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f2705-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="f2705-106">Controllare l'ortografia del nome nell'istruzione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f2705-106">Check the spelling of the name in the referring statement.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f2705-107">tra maiuscole e minuscole, ma qualsiasi altra variazione nell'ortografia verrà considerata come un nome completamente diverso.</span><span class="sxs-lookup"><span data-stu-id="f2705-107"> is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="f2705-108">Si noti che il carattere di sottolineatura (`_`) fa parte del nome e quindi dell'ortografia.</span><span class="sxs-lookup"><span data-stu-id="f2705-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="f2705-109">Verificare di disporre l'operatore di accesso ai membri (`.`) tra un oggetto e il relativo membro.</span><span class="sxs-lookup"><span data-stu-id="f2705-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="f2705-110">Ad esempio, se si dispone di un <xref:System.Windows.Forms.TextBox>controllo denominato `TextBox1`, per accedere ai relativi <xref:System.Windows.Forms.TextBoxBase.Text%2A>proprietà è necessario digitare `TextBox1.Text`.</xref:System.Windows.Forms.TextBoxBase.Text%2A> </xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="f2705-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="f2705-111">Se invece si digita `TextBox1Text`, viene creato un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="f2705-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="f2705-112">Se l'ortografia e la sintassi di accesso ai membri qualsiasi oggetto sia corretta, verificare che l'elemento è stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="f2705-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="f2705-113">Per ulteriori informazioni, vedere [gli elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="f2705-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="f2705-114">Se l'elemento di programmazione è stata dichiarata, controllare che si trova nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="f2705-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="f2705-115">Se l'istruzione di riferimento è all'esterno dell'area di dichiarazione di elemento di programmazione, potrebbe essere necessario qualificare il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="f2705-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="f2705-116">Per ulteriori informazioni, vedere [ambito in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="f2705-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2705-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2705-117">See Also</span></span>  
 <span data-ttu-id="f2705-118">[Riepilogo delle dichiarazioni e costanti](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md) </span><span class="sxs-lookup"><span data-stu-id="f2705-118">[Declarations and Constants Summary](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md) </span></span>  
<span data-ttu-id="f2705-119"> [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="f2705-119"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="f2705-120"> [Nomi elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="f2705-120"> [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="f2705-121"> [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="f2705-121"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>

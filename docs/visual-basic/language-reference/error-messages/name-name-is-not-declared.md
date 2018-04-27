---
title: Nome &#39; &lt;nome&gt; &#39; non è dichiarato
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26245952a2dc5341dedba6c497c47773b882b49b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="5dadc-102">Nome &#39; &lt;nome&gt; &#39; non è dichiarato</span><span class="sxs-lookup"><span data-stu-id="5dadc-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="5dadc-103">Un'istruzione fa riferimento a un elemento di programmazione, ma il compilatore non trova un elemento con quel nome esatto.</span><span class="sxs-lookup"><span data-stu-id="5dadc-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="5dadc-104">**ID errore:** BC30451</span><span class="sxs-lookup"><span data-stu-id="5dadc-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5dadc-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5dadc-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="5dadc-106">Controllare l'ortografia del nome nell'istruzione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5dadc-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="5dadc-107">Visual Basic è tra maiuscole e minuscole, ma qualsiasi altra variazione nell'ortografia verrà considerata come un nome completamente diverso.</span><span class="sxs-lookup"><span data-stu-id="5dadc-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="5dadc-108">Si noti che il carattere di sottolineatura (`_`) fa parte del nome e quindi dell'ortografia.</span><span class="sxs-lookup"><span data-stu-id="5dadc-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="5dadc-109">Verificare di avere l'operatore di accesso ai membri (`.`) tra un oggetto e il relativo membro.</span><span class="sxs-lookup"><span data-stu-id="5dadc-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="5dadc-110">Ad esempio, se è presente un controllo <xref:System.Windows.Forms.TextBox> denominato `TextBox1`, per accedere alla relativa proprietà <xref:System.Windows.Forms.TextBoxBase.Text%2A> occorre digitare `TextBox1.Text`.</span><span class="sxs-lookup"><span data-stu-id="5dadc-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="5dadc-111">Se invece si digita `TextBox1Text`, viene creato un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="5dadc-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="5dadc-112">Se l'ortografia e la sintassi di accesso ai membri qualsiasi oggetto sia corretta, verificare che l'elemento è stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="5dadc-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="5dadc-113">Per ulteriori informazioni, vedere [elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="5dadc-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="5dadc-114">Se è stato dichiarato l'elemento di programmazione, controllare che si trova nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="5dadc-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="5dadc-115">Se l'istruzione che fa riferimento è di fuori dell'area di dichiarazione di elemento di programmazione, è necessario qualificare il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="5dadc-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="5dadc-116">Per ulteriori informazioni, vedere [ambito in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="5dadc-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dadc-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dadc-117">See Also</span></span>  
 [<span data-ttu-id="5dadc-118">Riepilogo delle dichiarazioni e delle costanti</span><span class="sxs-lookup"><span data-stu-id="5dadc-118">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [<span data-ttu-id="5dadc-119">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5dadc-119">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="5dadc-120">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="5dadc-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="5dadc-121">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="5dadc-121">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

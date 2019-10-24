---
title: Il nome <namespacename> nello spazio dei nomi radice <fullnamespacename> non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 821044d3ee359a052fa6a763e9c5a89da5d6f607
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775573"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="e099e-102">Nome \<namespacename > nello spazio dei nomi radice \<fullnamespacename > non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="e099e-102">Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>
<span data-ttu-id="e099e-103">Un assembly è contrassegnato come `<CLSCompliant(True)>`, ma un elemento del nome dello spazio dei nomi radice inizia con un carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="e099e-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="e099e-104">Un elemento di programmazione può contenere uno o più caratteri di sottolineatura, ma deve essere conforme all' [indipendenza del linguaggio e ai componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), non deve iniziare con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="e099e-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="e099e-105">Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="e099e-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="e099e-106">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="e099e-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="e099e-107">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="e099e-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="e099e-108">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="e099e-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="e099e-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="e099e-109">By default, this message is a warning.</span></span> <span data-ttu-id="e099e-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e099e-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e099e-111">**ID errore:** BC40039</span><span class="sxs-lookup"><span data-stu-id="e099e-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e099e-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e099e-112">To correct this error</span></span>  
  
- <span data-ttu-id="e099e-113">Se è necessaria la conformità a CLS, modificare il nome dello spazio dei nomi radice in modo che nessuno degli elementi inizi con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="e099e-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
- <span data-ttu-id="e099e-114">Se è necessario che il nome dello spazio dei nomi rimanga invariato, rimuovere il <xref:System.CLSCompliantAttribute> dall'assembly o contrassegnarlo come `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="e099e-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e099e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e099e-115">See also</span></span>

- [<span data-ttu-id="e099e-116">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="e099e-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="e099e-117">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e099e-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="e099e-118">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="e099e-118">-rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="e099e-119">Pagina Applicazione, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e099e-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="e099e-120">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="e099e-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="e099e-121">Convenzioni di denominazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e099e-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)

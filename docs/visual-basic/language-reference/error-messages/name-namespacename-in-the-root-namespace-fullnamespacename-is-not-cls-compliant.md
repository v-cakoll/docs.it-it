---
title: "Nome &lt;NomeSpazioDeiNomi&gt; nello spazio dei nomi radice &lt;fullnamespacename&gt; non è conforme a CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords: BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3a89f8cfe4038a81002777886de1155bea72ba22
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a><span data-ttu-id="bc83c-102">Nome &lt;NomeSpazioDeiNomi&gt; nello spazio dei nomi radice &lt;fullnamespacename&gt; non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="bc83c-102">Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="bc83c-103">Un assembly è contrassegnato come `<CLSCompliant(True)>`, ma un elemento del nome dello spazio dei nomi radice inizia con un carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="bc83c-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="bc83c-104">Un elemento di programmazione può contenere uno o più caratteri di sottolineatura, ma to deve essere compatibile con il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), non può iniziare con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="bc83c-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="bc83c-105">Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="bc83c-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="bc83c-106">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="bc83c-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="bc83c-107">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="bc83c-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="bc83c-108">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="bc83c-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="bc83c-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="bc83c-109">By default, this message is a warning.</span></span> <span data-ttu-id="bc83c-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="bc83c-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="bc83c-111">**ID errore:** BC40039</span><span class="sxs-lookup"><span data-stu-id="bc83c-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bc83c-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="bc83c-112">To correct this error</span></span>  
  
-   <span data-ttu-id="bc83c-113">Se è necessaria la conformità a CLS, modificare il nome dello spazio dei nomi radice in modo che nessuno dei suoi elementi inizia con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="bc83c-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="bc83c-114">Se è necessario che il nome dello spazio dei nomi deve rimanere invariato, quindi rimuovere il <xref:System.CLSCompliantAttribute> dall'assembly o contrassegnarlo come `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="bc83c-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc83c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc83c-115">See Also</span></span>  
 [<span data-ttu-id="bc83c-116">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="bc83c-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="bc83c-117">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc83c-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="bc83c-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="bc83c-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)  
 [<span data-ttu-id="bc83c-119">Pagina Applicazione, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc83c-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [<span data-ttu-id="bc83c-120">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="bc83c-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="bc83c-121">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc83c-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 

---
title: "Nome &lt;NomeSpazioDeiNomi&gt; nello spazio dei nomi radice &lt;fullnamespacename&gt; non è conforme a CLS | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
dev_langs:
- VB
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: 10
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
ms.openlocfilehash: 0d31657a958581b91cb448b78b8f55f8aadfe7c9
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a><span data-ttu-id="07f3b-102">Nome &lt;NomeSpazioDeiNomi&gt; nello spazio dei nomi radice &lt;fullnamespacename&gt; non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="07f3b-102">Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="07f3b-103">Un assembly è contrassegnato come `<CLSCompliant(True)>`, ma un elemento del nome dello spazio dei nomi principale inizia con un carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="07f3b-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="07f3b-104">Un elemento di programmazione può contenere uno o più caratteri di sottolineatura, ma to deve essere compatibile con il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](https://msdn.microsoft.com/library/12a7a7h3) (CLS), non può iniziare con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="07f3b-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="07f3b-105">Vedere [dichiarati i nomi degli elementi](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="07f3b-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="07f3b-106">Quando si applica il <xref:System.CLSCompliantAttribute>a un elemento di programmazione, impostare l'attributo `isCompliant` parametro al metodo `True` o `False` per indicare la conformità o la non conformità.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="07f3b-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="07f3b-107">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="07f3b-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="07f3b-108">Se non si applica il <xref:System.CLSCompliantAttribute>a un elemento, viene considerato come non conforme.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="07f3b-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="07f3b-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="07f3b-109">By default, this message is a warning.</span></span> <span data-ttu-id="07f3b-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="07f3b-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="07f3b-111">**ID errore:** BC40039</span><span class="sxs-lookup"><span data-stu-id="07f3b-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="07f3b-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="07f3b-112">To correct this error</span></span>  
  
-   <span data-ttu-id="07f3b-113">Se è necessaria la conformità a CLS, modificare il nome dello spazio dei nomi radice in modo che nessuno dei suoi elementi inizi con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="07f3b-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="07f3b-114">Se è necessario che il nome dello spazio dei nomi deve rimanere invariato, quindi rimuovere il <xref:System.CLSCompliantAttribute>dall'assembly o contrassegnarlo come `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="07f3b-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f3b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07f3b-115">See Also</span></span>  
 <span data-ttu-id="07f3b-116">[Istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="07f3b-116">[Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="07f3b-117"> [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="07f3b-117"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="07f3b-118"> [/RootNamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md) </span><span class="sxs-lookup"><span data-stu-id="07f3b-118"> [/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md) </span></span>  
<span data-ttu-id="07f3b-119"> [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)  (Pagina Applicazione, Creazione progetti (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="07f3b-119"> [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="07f3b-120"> [Nomi elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="07f3b-120"> [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="07f3b-121"> [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="07f3b-121"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="07f3b-122"> [\<PAVE su > la scrittura di codice conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="07f3b-122"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>

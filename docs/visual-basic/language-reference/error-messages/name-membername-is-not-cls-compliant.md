---
title: "Nome &lt;membername&gt; non è conforme a CLS | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
dev_langs:
- VB
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: 9
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
ms.openlocfilehash: cbe0a8db6d801a0d083a6828af75342f15f0178d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a><span data-ttu-id="068ef-102">Nome &lt;membername&gt; non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="068ef-102">Name &lt;membername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="068ef-103">Un assembly è contrassegnato come `<CLSCompliant(True)>` ma espone un membro con un nome che inizia con un carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="068ef-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="068ef-104">Un elemento di programmazione può contenere uno o più caratteri di sottolineatura, ma to deve essere compatibile con il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](https://msdn.microsoft.com/library/12a7a7h3) (CLS), non può iniziare con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="068ef-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="068ef-105">Vedere [dichiarati i nomi degli elementi](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="068ef-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="068ef-106">Quando si applica il <xref:System.CLSCompliantAttribute>a un elemento di programmazione, impostare l'attributo `isCompliant` parametro al metodo `True` o `False` per indicare la conformità o la non conformità.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="068ef-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="068ef-107">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="068ef-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="068ef-108">Se non si applica il <xref:System.CLSCompliantAttribute>a un elemento, viene considerato come non conforme.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="068ef-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="068ef-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="068ef-109">By default, this message is a warning.</span></span> <span data-ttu-id="068ef-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="068ef-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="068ef-111">**ID errore:** BC40031</span><span class="sxs-lookup"><span data-stu-id="068ef-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="068ef-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="068ef-112">To correct this error</span></span>  
  
-   <span data-ttu-id="068ef-113">Se si dispone di controllo del codice sorgente, modificare il nome del membro in modo che non inizia con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="068ef-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="068ef-114">Se è necessario che il nome del membro rimangono invariati, rimuovere il <xref:System.CLSCompliantAttribute>dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="068ef-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="068ef-115">È comunque possibile contrassegnare l'assembly come `<CLSCompliant(True)>`.</span><span class="sxs-lookup"><span data-stu-id="068ef-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068ef-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="068ef-116">See Also</span></span>  
 <span data-ttu-id="068ef-117">[Nomi elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="068ef-117">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="068ef-118"> [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="068ef-118"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="068ef-119"> [\<PAVE su > la scrittura di codice conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="068ef-119"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>

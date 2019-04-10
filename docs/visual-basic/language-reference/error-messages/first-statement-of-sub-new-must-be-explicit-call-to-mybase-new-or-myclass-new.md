---
title: "La prima istruzione di questo 'Sub New' deve essere una chiamata esplicita a 'MyBase.New' o a 'MyClass.New' perché '<constructorname>' nella classe base '<baseclassname>' di '<derivedclassname>' è contrassegnato come obsoleto: '<errormessage>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 89b6c241bb637f2efc6014c4640b3b463c4facfa
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313477"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a><span data-ttu-id="024eb-102">La prima istruzione di questo 'Sub New' deve essere una chiamata esplicita a 'MyBase. New' o 'MyClass. New' perché il '\<nomecostruttore >' nella classe base\<nomeclassebase >' di '\<nomeclassederivata >' è contrassegnato come obsoleto: '\< messaggio di errore >'</span><span class="sxs-lookup"><span data-stu-id="024eb-102">First statement of this 'Sub New' must be an explicit call to 'MyBase.New' or 'MyClass.New' because the '\<constructorname>' in the base class '\<baseclassname>' of '\<derivedclassname>' is marked obsolete: '\<errormessage>'</span></span>
<span data-ttu-id="024eb-103">Un costruttore di classe non chiama esplicitamente un costruttore della classe base e il costruttore della classe base implicito è contrassegnato con l'attributo <xref:System.ObsoleteAttribute> e la direttiva di considerarlo come un errore.</span><span class="sxs-lookup"><span data-stu-id="024eb-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="024eb-104">Quando un costruttore della classe derivata non chiama un costruttore di classe di base, Visual Basic tenta di generare una chiamata implicita a un costruttore di classe di base senza parametri.</span><span class="sxs-lookup"><span data-stu-id="024eb-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="024eb-105">Se non è presente alcun costruttore accessibile nella classe di base che può essere chiamata senza argomenti, Visual Basic non è possibile generare una chiamata implicita.</span><span class="sxs-lookup"><span data-stu-id="024eb-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="024eb-106">In questo caso, il costruttore obbligatorio è contrassegnato con il <xref:System.ObsoleteAttribute> attributo, in modo che Visual Basic non può chiamarlo.</span><span class="sxs-lookup"><span data-stu-id="024eb-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="024eb-107">È possibile contrassegnare qualsiasi elemento di programmazione come non più in uso applicando <xref:System.ObsoleteAttribute> a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="024eb-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="024eb-108">In questo caso, è possibile impostare la proprietà <xref:System.ObsoleteAttribute.IsError%2A> dell'attributo su `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="024eb-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="024eb-109">Se si imposta la proprietà su `True`, il compilatore considera il tentativo di usare l'elemento come un errore.</span><span class="sxs-lookup"><span data-stu-id="024eb-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="024eb-110">Se si imposta la proprietà su `False`, o si lascia l'impostazione predefinita `False`, il compilatore genera un avviso se si prova a usare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="024eb-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="024eb-111">**ID errore:** BC30920</span><span class="sxs-lookup"><span data-stu-id="024eb-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="024eb-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="024eb-112">To correct this error</span></span>  
  
1. <span data-ttu-id="024eb-113">Esaminare il messaggio di errore tra virgolette e intraprendere l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="024eb-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2. <span data-ttu-id="024eb-114">Includere una chiamata a `MyBase.New()` o `MyClass.New()` come prima istruzione di `Sub New` nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="024eb-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="024eb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="024eb-115">See also</span></span>

- [<span data-ttu-id="024eb-116">Cenni preliminari sugli attributi</span><span class="sxs-lookup"><span data-stu-id="024eb-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

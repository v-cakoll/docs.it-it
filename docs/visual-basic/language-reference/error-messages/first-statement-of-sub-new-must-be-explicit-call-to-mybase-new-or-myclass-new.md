---
title: "La prima istruzione di questo 'Sub New' deve essere una chiamata esplicita a 'MyBase.New' o a 'MyClass.New' perché '<constructorname>' nella classe base '<baseclassname>' di '<derivedclassname>' è contrassegnato come obsoleto: '<errormessage>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 33dd15e3f5f5538963597f2b00f4214895e1f47a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403005"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a><span data-ttu-id="e30fd-102">La prima istruzione di questo 'Sub New' deve essere una chiamata esplicita a 'MyBase.New' o a 'MyClass.New' perché '\<constructorname>' nella classe base '\<baseclassname>' di '\<derivedclassname>' è contrassegnato come obsoleto: '\<errormessage>'</span><span class="sxs-lookup"><span data-stu-id="e30fd-102">First statement of this 'Sub New' must be an explicit call to 'MyBase.New' or 'MyClass.New' because the '\<constructorname>' in the base class '\<baseclassname>' of '\<derivedclassname>' is marked obsolete: '\<errormessage>'</span></span>
<span data-ttu-id="e30fd-103">Un costruttore di classe non chiama esplicitamente un costruttore della classe base e il costruttore della classe base implicito è contrassegnato con l'attributo <xref:System.ObsoleteAttribute> e la direttiva di considerarlo come un errore.</span><span class="sxs-lookup"><span data-stu-id="e30fd-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="e30fd-104">Quando un costruttore della classe derivata non chiama un costruttore della classe base, Visual Basic tenta di generare una chiamata implicita a un costruttore della classe base senza parametri.</span><span class="sxs-lookup"><span data-stu-id="e30fd-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="e30fd-105">Se nella classe base non è presente alcun costruttore accessibile che può essere chiamato senza argomenti, Visual Basic non può generare una chiamata implicita.</span><span class="sxs-lookup"><span data-stu-id="e30fd-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="e30fd-106">In questo caso, il costruttore obbligatorio è contrassegnato con l' <xref:System.ObsoleteAttribute> attributo, quindi Visual Basic non può chiamarlo.</span><span class="sxs-lookup"><span data-stu-id="e30fd-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="e30fd-107">È possibile contrassegnare qualsiasi elemento di programmazione come non più in uso applicando <xref:System.ObsoleteAttribute> a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="e30fd-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="e30fd-108">In questo caso, è possibile impostare la proprietà <xref:System.ObsoleteAttribute.IsError%2A> dell'attributo su `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="e30fd-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="e30fd-109">Se si imposta la proprietà su `True`, il compilatore considera il tentativo di usare l'elemento come un errore.</span><span class="sxs-lookup"><span data-stu-id="e30fd-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="e30fd-110">Se si imposta la proprietà su `False`, o si lascia l'impostazione predefinita `False`, il compilatore genera un avviso se si prova a usare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="e30fd-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="e30fd-111">**ID errore:** BC30920</span><span class="sxs-lookup"><span data-stu-id="e30fd-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e30fd-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e30fd-112">To correct this error</span></span>  
  
1. <span data-ttu-id="e30fd-113">Esaminare il messaggio di errore tra virgolette e intraprendere l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="e30fd-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2. <span data-ttu-id="e30fd-114">Includere una chiamata a `MyBase.New()` o `MyClass.New()` come prima istruzione di `Sub New` nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e30fd-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e30fd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e30fd-115">See also</span></span>

- [<span data-ttu-id="e30fd-116">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="e30fd-116">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)

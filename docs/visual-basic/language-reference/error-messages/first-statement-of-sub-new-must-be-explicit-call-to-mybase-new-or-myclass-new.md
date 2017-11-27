---
title: "La prima istruzione di questo &#39; Sub nuovo &#39; deve essere una chiamata esplicita a &#39; MyBase. New &#39; o &#39; MyClass. New &#39; Poiché il &#39; &lt;nomecostruttore&gt;&#39; la classe di base &#39;&lt; nomeclassebase&gt;&#39; &#39;&lt; nomeclassederivata&gt;&#39; è contrassegnato come obsoleto: &#39;&lt; messaggio di errore&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords: BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8882acd947251d85804fbefd54267ce078e31b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="d2565-102">La prima istruzione di questo &#39; Sub nuovo &#39; deve essere una chiamata esplicita a &#39; MyBase. New &#39; o &#39; MyClass. New &#39; Poiché il &#39; &lt;nomecostruttore&gt;&#39; la classe di base &#39;&lt; nomeclassebase&gt;&#39; &#39;&lt; nomeclassederivata&gt;&#39; è contrassegnato come obsoleto: &#39;&lt; messaggio di errore&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="d2565-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="d2565-103">Un costruttore di classe non chiama esplicitamente un costruttore della classe base e il costruttore della classe base implicito è contrassegnato con l'attributo <xref:System.ObsoleteAttribute> e la direttiva di considerarlo come un errore.</span><span class="sxs-lookup"><span data-stu-id="d2565-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="d2565-104">Quando un costruttore della classe derivata non chiama un costruttore della classe base, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] prova a generare una chiamata implicita a un costruttore della classe base senza parametri.</span><span class="sxs-lookup"><span data-stu-id="d2565-104">When a derived class constructor does not call a base class constructor, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="d2565-105">Se non è presente alcun costruttore accessibile nella classe base che può essere chiamato senza argomenti, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non può generare una chiamata implicita.</span><span class="sxs-lookup"><span data-stu-id="d2565-105">If there is no accessible constructor in the base class that can be called without arguments, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot generate an implicit call.</span></span> <span data-ttu-id="d2565-106">In questo caso, il costruttore obbligatorio è contrassegnato con l'attributo <xref:System.ObsoleteAttribute> , per cui [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non può chiamarlo.</span><span class="sxs-lookup"><span data-stu-id="d2565-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot call it.</span></span>  
  
 <span data-ttu-id="d2565-107">È possibile contrassegnare qualsiasi elemento di programmazione come non più in uso applicando <xref:System.ObsoleteAttribute> a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="d2565-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="d2565-108">In questo caso, è possibile impostare la proprietà <xref:System.ObsoleteAttribute.IsError%2A> dell'attributo su `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="d2565-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="d2565-109">Se si imposta la proprietà su `True`, il compilatore considera il tentativo di usare l'elemento come un errore.</span><span class="sxs-lookup"><span data-stu-id="d2565-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="d2565-110">Se si imposta la proprietà su `False`, o si lascia l'impostazione predefinita `False`, il compilatore genera un avviso se si prova a usare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="d2565-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="d2565-111">**ID errore:** BC30920</span><span class="sxs-lookup"><span data-stu-id="d2565-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2565-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d2565-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="d2565-113">Esaminare il messaggio di errore tra virgolette e intraprendere l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="d2565-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="d2565-114">Includere una chiamata a `MyBase.New()` o `MyClass.New()` come prima istruzione di `Sub New` nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d2565-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2565-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2565-115">See Also</span></span>  
 [<span data-ttu-id="d2565-116">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="d2565-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 

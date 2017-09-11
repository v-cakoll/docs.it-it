---
title: "La prima istruzione di questo &quot;Sub New&quot; deve essere una chiamata esplicita a &quot;MyClass. New&quot; o &quot;MyBase. New&quot; perché il &quot;&lt;constructorname&gt;&quot;nella classe di base&quot;&lt;baseclassname&gt;&quot;di&quot;&lt;derivedclassname&gt;&quot; è contrassegnato come obsoleto: &quot;&lt;errormessage&gt;&quot; | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
dev_langs:
- VB
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
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
ms.openlocfilehash: d46192bc9a9f2807f56cbdd7bdd4fd21f6c9a7b0
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="67191-102">La prima istruzione di questo 'Sub New' deve essere una chiamata esplicita a 'MyClass. New' o 'MyBase. New' perché il '&lt;constructorname&gt;'nella classe di base'&lt;baseclassname&gt;'di'&lt;derivedclassname&gt;' è contrassegnato come obsoleto: '&lt;errormessage&gt;'</span><span class="sxs-lookup"><span data-stu-id="67191-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="67191-103">Un costruttore di classe non chiama in modo esplicito un costruttore di classe di base e il costruttore della classe base implicito è contrassegnato con il <xref:System.ObsoleteAttribute>attributo e la direttiva di considerarla come un errore.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="67191-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="67191-104">Quando un costruttore di classe derivata non chiama un costruttore di classe base, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tenta di generare una chiamata implicita a un costruttore senza parametri della classe base.</span><span class="sxs-lookup"><span data-stu-id="67191-104">When a derived class constructor does not call a base class constructor, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="67191-105">Se non vi è alcun costruttore accessibile nella classe di base che può essere chiamata senza argomenti, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] non può generare una chiamata implicita.</span><span class="sxs-lookup"><span data-stu-id="67191-105">If there is no accessible constructor in the base class that can be called without arguments, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot generate an implicit call.</span></span> <span data-ttu-id="67191-106">In questo caso, il costruttore richiesto è contrassegnato con il <xref:System.ObsoleteAttribute>attributo, operazione [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] non può chiamare tale</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="67191-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot call it.</span></span>  
  
 <span data-ttu-id="67191-107">È possibile contrassegnare gli elementi di programmazione come non più in uso, applicando <xref:System.ObsoleteAttribute>a tale</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="67191-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="67191-108">In questo caso, è possibile impostare l'attributo <xref:System.ObsoleteAttribute.IsError%2A>a una proprietà `True` o `False`.</xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="67191-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="67191-109">Se si imposta la proprietà su `True`, il compilatore considera il tentativo di usare l'elemento come un errore.</span><span class="sxs-lookup"><span data-stu-id="67191-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="67191-110">Se si imposta la proprietà su `False`, o si lascia l'impostazione predefinita `False`, il compilatore genera un avviso se si prova a usare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="67191-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="67191-111">**ID errore:** BC30920</span><span class="sxs-lookup"><span data-stu-id="67191-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="67191-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="67191-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="67191-113">Esaminare il messaggio di errore tra virgolette e intraprendere l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="67191-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="67191-114">Includere una chiamata a `MyBase.New()` o `MyClass.New()` come prima istruzione di `Sub New` nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="67191-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67191-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67191-115">See Also</span></span>  
 [<span data-ttu-id="67191-116">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="67191-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 

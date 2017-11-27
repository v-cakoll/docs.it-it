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
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>La prima istruzione di questo &#39; Sub nuovo &#39; deve essere una chiamata esplicita a &#39; MyBase. New &#39; o &#39; MyClass. New &#39; Poiché il &#39; &lt;nomecostruttore&gt;&#39; la classe di base &#39;&lt; nomeclassebase&gt;&#39; &#39;&lt; nomeclassederivata&gt;&#39; è contrassegnato come obsoleto: &#39;&lt; messaggio di errore&gt;&#39;
Un costruttore di classe non chiama esplicitamente un costruttore della classe base e il costruttore della classe base implicito è contrassegnato con l'attributo <xref:System.ObsoleteAttribute> e la direttiva di considerarlo come un errore.  
  
 Quando un costruttore della classe derivata non chiama un costruttore della classe base, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] prova a generare una chiamata implicita a un costruttore della classe base senza parametri. Se non è presente alcun costruttore accessibile nella classe base che può essere chiamato senza argomenti, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non può generare una chiamata implicita. In questo caso, il costruttore obbligatorio è contrassegnato con l'attributo <xref:System.ObsoleteAttribute> , per cui [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non può chiamarlo.  
  
 È possibile contrassegnare qualsiasi elemento di programmazione come non più in uso applicando <xref:System.ObsoleteAttribute> a tale elemento. In questo caso, è possibile impostare la proprietà <xref:System.ObsoleteAttribute.IsError%2A> dell'attributo su `True` o `False`. Se si imposta la proprietà su `True`, il compilatore considera il tentativo di usare l'elemento come un errore. Se si imposta la proprietà su `False`, o si lascia l'impostazione predefinita `False`, il compilatore genera un avviso se si prova a usare l'elemento.  
  
 **ID errore:** BC30920  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Esaminare il messaggio di errore tra virgolette e intraprendere l'azione appropriata.  
  
2.  Includere una chiamata a `MyBase.New()` o `MyClass.New()` come prima istruzione di `Sub New` nella classe derivata.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 

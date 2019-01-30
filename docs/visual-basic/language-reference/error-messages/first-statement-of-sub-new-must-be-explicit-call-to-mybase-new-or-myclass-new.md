---
title: "La prima istruzione di questo 'Sub New' deve essere una chiamata esplicita a 'MyBase.New' o a 'MyClass.New' perché '<constructorname>' nella classe base '<baseclassname>' di '<derivedclassname>' è contrassegnato come obsoleto: '<errormessage>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 31f92d1e52e50b2a87fd6a6af6e3c87292f4437f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268795"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a>La prima istruzione di questo 'Sub New' deve essere una chiamata esplicita a 'MyBase. New' o 'MyClass. New' perché il '\<nomecostruttore >' nella classe base\<nomeclassebase >' di '\<nomeclassederivata >' è contrassegnato come obsoleto: '\< messaggio di errore >'
Un costruttore di classe non chiama esplicitamente un costruttore della classe base e il costruttore della classe base implicito è contrassegnato con l'attributo <xref:System.ObsoleteAttribute> e la direttiva di considerarlo come un errore.  
  
 Quando un costruttore della classe derivata non chiama un costruttore di classe di base, Visual Basic tenta di generare una chiamata implicita a un costruttore di classe di base senza parametri. Se non è presente alcun costruttore accessibile nella classe di base che può essere chiamata senza argomenti, Visual Basic non è possibile generare una chiamata implicita. In questo caso, il costruttore obbligatorio è contrassegnato con il <xref:System.ObsoleteAttribute> attributo, in modo che Visual Basic non può chiamarlo.  
  
 È possibile contrassegnare qualsiasi elemento di programmazione come non più in uso applicando <xref:System.ObsoleteAttribute> a tale elemento. In questo caso, è possibile impostare la proprietà <xref:System.ObsoleteAttribute.IsError%2A> dell'attributo su `True` o `False`. Se si imposta la proprietà su `True`, il compilatore considera il tentativo di usare l'elemento come un errore. Se si imposta la proprietà su `False`, o si lascia l'impostazione predefinita `False`, il compilatore genera un avviso se si prova a usare l'elemento.  
  
 **ID errore:** BC30920  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Esaminare il messaggio di errore tra virgolette e intraprendere l'azione appropriata.  
  
2.  Includere una chiamata a `MyBase.New()` o `MyClass.New()` come prima istruzione di `Sub New` nella classe derivata.  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)


---
title: Il nome <namespacename> nello spazio dei nomi radice <fullnamespacename> non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: b03a50365122c17fa311a284bd6995d1af2631c3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401537"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a>Il nome \<namespacename> nello spazio dei nomi radice \<fullnamespacename> non è conforme a CLS
Un assembly è contrassegnato come `<CLSCompliant(True)>` , ma un elemento del nome dello spazio dei nomi radice inizia con un carattere di sottolineatura ( `_` ).  
  
 Un elemento di programmazione può contenere uno o più caratteri di sottolineatura, ma deve essere conforme all' [indipendenza del linguaggio e ai componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), non deve iniziare con un carattere di sottolineatura. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40039  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se è necessaria la conformità a CLS, modificare il nome dello spazio dei nomi radice in modo che nessuno degli elementi inizi con un carattere di sottolineatura.  
  
- Se è necessario che il nome dello spazio dei nomi rimanga invariato, rimuovere <xref:System.CLSCompliantAttribute> dall'assembly o contrassegnarlo come `<CLSCompliant(False)>` .  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Namespace](../statements/namespace-statement.md)
- [Spazi dei nomi in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [-rootnamespace](../../reference/command-line-compiler/rootnamespace.md)
- [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Convenzioni di denominazione di Visual Basic](../../programming-guide/program-structure/naming-conventions.md)

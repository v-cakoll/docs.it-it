---
title: Shadows (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: 4ca4ec48ee63b71447056a2c5cb68e8948f27ad0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604653"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)
Specifica che un elemento di programmazione dichiarato ridichiara e nasconde un elemento con nome identico, o un set di elementi in overload di una classe di base.  
  
## <a name="remarks"></a>Note  
 Lo scopo principale di shadowing (anche noto come *occultamento nome*) consiste nel conservare la definizione dei membri della classe. La classe di base può essere sottoposto a una modifica che crea un elemento con lo stesso nome già definito. In questo caso, il `Shadows` modificatore impone che fa riferimento tramite la classe deve essere risolto per il membro è definito, anziché il nuovo elemento della classe base.  
  
 Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali. Per ulteriori informazioni, vedere [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** È possibile utilizzare `Shadows` solo a livello di classe. Ciò significa che il contesto della dichiarazione per un `Shadows` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o stored procedure.  
  
     È possibile dichiarare un solo elemento di shadowing in una singola istruzione di dichiarazione.  
  
-   **Modificatori combinati.** Non è possibile specificare `Shadows` con `Overloads`, `Overrides`, o `Static` nella stessa dichiarazione.  
  
-   **Tipi di elemento.** È possibile nascondere qualsiasi tipo di elemento dichiarato con qualsiasi altro tipo. Se si nasconde una proprietà o routine con un'altra proprietà o routine, i parametri e il tipo restituito non è affinché corrispondano a quelle nella proprietà di classe di base o della routine.  
  
-   **L'accesso.** L'elemento nascosto nella classe base è generalmente disponibile all'interno della classe derivata che lo nasconde. Tuttavia, si applicano le considerazioni seguenti.  
  
    -   Se l'elemento di shadowing non è accessibile dal codice che fa riferimento a esso, il riferimento viene risolto l'elemento nascosto. Ad esempio, se un `Private` elemento nasconde un elemento della classe base, il codice che non dispone dell'autorizzazione per accedere il `Private` elemento accede invece all'elemento della classe base.  
  
    -   Se si nasconde un elemento, è comunque possibile accedere all'elemento nascosto tramite un oggetto dichiarato con il tipo della classe di base. È anche possibile accedervi tramite `MyBase`.  
  
 Il modificatore `Shadows` può essere usato nei contesti seguenti:  
  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Static](../../../visual-basic/language-reference/modifiers/static.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [Overload](../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)

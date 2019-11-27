---
title: Shadows
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
ms.openlocfilehash: e9a423fa69ad1dcd8c1d4a5b7085e5b5da548f93
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351272"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

Specifica che un elemento di programmazione dichiarato ridichiara e nasconde un elemento con nome identico o un set di elementi in overload in una classe base.

## <a name="remarks"></a>Osservazioni

Lo scopo principale dello shadowing, noto anche come *nascondiglio per nome*, è quello di mantenere la definizione dei membri della classe. La classe base può subire una modifica che crea un elemento con lo stesso nome di uno già definito. In tal caso, il modificatore di `Shadows` impone la risoluzione dei riferimenti attraverso la classe al membro definito, anziché al nuovo elemento della classe base.

Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali. Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

## <a name="rules"></a>Regole

- **Contesto di dichiarazione.** È possibile utilizzare `Shadows` solo a livello di classe. Ciò significa che il contesto di dichiarazione per un elemento di `Shadows` deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.

  In una singola istruzione di dichiarazione è possibile dichiarare un solo elemento shadowing.

- **Modificatori combinati.** Non è possibile specificare `Shadows` insieme `Overloads`, `Overrides`o `Static` nella stessa dichiarazione.

- **Tipi di elemento.** È possibile nascondere qualsiasi tipo di elemento dichiarato con qualsiasi altro tipo. Se si nasconde una proprietà o una routine con un'altra proprietà o routine, i parametri e il tipo restituito non devono corrispondere a quelli della routine o della proprietà della classe base.

- **Accesso.** L'elemento ombreggiato nella classe base non è in genere disponibile all'interno della classe derivata che lo nasconde. Tuttavia, si applicano le considerazioni seguenti.

  - Se l'elemento shadowing non è accessibile dal codice che vi fa riferimento, il riferimento viene risolto nell'elemento ombreggiato. Se, ad esempio, un elemento `Private` nasconde un elemento della classe base, il codice che non dispone dell'autorizzazione per accedere all'elemento `Private` accede invece all'elemento della classe di base.

  - Se si nasconde un elemento, è comunque possibile accedere all'elemento ombreggiato tramite un oggetto dichiarato con il tipo della classe di base. È anche possibile accedervi tramite `MyBase`.

Il modificatore `Shadows` può essere usato nei contesti seguenti:

- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)

- [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)

- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md)

- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)

- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)

- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)

- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)

- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)

- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Vedere anche

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Static](../../../visual-basic/language-reference/modifiers/static.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)

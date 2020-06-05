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
ms.openlocfilehash: 7aed6bec21bd484cca019b061bd5915de13a9eb8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402707"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

Specifica che un elemento di programmazione dichiarato ridichiara e nasconde un elemento con nome identico o un set di elementi in overload in una classe base.

## <a name="remarks"></a>Commenti

Lo scopo principale dello shadowing, noto anche come *nascondiglio per nome*, è quello di mantenere la definizione dei membri della classe. La classe base può subire una modifica che crea un elemento con lo stesso nome di uno già definito. In tal caso, il `Shadows` modificatore impone la risoluzione dei riferimenti attraverso la classe al membro definito, anziché al nuovo elemento della classe di base.

Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali. Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).

## <a name="rules"></a>Regole

- **Contesto della dichiarazione. ** È possibile usare `Shadows` solo a livello di classe. Ciò significa che il contesto di dichiarazione per un `Shadows` elemento deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.

  In una singola istruzione di dichiarazione è possibile dichiarare un solo elemento shadowing.

- **Modificatori combinati.** Non è possibile specificare `Shadows` insieme a `Overloads` , `Overrides` o `Static` nella stessa dichiarazione.

- **Tipi di elemento.** È possibile nascondere qualsiasi tipo di elemento dichiarato con qualsiasi altro tipo. Se si nasconde una proprietà o una routine con un'altra proprietà o routine, i parametri e il tipo restituito non devono corrispondere a quelli della routine o della proprietà della classe base.

- **Accesso.** L'elemento ombreggiato nella classe base non è in genere disponibile all'interno della classe derivata che lo nasconde. Tuttavia, si applicano le considerazioni seguenti.

  - Se l'elemento shadowing non è accessibile dal codice che vi fa riferimento, il riferimento viene risolto nell'elemento ombreggiato. Se, ad esempio, un `Private` elemento nasconde un elemento della classe base, il codice che non dispone dell'autorizzazione per accedere all'elemento `Private` accede all'elemento della classe di base.

  - Se si nasconde un elemento, è comunque possibile accedere all'elemento ombreggiato tramite un oggetto dichiarato con il tipo della classe di base. È anche possibile accedervi tramite `MyBase` .

Il modificatore `Shadows` può essere usato nei contesti seguenti:

- [Istruzione Class](../statements/class-statement.md)

- [Istruzione Const](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Istruzione Delegate](../statements/delegate-statement.md)

- [Istruzione Dim](../statements/dim-statement.md)

- [Istruzione Enum](../statements/enum-statement.md)

- [Istruzione Event](../statements/event-statement.md)

- [Istruzione Function](../statements/function-statement.md)

- [Istruzione Interface](../statements/interface-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Istruzione Structure](../statements/structure-statement.md)

- [Istruzione Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Vedere anche

- [Condivisa](shared.md)
- [Statico](static.md)
- [Privata](private.md)
- [Me, My, MyBase e MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Overload](overloads.md)
- [Overridable](overridable.md)
- [Override](overrides.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)

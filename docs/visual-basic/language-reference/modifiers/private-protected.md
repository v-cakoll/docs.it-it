---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351350"
---
# <a name="private-protected-visual-basic"></a>Privato protetto (Visual Basic)

La combinazione delle parole chiave `Private Protected` è un modificatore di accesso ai membri. Un membro `Private Protected` è accessibile da tutti i membri della relativa classe che lo contiene, nonché dai tipi derivati dalla classe che lo contiene, ma solo se vengono trovati nell'assembly contenitore.

È possibile specificare `Private Protected` solo per i membri delle classi; non è possibile applicare `Private Protected` ai membri di una struttura perché le strutture non possono essere ereditate.

Il modificatore di accesso `Private Protected` è supportato da Visual Basic 15,5 e versioni successive. Per usarlo, è possibile aggiungere l'elemento seguente al file del progetto Visual Basic (\*. vbproj). Fino a quando nel sistema è installato Visual Basic 15,5 o versione successiva, è possibile sfruttare tutte le funzionalità del linguaggio supportate dalla versione più recente del compilatore Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Per ulteriori informazioni, vedere [impostazione della versione della lingua Visual Basic](../../language-reference/configure-language-version.md).

> [!NOTE]
> In Visual Studio, selezionando la Guida sensibile al contesto `private protected` viene fornita la guida per [privato](private.md) o [protetto](protected.md). L'IDE sceglie il singolo token sotto il cursore anziché la parola composta.

## <a name="rules"></a>Regole

- **Contesto di dichiarazione.** È possibile utilizzare `Private Protected` solo a livello di classe. Ciò significa che il contesto di dichiarazione per un elemento di `Protected` deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.

## <a name="behavior"></a>Comportamento

- **Livello di accesso.** Tutto il codice in una classe può accedere ai relativi elementi. Il codice in qualsiasi classe che deriva da una classe base ed è contenuto nello stesso assembly può accedere a tutti gli elementi `Private Protected` della classe di base. Tuttavia, il codice in qualsiasi classe che deriva da una classe base e che è contenuto in un assembly diverso non può accedere alla classe di base `Private Protected` elementi.

- **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*. Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Il modificatore `Private Protected` può essere usato nei contesti seguenti:

- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md) di una classe annidata

- [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)

- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) di un delegato annidato in una classe

- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Istruzione enum](../../../visual-basic/language-reference/statements/enum-statement.md) di un'enumerazione annidata in una classe

- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)

- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)

- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md) di un'interfaccia annidata in una classe

- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)

- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md) di una struttura annidata in una classe

- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Vedere anche

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Protected Friend](./protected-friend.md)
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: b7d9f81e41950b92c787e2e50fb94fe3d7c07559
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362229"
---
# <a name="private-protected-visual-basic"></a>Privato protetto (Visual Basic)

La combinazione delle parole chiave `Private Protected` è un modificatore di accesso ai membri. Un `Private Protected` membro è accessibile da tutti i membri della classe che lo contiene, nonché dai tipi derivati dalla classe che lo contiene, ma solo se vengono trovati nell'assembly contenitore.

È possibile specificare `Private Protected` solo per i membri delle classi. non è possibile applicare `Private Protected` ai membri di una struttura perché le strutture non possono essere ereditate.

Il `Private Protected` modificatore di accesso è supportato da Visual Basic 15,5 e versioni successive. Per usarlo, è possibile aggiungere l'elemento seguente al file del progetto di Visual Basic ( \* . vbproj). Fino a quando nel sistema è installato Visual Basic 15,5 o versione successiva, è possibile sfruttare tutte le funzionalità del linguaggio supportate dalla versione più recente del compilatore Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Per ulteriori informazioni, vedere [impostazione della versione della lingua Visual Basic](../configure-language-version.md).

> [!NOTE]
> In Visual Studio, selezionando la Guida sensibile al contesto, `private protected` viene fornita una guida per [privato](private.md) o [protetto](protected.md). L'IDE sceglie il singolo token sotto il cursore anziché la parola composta.

## <a name="rules"></a>Regole

- **Contesto della dichiarazione. ** È possibile usare `Private Protected` solo a livello di classe. Ciò significa che il contesto di dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.

## <a name="behavior"></a>Comportamento

- **Livello di accesso.** Tutto il codice in una classe può accedere ai relativi elementi. Il codice in qualsiasi classe che deriva da una classe base e che è contenuto nello stesso assembly può accedere a tutti gli `Private Protected` elementi della classe di base. Tuttavia, il codice in qualsiasi classe che deriva da una classe base e che è contenuto in un assembly diverso non può accedere agli elementi della classe di base `Private Protected` .

- **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*. Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Il modificatore `Private Protected` può essere usato nei contesti seguenti:

- [Istruzione Class](../statements/class-statement.md) di una classe annidata

- [Istruzione Const](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Istruzione Delegate](../statements/delegate-statement.md) di un delegato annidato in una classe

- [Istruzione Dim](../statements/dim-statement.md)

- [Istruzione enum](../statements/enum-statement.md) di un'enumerazione annidata in una classe

- [Istruzione Event](../statements/event-statement.md)

- [Istruzione Function](../statements/function-statement.md)

- [Istruzione Interface](../statements/interface-statement.md) di un'interfaccia annidata in una classe

- [Property Statement](../statements/property-statement.md)

- [Istruzione Structure](../statements/structure-statement.md) di una struttura annidata in una classe

- [Istruzione Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Vedere anche

- [Pubblica](public.md)
- [Protetto](protected.md)
- [Amico](friend.md)
- [Privata](private.md)
- [Protected Friend](./protected-friend.md)
- [Livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)

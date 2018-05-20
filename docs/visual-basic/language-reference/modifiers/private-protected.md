---
title: Protetto privato (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a>Protetto privato (Visual Basic)

La combinazione delle parole chiave `Private Protected` è un modificatore di accesso ai membri. Oggetto `Private Protected` membro è accessibile da tutti i membri nella classe che contiene, sia da tipi derivati dalla classe che lo contiene, ma solo se si trovano nell'assembly che lo contiene. 

È possibile specificare `Private Protected` solo in membri di classi; non è possibile applicare `Private Protected` ai membri di una struttura perché le strutture non possono essere ereditate.

Il `Private Protected` modificatore di accesso è supportato da Visual Basic 15,5 e versioni successive. Per utilizzarlo, è possibile aggiungere l'elemento seguente al file di progetto (*. vbproj) di Visual Basic. Purché 15,5 Visual Basic o versione successiva è installato nel sistema, consente di sfruttare tutte le funzionalità del linguaggio è supportata dalla versione più recente del compilatore Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> In Visual Studio, selezionare la Guida F1 nei `private protected` viene fornita la Guida per uno [privato](private.md) o [protetti](protected.md). L'IDE sceglie il token singolo sotto il cursore anziché la parola composta.

## <a name="rules"></a>Regole

- **Contesto della dichiarazione.** È possibile utilizzare `Private Protected` solo a livello di classe. Ciò significa che il contesto della dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o stored procedure.

## <a name="behavior"></a>Comportamento

- **Livello di accesso.** Tutto il codice in una classe possa accedere ai relativi elementi. Codice di qualsiasi classe che deriva da una classe base ed è inclusa nello stesso assembly possa accedere a tutte le `Private Protected` gli elementi della classe base. Tuttavia, il codice di qualsiasi classe che deriva da una classe di base ed è contenuto in un assembly diverso non può accedere la classe di base `Private Protected` elementi.

- **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*. Per un confronto tra i modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).
  
 Il modificatore `Private Protected` può essere usato nei contesti seguenti:  
  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md) di una classe annidata  
  
 [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) di un delegato annidato in una classe  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md) di un eumeration annidata in una classe 
  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md) di un'interfaccia annidata in una classe 
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Struttura istruzione](../../../visual-basic/language-reference/statements/structure-statement.md) di una struttura annidata in una classe 
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
[Friend](friend.md)   
[Private](../../../visual-basic/language-reference/modifiers/private.md)  
[Protected Friend](./protected-friend.md)   
[Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

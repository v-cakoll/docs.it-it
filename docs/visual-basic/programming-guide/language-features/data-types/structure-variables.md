---
title: Variabili di struttura
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 16b6cdc5a849b50f6caa8b7963dac5c12d63cf3e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346299"
---
# <a name="structure-variables-visual-basic"></a>Variabili di struttura (Visual Basic)

Dopo aver creato una struttura, è possibile dichiarare le variabili a livello di procedura e a livello di modulo come quel tipo. Ad esempio, è possibile creare una struttura che registra le informazioni relative a un sistema di computer. Nell'esempio che segue viene illustrato quanto descritto.

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

È ora possibile dichiarare variabili di quel tipo. Questa operazione viene illustrata nella dichiarazione seguente.

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> Nelle classi e nei moduli, le strutture dichiarate con l' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) sono predefinite per l'accesso pubblico. Se si vuole che una struttura sia privata, assicurarsi di dichiararla usando la parola chiave [private](../../../../visual-basic/language-reference/modifiers/private.md) .

## <a name="access-to-structure-values"></a>Accesso ai valori della struttura

Per assegnare e recuperare valori dagli elementi di una variabile di struttura, è possibile utilizzare la stessa sintassi utilizzata per impostare e ottenere le proprietà di un oggetto. Si inserisce l'operatore di accesso ai membri (`.`) tra il nome della variabile di struttura e il nome dell'elemento. Nell'esempio seguente viene eseguito l'accesso agli elementi delle variabili dichiarate in precedenza come tipo `systemInfo`.

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a>Assegnazione di variabili di struttura

È anche possibile assegnare una variabile a un'altra se entrambe sono dello stesso tipo di struttura. In questo modo tutti gli elementi di una struttura vengono copiati negli elementi corrispondenti dell'altro. Questa operazione viene illustrata nella dichiarazione seguente.

```vb
yourSystem = mySystem
```

Se un elemento della struttura è un tipo di riferimento, ad esempio un `String`, `Object`o una matrice, viene copiato il puntatore ai dati. Nell'esempio precedente, se `systemInfo` aveva incluso una variabile oggetto, l'esempio precedente avrebbe copiato il puntatore da `mySystem` a `yourSystem`e una modifica ai dati dell'oggetto tramite una struttura verrebbe applicata quando si accede tramite l'altra struttura.

## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)

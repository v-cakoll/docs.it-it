---
title: Variabili di struttura
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 270e8ca26185e4a68def3b95f4ce6ab4c57a629c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393585"
---
# <a name="structure-variables-visual-basic"></a>Variabili di struttura (Visual Basic)

Dopo aver creato una struttura, è possibile dichiarare le variabili a livello di procedura e a livello di modulo come quel tipo. Ad esempio, è possibile creare una struttura che registra le informazioni relative a un sistema di computer. L'esempio seguente illustra questa operazione.

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
> Nelle classi e nei moduli, le strutture dichiarate con l' [istruzione Dim](../../../language-reference/statements/dim-statement.md) sono predefinite per l'accesso pubblico. Se si vuole che una struttura sia privata, assicurarsi di dichiararla usando la parola chiave [private](../../../language-reference/modifiers/private.md) .

## <a name="access-to-structure-values"></a>Accesso ai valori della struttura

Per assegnare e recuperare valori dagli elementi di una variabile di struttura, è possibile utilizzare la stessa sintassi utilizzata per impostare e ottenere le proprietà di un oggetto. Si inserisce l'operatore di accesso ai membri ( `.` ) tra il nome della variabile di struttura e il nome dell'elemento. Nell'esempio seguente viene eseguito l'accesso agli elementi delle variabili dichiarate in precedenza come tipo `systemInfo` .

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

Se un elemento della struttura è un tipo di riferimento, ad esempio una `String` `Object` matrice, o, viene copiato il puntatore ai dati. Nell'esempio precedente, se `systemInfo` era inclusa una variabile oggetto, l'esempio precedente avrebbe copiato il puntatore da `mySystem` a `yourSystem` e una modifica ai dati dell'oggetto tramite una struttura verrebbe applicata quando si accede tramite l'altra struttura.

## <a name="see-also"></a>Vedere anche

- [Tipi di dati](index.md)
- [Tipi di dati elementari](elementary-data-types.md)
- [Tipi di dati compositi](composite-data-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Strutture](structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](troubleshooting-data-types.md)
- [Procedura: Dichiarare una struttura](how-to-declare-a-structure.md)
- [Strutture e altri elementi di programmazione](structures-and-other-programming-elements.md)
- [Strutture e classi](structures-and-classes.md)
- [Istruzione Structure](../../../language-reference/statements/structure-statement.md)

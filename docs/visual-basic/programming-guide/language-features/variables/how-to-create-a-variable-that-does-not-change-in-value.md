---
title: 'Procedura: creare una variabile che non cambia di valore'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 04e08784b5cfbdeb6db73b9b00fe9afa201bd06d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410516"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Procedura: creare una variabile che non cambia di valore (Visual Basic)

Il concetto di variabile che non modifica il valore potrebbe sembrare contraddittorio. In alcuni casi, tuttavia, una costante non è fattibile ed è utile avere una variabile con un valore fisso. In tal caso, è possibile definire una variabile membro con la parola chiave [ReadOnly](../../../language-reference/modifiers/readonly.md) .

Non è possibile usare l' [istruzione Const](../../../language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante nelle circostanze seguenti:

- L' `Const` istruzione non accetta il tipo di dati che si desidera utilizzare

- Il valore non è noto in fase di compilazione

- Non è possibile calcolare il valore costante in fase di compilazione

### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Per creare una variabile che non cambia in value

1. A livello di modulo, dichiarare una variabile membro con l' [istruzione Dim](../../../language-reference/statements/dim-statement.md)e includere la parola chiave [ReadOnly](../../../language-reference/modifiers/readonly.md) .

    ```vb
    Dim ReadOnly timeStarted
    ```

    È possibile specificare `ReadOnly` solo su una variabile membro. Ciò significa che è necessario definire la variabile a livello di modulo, al di fuori di qualsiasi routine.

2. Se è possibile calcolare il valore in una singola istruzione in fase di compilazione, utilizzare una clausola di inizializzazione nell' `Dim` istruzione. Seguire la clausola [As](../../../language-reference/statements/as-clause.md) con un segno di uguale ( `=` ), seguito da un'espressione. Verificare che il compilatore possa valutare questa espressione in un valore costante.

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    È possibile assegnare un valore a una `ReadOnly` variabile una sola volta. Quando si esegue questa operazione, non è possibile modificare il valore di codice.

    Se il valore non è noto in fase di compilazione o non può essere calcolato in fase di compilazione in una singola istruzione, è comunque possibile assegnarlo in fase di esecuzione in un costruttore. A tale scopo, è necessario dichiarare la `ReadOnly` variabile a livello di classe o di struttura. Nel costruttore della classe o della struttura, calcolare il valore fisso della variabile e assegnarlo alla variabile prima di restituire dal costruttore.

## <a name="see-also"></a>Vedere anche

- [WriteOnly](../../../language-reference/modifiers/writeonly.md)
- [Istruzione Const](../../../language-reference/statements/const-statement.md)

---
title: 'Procedura: creare una variabile che non cambia di valore'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d5d8a6b066ae7e8795afd2f788b60823d8efdafa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348639"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Procedura: creare una variabile che non cambia di valore (Visual Basic)

Il concetto di variabile che non modifica il valore potrebbe sembrare contraddittorio. In alcuni casi, tuttavia, una costante non è fattibile ed è utile avere una variabile con un valore fisso. In tal caso, è possibile definire una variabile membro con la parola chiave [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .

Non è possibile usare l' [istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante nelle circostanze seguenti:

- L'istruzione `Const` non accetta il tipo di dati che si desidera utilizzare

- Il valore non è noto in fase di compilazione

- Non è possibile calcolare il valore costante in fase di compilazione

### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Per creare una variabile che non cambia in value

1. A livello di modulo, dichiarare una variabile membro con l' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)e includere la parola chiave [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .

    ```vb
    Dim ReadOnly timeStarted
    ```

    È possibile specificare `ReadOnly` solo in una variabile membro. Ciò significa che è necessario definire la variabile a livello di modulo, al di fuori di qualsiasi routine.

2. Se è possibile calcolare il valore in un'unica istruzione in fase di compilazione, utilizzare una clausola di inizializzazione nell'istruzione `Dim`. Seguire la clausola [As](../../../../visual-basic/language-reference/statements/as-clause.md) con un segno di uguale (`=`), seguito da un'espressione. Verificare che il compilatore possa valutare questa espressione in un valore costante.

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    È possibile assegnare un valore a una variabile di `ReadOnly` una sola volta. Quando si esegue questa operazione, non è possibile modificare il valore di codice.

    Se il valore non è noto in fase di compilazione o non può essere calcolato in fase di compilazione in una singola istruzione, è comunque possibile assegnarlo in fase di esecuzione in un costruttore. A tale scopo, è necessario dichiarare la variabile `ReadOnly` a livello di classe o di struttura. Nel costruttore della classe o della struttura, calcolare il valore fisso della variabile e assegnarlo alla variabile prima di restituire dal costruttore.

## <a name="see-also"></a>Vedere anche

- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md)

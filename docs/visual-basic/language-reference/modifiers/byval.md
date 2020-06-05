---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: c4cdafafa6bae3246c0512e28f94fde7e88d230b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373024"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Specifica che un argomento viene passato [per valore](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), in modo che la routine o proprietà chiamata non possa modificare il valore di una variabile sottostante l'argomento nel codice chiamante. Se non si specifica alcun modificatore, ByVal è il valore predefinito.

> [!NOTE]
> Poiché è l'impostazione predefinita, non è necessario specificare in modo esplicito la `ByVal` parola chiave nelle firme dei metodi. Tende a produrre codice rumoroso e spesso conduce alla parola chiave non predefinita da `ByRef` trascurare.

## <a name="remarks"></a>Commenti
 Il modificatore `ByVal` può essere usato nei contesti seguenti:

 [Declare Statement](../statements/declare-statement.md)

 [Istruzione Function](../statements/function-statement.md)
  
 [Operator Statement](../statements/operator-statement.md)
  
 [Property Statement](../statements/property-statement.md)
  
 [Istruzione Sub](../statements/sub-statement.md)

## <a name="example"></a>Esempio
 Nell'esempio seguente viene illustrato l'utilizzo del `ByVal` meccanismo di passaggio del parametro con un argomento di tipo riferimento. Nell'esempio, l'argomento è `c1` , un'istanza della classe `Class1` . `ByVal`impedisce al codice nelle procedure di modificare il valore sottostante dell'argomento di riferimento, `c1` , ma non protegge i campi e le proprietà accessibili di `c1` .

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>Vedere anche

- [Parole chiave](../keywords/index.md)
- [Passaggio di argomenti per valore e per riferimento](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)

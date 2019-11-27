---
title: Default
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: ad4c9528f208cc2c31f07b0506d1b049a7568c86
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351574"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifica una proprietà come proprietà predefinita della relativa classe, struttura o interfaccia.  
  
## <a name="remarks"></a>Osservazioni  
 Una classe, una struttura o un'interfaccia può definire al massimo una delle proprietà come *proprietà predefinita*, purché la proprietà accetti almeno un parametro. Se il codice fa riferimento a una classe o a una struttura senza specificare un membro, Visual Basic risolve il riferimento alla proprietà predefinita.  
  
 Le proprietà predefinite possono causare una riduzione ridotta dei caratteri di codice sorgente, ma possono rendere il codice più difficile da leggere. Se il codice chiamante non ha familiarità con la classe o la struttura, quando fa riferimento al nome della classe o della struttura, non può essere certo se il riferimento accede alla classe o alla struttura o a una proprietà predefinita. Questo può causare errori del compilatore o errori di logica di run-time sottili.  
  
 È possibile ridurre in qualche modo la probabilità di errori di proprietà predefiniti usando sempre l' [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il controllo dei tipi del compilatore su `On`.  
  
 Se si prevede di usare una classe o una struttura predefinita nel codice, è necessario determinare se dispone di una proprietà predefinita e, in caso affermativo, il nome.  
  
 A causa di questi svantaggi, è consigliabile non definire le proprietà predefinite. Per la leggibilità del codice, è consigliabile considerare sempre il riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.  
  
 Il modificatore `Default` può essere usato in questo contesto:  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)

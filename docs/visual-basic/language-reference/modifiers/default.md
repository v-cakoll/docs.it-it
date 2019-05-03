---
title: Default (Visual Basic)
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
ms.openlocfilehash: f78ffe42a9d618d44da2a50c0de831396576430c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800932"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifica una proprietà come proprietà predefinita della relativa classe, struttura o interfaccia.  
  
## <a name="remarks"></a>Note  
 È possibile designare una classe, struttura o interfaccia al massimo una delle relative proprietà come il *predefiniti delle proprietà*, purché tali proprietà richiede almeno un parametro. Se il codice crea un riferimento a una classe o struttura senza specificare un membro, Visual Basic risolve tale riferimento alla proprietà predefinita.  
  
 Proprietà predefinite può determinare un lieve riduzione del numero di caratteri del codice sorgente, ma è possibile rendere il codice più difficile da leggere. Se il codice chiamante non abbia familiarità con la classe o struttura, quando effettua un riferimento al nome della classe o struttura non può essere determinato se il riferimento accede la classe o struttura stessa o una proprietà predefinita. Questo può causare errori del compilatore o meno evidenti in fase di esecuzione della logica.  
  
 In qualche modo, è possibile ridurre le probabilità di errori di proprietà predefiniti utilizzando sempre la [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il tipo del compilatore controllo `On`.  
  
 Se si prevede di usare una struttura o classe predefinite nel codice, è necessario determinare se dispone di una proprietà predefinita e in tal caso, quali il nome sarà.  
  
 A causa di questi svantaggi, è necessario considerare che non definisce le proprietà predefinite. Per la leggibilità del codice, è necessario considerare anche fare sempre riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.  
  
 Il `Default` modificatore può essere usato in questo contesto:  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)

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
ms.openlocfilehash: 555e15110c7af501de05d1f395a72ca4b7800054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595143"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifica una proprietà come proprietà predefinita della relativa classe, struttura o interfaccia.  
  
## <a name="remarks"></a>Note  
 È possibile designare una classe, struttura o interfaccia al massimo una delle relative proprietà come il *proprietà predefinita*, a condizione che accetti almeno un parametro. Se il codice crea un riferimento a una classe o struttura senza specificare un membro, Visual Basic risolve il riferimento alla proprietà predefinita.  
  
 Proprietà predefinite può determinare un lieve riduzione del numero di caratteri del codice sorgente, ma può rendere più difficile la lettura di codice. Se il codice chiamante non ha familiarità con la classe o struttura, quando fa riferimento al nome di classe o struttura non può essere determinato se il riferimento accede la classe o struttura o una proprietà predefinita. Questo può causare errori del compilatore o meno evidenti della logica di runtime.  
  
 Piuttosto, è possibile ridurre il rischio di errori di proprietà predefiniti utilizzando sempre la [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il tipo di compilatore controllo `On`.  
  
 Se si intende utilizzare una struttura o classe predefiniti nel codice, è necessario determinare se dispone di una proprietà predefinita e in tal caso, il relativo nome novità.  
  
 A causa di questi svantaggi, è consigliabile non definire proprietà predefinite. Per la leggibilità del codice, è necessario anche valutare fare sempre riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.  
  
 Il `Default` modificatore può essere utilizzato in questo contesto:  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)

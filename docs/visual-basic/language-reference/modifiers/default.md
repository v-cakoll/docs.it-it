---
title: Default (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18126a0a5b6254da0b43e806b3de1f5b2127e6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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

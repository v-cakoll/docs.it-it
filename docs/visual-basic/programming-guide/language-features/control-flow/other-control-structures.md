---
title: Altre strutture di controllo (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 09e59d25b3b2fc89026295e8500c30dad7b75086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="other-control-structures-visual-basic"></a>Altre strutture di controllo (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]fornisce le strutture di controllo che consentono di eliminare una risorsa o ridurre il numero di volte in cui che è necessario ripetere un riferimento all'oggetto.  
  
## <a name="usingend-using-construction"></a>Utilizzo... Usando la costruzione di fine  
 Il `Using...End Using` costruzione definisce un blocco di istruzioni all'interno del quale utilizza di una risorsa, ad esempio una connessione SQL. Facoltativamente è possibile acquisire la risorsa con il `Using` istruzione. Quando si esce dal `Using` blocco [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Elimina automaticamente la risorsa in modo che sia disponibile per altro codice. La risorsa deve essere locale ed eliminabile. Per altre informazioni, vedere [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Con... Termina con la costruzione  
 Il `With...End With` costruzione consente di specificare un riferimento all'oggetto una volta e quindi eseguire una serie di istruzioni per accedere ai relativi membri. Questo può semplificare il codice e migliorare le prestazioni poiché [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non è necessario ristabilire il riferimento per ogni istruzione che vi accede. Per ulteriori informazioni, vedere [con... Terminare con l'istruzione](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Istruzione Using](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [Istruzione With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)

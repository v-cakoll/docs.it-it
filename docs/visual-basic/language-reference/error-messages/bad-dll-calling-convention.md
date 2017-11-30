---
title: Convenzione di chiamata DLL non valida
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa84e82d2fbe1041af56fdd5cc3855efd814ddf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="bad-dll-calling-convention"></a>Convenzione di chiamata DLL non valida
Gli argomenti passati a una libreria di collegamento dinamico (DLL) devono corrispondere esattamente a quelli previsti per la routine. Convenzioni di chiamata affrontare numero, tipo e ordine degli argomenti. Il programma può chiamare una routine in una DLL che viene passata il tipo non corretto o il numero di argomenti.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Assicurarsi che tutti i tipi di argomento corrispondano a quelli specificati nella dichiarazione di routine che si sta chiamando.  
  
2.  Verificare che si sta passando lo stesso numero di argomenti indicati nella dichiarazione della routine che si sta chiamando.  
  
3.  Se la routine della DLL prevede gli argomenti per valore, assicurarsi che `ByVal` viene specificato per gli argomenti nella dichiarazione della routine.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Istruzione Call](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

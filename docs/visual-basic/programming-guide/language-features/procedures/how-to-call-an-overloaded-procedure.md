---
title: 'Procedura: chiamare una routine di overload (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5eca03de6b6dd2ca2b992196b1ae224f8fbf5068
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Procedura: chiamare una routine di overload (Visual Basic)
Il vantaggio di overload di una routine è la flessibilità della chiamata. Il codice chiamante può ottenere le informazioni che necessarie per passare alla procedura e quindi chiamare un singolo nome di routine indipendentemente dagli argomenti passaggio.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Per chiamare una routine con più di una versione definita  
  
1.  Nel codice chiamante, determinano i dati da passare alla procedura.  
  
2.  Chiamata di routine di scrittura in modo normale, presentazione dei dati nell'elenco di argomenti. Assicurarsi che gli argomenti corrispondere l'elenco di parametri in una delle versioni definite per la routine.  
  
3.  Non è necessario determinare la versione della routine da chiamare. Visual Basic passa il controllo per la versione corrispondente all'elenco di argomenti.  
  
     L'esempio seguente chiama il `post` routine è dichiarata [procedura: definire più versioni di una stored Procedure](./how-to-define-multiple-versions-of-a-procedure.md). Viene ottenuto l'identificazione del cliente, che determina se è un `String` o `Integer`e quindi chiama la stessa procedura in entrambi i casi.  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)  
 [Procedura: Definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)  
 [Risoluzione dell'overload](./overload-resolution.md)  
 [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)

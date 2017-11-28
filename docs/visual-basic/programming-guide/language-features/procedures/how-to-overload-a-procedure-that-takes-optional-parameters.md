---
title: 'Procedura: eseguire l''overload di una routine che accetta parametri facoltativi (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b4a863944d4f9ab265aab52578fbb704ca376de5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>Procedura: eseguire l'overload di una routine che accetta parametri facoltativi (Visual Basic)
Se una stored procedure ha uno o più [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametri, non è possibile definire una versione di overload che corrisponda a uno dei relativi overload impliciti. Per ulteriori informazioni, vedere "Overload impliciti per i parametri facoltativi" in [considerazioni sull'overload procedure](./considerations-in-overloading-procedures.md).  
  
## <a name="one-optional-parameter"></a>Un parametro facoltativo  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>Eseguire l'overload che accetta un parametro facoltativo  
  
1.  Scrivere un `Sub` o `Function` istruzione di dichiarazione che include il parametro facoltativo nell'elenco di parametri. Non utilizzare il `Optional` parola chiave in questa versione di overload.  
  
2.  Anteporre il `Sub` o `Function` parola chiave with il [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).  
  
3.  Scrivere il codice di routine che deve essere eseguito quando il codice chiamante fornisce un argomento facoltativo.  
  
4.  Terminare la procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.  
  
5.  Scrivere una seconda istruzione di dichiarazione è identica alla prima dichiarazione, ad eccezione del fatto che non include il parametro facoltativo nell'elenco di parametri.  
  
6.  Scrivere il codice di routine che deve essere eseguito quando il codice chiamante non specifica l'argomento facoltativo. Terminare la procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.  
  
     Nell'esempio seguente viene illustrata una routine definita con un parametro facoltativo, un set equivalente di due overload di routine e infine esempi delle versioni di overload validi e non validi.  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## <a name="multiple-optional-parameters"></a>Più parametri facoltativi  
 Per una routine con più di un parametro facoltativo, è necessario in genere più di due versioni di overload. Ad esempio, se sono presenti due parametri facoltativi e il codice chiamante può specificare o omettere ognuno indipendente, è necessario quattro versioni di overload, uno per ogni possibile combinazione di argomenti forniti.  
  
 Man mano che aumenta il numero di parametri facoltativi, aumenta la complessità dell'overload. A meno che alcune combinazioni di argomenti forniti non sono accettabili, per i parametri facoltativi di N è necessario 2 ^ N versioni di overload. A seconda della natura della procedura, è possibile che la semplicità della logica giustifica lo sforzo aggiuntivo della definizione di tutte le versioni di overload.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>Eseguire l'overload che accetta più di un parametro facoltativo  
  
1.  Determinare le combinazioni di argomenti facoltativi forniti sono accettabili per la logica della routine. Una combinazione inaccettabile potrebbe verificarsi se un parametro facoltativo dipende da un altro. Ad esempio, se un parametro accetta un nome coniuge e un altro accetta l'età, una combinazione di argomenti che specifica l'età, ma omette il nome è accettabile.  
  
2.  Per ogni combinazione accettabile di argomenti facoltativi forniti, scrivere un `Sub` o `Function` istruzione di dichiarazione che definisce l'elenco di parametri corrispondenti. Non utilizzare il `Optional` (parola chiave).  
  
3.  In ogni dichiarazione far precedere il `Sub` o `Function` parola chiave with il [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).  
  
4.  Dopo ogni dichiarazione, scrivere il codice che deve essere eseguito quando il codice chiamante fornisce un elenco di argomenti corrispondente all'elenco di parametri della dichiarazione della routine.  
  
5.  Terminare ogni routine con il `End Sub` o `End Function` istruzione nel modo appropriato.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Parametri facoltativi](./optional-parameters.md)  
 [Matrici di parametri](./parameter-arrays.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)  
 [Procedura: Definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)  
 [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Risoluzione dell'overload](./overload-resolution.md)

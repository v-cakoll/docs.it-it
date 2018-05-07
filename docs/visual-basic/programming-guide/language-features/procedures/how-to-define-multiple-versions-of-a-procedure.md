---
title: 'Procedura: definire più versioni di una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: a4d0c5bbb07dd5433ff62179fc10a6274bf19364
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Procedura: definire più versioni di una routine (Visual Basic)
È possibile definire una routine in più versioni da *overload* utilizzando lo stesso nome ma un elenco di parametri diversi per ogni versione. Lo scopo dell'overload consiste nel definire più versioni strettamente correlate di una stored procedure senza la necessità di distinguere per nome.  
  
 Per ulteriori informazioni, vedere [overload di routine](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Per definire più versioni di una stored procedure  
  
1.  Scrivere un `Sub` o `Function` istruzione di dichiarazione per ogni versione della procedura di cui si desidera definire. Usare lo stesso nome di stored procedure in ogni dichiarazione.  
  
2.  Anteporre il `Sub` o `Function` (parola chiave) in ogni dichiarazione con il [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave). È possibile omettere `Overloads` nelle dichiarazioni, ma se si include in una qualsiasi delle dichiarazioni, è necessario includerlo in ogni dichiarazione.  
  
3.  Dopo ogni istruzione di dichiarazione, scrivere il codice di procedure per gestire il caso specifico in cui il codice chiamante fornisce argomenti corrispondenti elenco di parametri di quella versione. Non si dispone di test per i parametri che è stato fornito il codice chiamante. Visual Basic passa il controllo per la versione corrispondente della routine.  
  
4.  Terminare ogni versione della routine con il `End Sub` o `End Function` istruzione nel modo appropriato.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce un `Sub` procedura per registrare una transazione al saldo di un cliente. Usa il `Overloads` (parola chiave) per definire due versioni della routine, una che accetta il cliente con nome e l'altra per numero di conto.  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 Il codice chiamante può ottenere l'identificazione del cliente come un `String` o `Integer`e quindi utilizzare la stessa istruzione di chiamata in entrambi i casi.  
  
 Per informazioni su come chiamare le versioni del `post` procedura, vedere [procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Verificare che le versioni di overload con lo stesso nome di stored procedure ma un elenco di parametri diverso.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)  
 [Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)  
 [Risoluzione dell'overload](./overload-resolution.md)

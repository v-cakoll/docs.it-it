---
title: 'Procedura: definire più versioni di una routine'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: e8ed9a6356b7177b2c029a9280d0790a93676653
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347588"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Procedura: definire più versioni di una routine (Visual Basic)
È possibile definire una stored procedure in più versioni eseguendo l' *Overload* , usando lo stesso nome ma un elenco di parametri diverso per ogni versione. Lo scopo dell'overload è definire diverse versioni strettamente correlate di una stored procedure senza doverle differenziare per nome.  
  
 Per altre informazioni, vedere [Procedure Overloading](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Per definire più versioni di una routine  
  
1. Scrivere un'istruzione di dichiarazione `Sub` o `Function` per ogni versione della procedura che si desidera definire. Utilizzare lo stesso nome di procedura in ogni dichiarazione.  
  
2. Precede la parola chiave `Sub` o `Function` in ogni dichiarazione con la parola chiave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) . Facoltativamente, è possibile omettere `Overloads` nelle dichiarazioni, ma se lo si include in una delle dichiarazioni, è necessario includerlo in ogni dichiarazione.  
  
3. Dopo ogni istruzione di dichiarazione, scrivere il codice della procedura per gestire il caso specifico in cui il codice chiamante fornisce argomenti corrispondenti all'elenco di parametri della versione. Non è necessario testare i parametri forniti dal codice chiamante. Visual Basic passa il controllo alla versione corrispondente della routine.  
  
4. Terminare ogni versione della routine con l'istruzione `End Sub` o `End Function` in base alle esigenze.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definita una procedura `Sub` per pubblicare una transazione in base al saldo del cliente. Usa la parola chiave `Overloads` per definire due versioni della procedura, una che accetta il cliente in base al nome e l'altra per numero di conto.  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 Il codice chiamante può ottenere l'identificazione del cliente come un `String` o un `Integer`e quindi usare la stessa istruzione chiamante in entrambi i casi.  
  
 Per informazioni su come chiamare queste versioni della procedura `post`, vedere procedura [: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Verificare che ogni versione di overload abbia lo stesso nome di procedura ma un elenco di parametri diverso.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)
- [Risoluzione dell'overload](./overload-resolution.md)

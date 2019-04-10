---
title: 'Procedura: Definire più versioni di una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: fc7a8e18394b904f0c22a80f71dee091d4f786ab
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324032"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Procedura: Definire più versioni di una routine (Visual Basic)
È possibile definire una procedura in più versioni da *overload* utilizzando lo stesso nome ma un elenco di parametri diversi per ogni versione. Lo scopo dell'overload consiste nel definire più versioni strettamente correlate di una stored procedure senza la necessità di distinguerli in base al nome.  
  
 Per altre informazioni, vedere [Procedure Overloading](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Per definire più versioni di una stored procedure  
  
1. Scrivere un `Sub` o `Function` istruzione di dichiarazione per ciascuna versione della procedura di cui si vuole definire. Usare il nome della routine stessa in ogni dichiarazione.  
  
2. Far precedere il `Sub` o `Function` parola chiave in ogni dichiarazione con la [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave). Facoltativamente, è possibile omettere `Overloads` nelle dichiarazioni, ma se si include in una qualsiasi delle dichiarazioni, è necessario includerlo in ogni dichiarazione.  
  
3. Dopo ogni istruzione di dichiarazione, scrivere il codice delle procedure per gestire il caso specifico in cui il codice chiamante fornisca gli argomenti corrispondenti elenco di parametri di tale versione. Non è necessario testare per i parametri che ha fornito il codice chiamante. Visual Basic passa il controllo per la versione corrispondente di routine.  
  
4. Terminare ogni versione della routine con la `End Sub` o `End Function` istruzione nel modo appropriato.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce un `Sub` procedure per inserire una transazione al saldo di un cliente. Usa il `Overloads` parola chiave per definire due versioni della routine, uno che accetta il cliente per nome e l'altro per numero di account.  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 Il codice chiamante può ottenere l'identificazione del cliente come un `String` o un `Integer`e quindi usare la stessa istruzione di chiamata in entrambi i casi.  
  
 Per informazioni su come chiamare queste versioni del `post` procedure, vedere [come: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Assicurarsi che ognuna delle versioni di overload con lo stesso nome di procedura ma un elenco di parametri diverso.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)
- [Overload Resolution](./overload-resolution.md)

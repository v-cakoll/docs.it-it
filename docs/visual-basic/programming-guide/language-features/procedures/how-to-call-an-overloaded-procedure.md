---
title: 'Procedura: chiamare una routine di overload'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: de101309fa1edaaddc3defc5759d9293fbef684c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388543"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Procedura: chiamare una routine di overload (Visual Basic)
Il vantaggio dell'overload di una stored procedure è la flessibilità della chiamata. Il codice chiamante può ottenere le informazioni necessarie per passare alla routine e quindi chiamare un solo nome di routine, indipendentemente dagli argomenti che passano.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Per chiamare una routine con più di una versione definita  
  
1. Nel codice chiamante determinare i dati da passare alla routine.  
  
2. Scrivere la chiamata di procedura in modo normale, presentando i dati nell'elenco di argomenti. Assicurarsi che gli argomenti corrispondano all'elenco di parametri in una delle versioni definite per la stored procedure.  
  
3. Non è necessario determinare la versione della procedura da chiamare. Visual Basic passa il controllo alla versione corrispondente all'elenco di argomenti.  
  
     Nell'esempio seguente viene chiamata la `post` procedura dichiarata in [procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md). Ottiene l'identificazione del cliente, determina se è un `String` oggetto o `Integer` , quindi in entrambi i casi chiama la stessa procedura.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Overload della routine](./procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)
- [Risoluzione dell'overload](./overload-resolution.md)
- [Overload](../../../language-reference/modifiers/overloads.md)

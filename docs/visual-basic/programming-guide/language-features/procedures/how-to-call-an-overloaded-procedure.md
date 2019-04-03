---
title: 'Procedura: Chiamare una routine di overload (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 9dda0fbc0cffe8904ab97c46cea40d5cf00c91e9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843786"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Procedura: Chiamare una routine di overload (Visual Basic)
Il vantaggio di overload di una routine è la flessibilità della chiamata. Il codice chiamante può ottenere le informazioni che necessarie per passare alla procedura e quindi chiamare un nome di procedura singolo, indipendentemente dagli argomenti è stato superato.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Per chiamare una routine che ha più di una versione definita  
  
1.  Nel codice chiamante, determinare a quali dati da passare alla procedura.  
  
2.  Scrivere la chiamata di routine in modo normale, presentazione dei dati nell'elenco di argomenti. Assicurarsi che gli argomenti corrispondono all'elenco di parametri in una delle versioni definite per la procedura.  
  
3.  Non è necessario determinare quale versione della routine da chiamare. Visual Basic passa il controllo per la versione corrispondente all'elenco di argomenti.  
  
     L'esempio seguente chiama il `post` routine dichiarata [come: Definire più versioni di una stored Procedure](./how-to-define-multiple-versions-of-a-procedure.md). Ottiene l'identificazione del cliente, determina se è un `String` o un `Integer`e quindi chiama la stessa procedura in entrambi i casi.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Overload della routine](./procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: Definire più versioni di una stored Procedure](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: Overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)
- [Risoluzione dell'overload](./overload-resolution.md)
- [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)

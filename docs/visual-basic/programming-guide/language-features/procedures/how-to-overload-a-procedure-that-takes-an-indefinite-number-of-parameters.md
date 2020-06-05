---
title: "Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri"
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: ddff8c8cd82593b7d89fb0847e56123c287e364b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387881"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)
Se una stored procedure dispone di un parametro [ParamArray](../../../language-reference/modifiers/paramarray.md) , non è possibile definire una versione di overload che accetta una matrice unidimensionale per la matrice di parametri. Per ulteriori informazioni, vedere "Overload impliciti per un parametro ParamArray" in [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Per eseguire l'overload di una routine che accetta un numero variabile di parametri  
  
1. Verificare che la procedura e la chiamata della logica del codice beneficino di versioni di overload più che da un `ParamArray` parametro. Vedere "Overload e ParamArray" in [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).  
  
2. Determinare il numero di valori forniti che la routine deve accettare nella parte variabile dell'elenco di parametri. Questo potrebbe includere il caso di nessun valore e potrebbe includere il caso di una singola matrice unidimensionale.  
  
3. Per ogni numero accettabile di valori forniti, scrivere un' `Sub` `Function` istruzione di dichiarazione o che definisce l'elenco di parametri corrispondente. Non usare la `Optional` `ParamArray` parola chiave o in questa versione di overload.  
  
4. In ogni dichiarazione, precede la `Sub` `Function` parola chiave o con la parola chiave [Overloads](../../../language-reference/modifiers/overloads.md) .  
  
5. Dopo ogni dichiarazione, scrivere il codice della procedura da eseguire quando il codice chiamante fornisce valori corrispondenti all'elenco di parametri della dichiarazione.  
  
6. Terminare ogni procedura con l' `End Sub` `End Function` istruzione o in base alle esigenze.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una procedura definita con un parametro [ParamArray](../../../language-reference/modifiers/paramarray.md) , quindi un set equivalente di routine di overload.  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Non è possibile eseguire l'overload di questa procedura con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri. Tuttavia, è possibile usare le firme degli altri overload impliciti. Questa operazione viene illustrata nelle dichiarazioni seguenti.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 Il codice nelle versioni di overload non deve verificare se il codice chiamante ha fornito uno o più valori per il `ParamArray` parametro o, in caso affermativo, il numero. Visual Basic passa il controllo alla versione corrispondente all'elenco di argomenti chiamante.  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Poiché una procedura con un `ParamArray` parametro è equivalente a un set di versioni di overload, non è possibile eseguire l'overload di tale procedura con un elenco di parametri corrispondente a uno di questi overload impliciti. Per ulteriori informazioni, vedere [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Ogni volta che si tratta di una matrice che può essere indefinitamente grande, esiste il rischio di sovraeseguire una capacità interna dell'applicazione. Se si accetta una matrice di parametri, è necessario verificare la lunghezza della matrice a cui è stato passato il codice chiamante ed eseguire le operazioni appropriate se è troppo grande per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Overload della routine](./procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Risoluzione dell'overload](./overload-resolution.md)

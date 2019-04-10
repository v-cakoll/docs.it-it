---
title: "Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)"
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
ms.openlocfilehash: 3cf75fc6221364704379eb23d308481c34e6c0d6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316453"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)
Se una routine ha un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro, non è possibile definire una versione di overload che accetta una matrice unidimensionale per la matrice di parametri. Per altre informazioni, vedere "Overloads impliciti per un parametro ParamArray" nella [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Eseguire l'overload di una routine che accetta un numero variabile di parametri  
  
1. Verificare che la stored procedure e la chiamata a vantaggi per la logica del codice dal sovraccarico versioni da più di un `ParamArray` parametro. Vedere "Overload e i parametri ParamArray" nella [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).  
  
2. Determinare i numeri dei valori specificati deve accettare la procedura nella parte variabile all'elenco di parametri. Ciò potrebbe includere il caso di alcun valore e può includere il caso di una matrice unidimensionale.  
  
3. Per ogni numero di valori forniti accettabile, scrivere un `Sub` o `Function` istruzione di dichiarazione che definisce l'elenco di parametri corrispondenti. Non usare la `Optional` o il `ParamArray` parola chiave in questa versione di overload.  
  
4. In ogni dichiarazione, anteporre il `Sub` o `Function` parola chiave with il [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).  
  
5. Dopo ogni dichiarazione, scrivere il codice che deve essere eseguita quando il codice chiamante fornisce i valori corrispondenti all'elenco dei parametri della dichiarazione della routine.  
  
6. Terminare ogni procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra una procedura definita con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro e quindi un set equivalente routine di overload.  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 È possibile eseguire l'overload di una procedura con un elenco di parametri che accetta una matrice unidimensionale la matrice di parametri. Tuttavia, è possibile utilizzare le firme degli altri overload impliciti. Le seguenti dichiarazioni di illustrare questo concetto.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 Non è necessario il codice nelle versioni di overload verificare se il codice chiamante fornito uno o più valori per il `ParamArray` parametro, in caso affermativo, il numero. Visual Basic passa il controllo alla versione associando l'elenco di argomento chiamante.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Poiché una procedura con un `ParamArray` parametro equivale a un set di versioni di overload, è possibile eseguire l'overload di una routine con un elenco di parametri corrispondente a uno di questi overload impliciti. Per altre informazioni, vedere [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Ogni volta che gestisce una matrice che può essere elevato per un periodo illimitato, sussiste il rischio di sovraccaricare capacità interna dell'applicazione. Se si accetta una matrice di parametri, si deve verificare la lunghezza della matrice passato al codice chiamante ed eseguire i passaggi appropriati, se è troppo grande per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Overload delle routine](./procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: Definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Overload Resolution](./overload-resolution.md)

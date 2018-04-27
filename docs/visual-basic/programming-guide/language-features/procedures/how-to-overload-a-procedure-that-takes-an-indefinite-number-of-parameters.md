---
title: "Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)"
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8cb4faa2dfd01f854dcc3bf8c2a330adf5acdcac
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)
Se una stored procedure ha un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro, non è possibile definire una versione di overload che accetta una matrice unidimensionale per la matrice di parametri. Per ulteriori informazioni, vedere "Overload impliciti per un parametro ParamArray" in [considerazioni sull'overload procedure](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Eseguire l'overload che accetta un numero variabile di parametri  
  
1.  Verificare che la stored procedure e la chiamata di codice logica beneficerà overload versioni da più di un `ParamArray` parametro. Vedere "Overload e i parametri ParamArray" [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).  
  
2.  Determinare il numero di valori forniti la routine deve accettare nella parte variabile all'elenco di parametri. Possono essere inclusi nel caso di alcun valore, e può includere nel caso di una matrice unidimensionale.  
  
3.  Per ogni numero accettabile di valori forniti, scrivere un `Sub` o `Function` istruzione di dichiarazione che definisce l'elenco di parametri corrispondenti. Non utilizzare il `Optional` o `ParamArray` parola chiave in questa versione di overload.  
  
4.  In ogni dichiarazione far precedere il `Sub` o `Function` parola chiave with il [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).  
  
5.  Dopo ogni dichiarazione, scrivere il codice che deve essere eseguito quando il codice chiamante fornisce valori corrispondenti all'elenco di parametri della dichiarazione della routine.  
  
6.  Terminare ogni routine con il `End Sub` o `End Function` istruzione nel modo appropriato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una routine definita con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro e un set equivalente di routine di overload.  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 È possibile eseguire l'overload di una procedura con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri. Tuttavia, è possibile utilizzare le firme di overload impliciti. Le seguenti dichiarazioni di illustrare questo concetto.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 Il codice nelle versioni di overload non è necessario verificare se il codice chiamante ha fornito uno o più valori per il `ParamArray` parametro, in caso affermativo, il numero. Visual Basic passa il controllo della versione associando l'elenco di argomento chiamante.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Poiché una routine con un `ParamArray` parametro è equivalente a un set di versioni di overload, è possibile eseguire l'overload di una routine con un elenco di parametri corrispondente a uno di questi overload impliciti. Per ulteriori informazioni, vedere [considerazioni sull'overload procedure](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Ogni volta che gestisce una matrice che può essere elevata per un periodo illimitato, c'è un rischio di sovraccaricare capacità interna dell'applicazione. Se si accetta una matrice di parametri, si deve verificare la lunghezza della matrice passato al codice chiamante e adottare se è troppo grande per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Parametri facoltativi](./optional-parameters.md)  
 [Matrici di parametri](./parameter-arrays.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)  
 [Procedura: Definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)  
 [Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Risoluzione dell'overload](./overload-resolution.md)

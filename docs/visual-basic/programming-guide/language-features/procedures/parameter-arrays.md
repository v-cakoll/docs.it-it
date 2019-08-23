---
title: Matrici di parametri (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: 5a2813b81490e7c2fcf1abcf5fd36ca89d9d7929
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933852"
---
# <a name="parameter-arrays-visual-basic"></a>Matrici di parametri (Visual Basic)
In genere, non è possibile chiamare una routine con più argomenti rispetto a quanto specificato nella dichiarazione di routine. Quando è necessario un numero indefinito di argomenti, è possibile dichiarare una *matrice di parametri*, che consente a una routine di accettare una matrice di valori per un parametro. Non è necessario individuare il numero di elementi nella matrice di parametri quando si definisce la procedura. La dimensione della matrice viene determinata singolarmente da ogni chiamata alla stored procedure.  
  
## <a name="declaring-a-paramarray"></a>Dichiarazione di un ParamArray  
 Usare la parola chiave [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) per indicare una matrice di parametri nell'elenco di parametri. È necessario attenersi alle regole che seguono:  
  
- Una routine può definire solo una matrice di parametri e deve essere l'ultimo parametro nella definizione della procedura.  
  
- La matrice di parametri deve essere passata per valore. È consigliabile includere in modo esplicito la parola chiave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) nella definizione della procedura.  
  
- La matrice di parametri è automaticamente facoltativa. Il valore predefinito è una matrice unidimensionale vuota del tipo di elemento della matrice di parametri.  
  
- Tutti i parametri che precedono la matrice di parametri devono essere obbligatori. La matrice di parametri deve essere l'unico parametro facoltativo.  
  
## <a name="calling-a-paramarray"></a>Chiamata di un ParamArray  
 Quando si chiama una routine che definisce una matrice di parametri, è possibile fornire l'argomento in uno dei modi seguenti:  
  
- Niente, ovvero è possibile omettere l'argomento [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) . In questo caso, alla routine viene passata una matrice vuota. È anche possibile passare la parola chiave [Nothing](../../../../visual-basic/language-reference/nothing.md) con lo stesso effetto.  
  
- Elenco di un numero arbitrario di argomenti, separati da virgole. Il tipo di dati di ogni argomento deve essere convertibile in `ParamArray` modo implicito nel tipo di elemento.  
  
- Matrice con lo stesso tipo di elemento del tipo di elemento della matrice di parametri.  
  
 In tutti i casi, il codice all'interno della routine considera la matrice di parametri come matrice unidimensionale con elementi dello stesso tipo `ParamArray` di dati del tipo di dati.  
  
> [!IMPORTANT]
> Ogni volta che si tratta di una matrice che può essere indefinitamente grande, esiste il rischio di sovraeseguire una capacità interna dell'applicazione. Se si accetta una matrice di parametri, è necessario verificare la dimensione della matrice passata al codice chiamante. Eseguire le operazioni appropriate se è troppo grande per l'applicazione. Per altre informazioni, vedere [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definita e chiamata la `calcSum`funzione. Il `ParamArray` modificatore per il `args` parametro consente alla funzione di accettare un numero variabile di argomenti.  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 Nell'esempio seguente viene definita una procedura con una matrice di parametri e vengono restituiti i valori di tutti gli elementi della matrice passati alla matrice di parametri.  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Overload della routine](./procedure-overloading.md)
- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md)

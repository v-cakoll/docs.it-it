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
ms.openlocfilehash: 372d5fdd2702d6f85f784ee5addea91abe46d3bd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64639013"
---
# <a name="parameter-arrays-visual-basic"></a>Matrici di parametri (Visual Basic)
In genere, non è possibile chiamare una routine con più argomenti di dichiarazione di routine specifica. Quando è necessario un numero indefinito di argomenti, è possibile dichiarare un *matrice di parametri*, che consente a una routine accettare una matrice di valori per un parametro. Non è necessario conoscere il numero di elementi nella matrice del parametro quando si definisce la procedura. La dimensione della matrice viene determinata singolarmente per ogni chiamata alla procedura.  
  
## <a name="declaring-a-paramarray"></a>La dichiarazione di un parametro ParamArray  
 Si utilizza il [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) (parola chiave) per indicare una matrice di parametri nell'elenco dei parametri. È necessario attenersi alle regole che seguono:  
  
- Una routine può definire solo una matrice di parametri e deve essere l'ultimo parametro nella definizione della procedura.  
  
- La matrice di parametri deve essere passata per valore. È buona norma includere in modo esplicito il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) parola chiave nella definizione della procedura.  
  
- La matrice di parametri è automaticamente facoltativa. Il valore predefinito è una matrice unidimensionale vuota del tipo di elemento della matrice di parametri.  
  
- Tutti i parametri che precedono la matrice di parametri devono essere obbligatori. La matrice di parametri deve essere l'unico parametro facoltativo.  
  
## <a name="calling-a-paramarray"></a>La chiamata a un parametro ParamArray  
 Quando si chiama una routine che definisce una matrice di parametri, è possibile fornire l'argomento in uno dei modi seguenti:  
  
- Nothing, vale a dire, è possibile omettere il [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argomento. In questo caso, una matrice vuota viene passata alla routine. È anche possibile passare il [Nothing](../../../../visual-basic/language-reference/nothing.md) (parola chiave), con lo stesso effetto.  
  
- Elenco di un numero arbitrario di argomenti, separati da virgole. Il tipo di dati di ogni argomento deve essere convertibile in modo implicito per il `ParamArray` tipo di elemento.  
  
- Una matrice con lo stesso tipo di elemento come tipo di elemento della matrice di parametri.  
  
 In tutti i casi, il codice all'interno della routine considera la matrice di parametri come una matrice unidimensionale con gli elementi dello stesso tipo di dati come il `ParamArray` tipo di dati.  
  
> [!IMPORTANT]
>  Ogni volta che gestisce una matrice che può essere elevato per un periodo illimitato, sussiste il rischio di sovraccaricare capacità interna dell'applicazione. Se si accetta una matrice di parametri, è necessario testare per la dimensione della matrice che il codice chiamante è passato ad esso. Se è troppo grande per l'applicazione, eseguire i passaggi appropriati. Per altre informazioni, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente definisce e chiama la funzione `calcSum`. Il `ParamArray` modificatore del parametro `args` consente alla funzione di accettare un numero variabile di argomenti.  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 Nell'esempio seguente definisce una routine con una matrice di parametri e restituisce i valori di tutti gli elementi della matrice passati alla matrice di parametri.  
  
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
- [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)

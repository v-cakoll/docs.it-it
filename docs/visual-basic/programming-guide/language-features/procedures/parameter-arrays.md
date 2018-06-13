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
ms.openlocfilehash: a91da0d9e16ff11fdd4980588fee64b3e4a603c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652377"
---
# <a name="parameter-arrays-visual-basic"></a>Matrici di parametri (Visual Basic)
In genere, è possibile chiamare una routine con più argomenti di specifica la dichiarazione di routine. Quando è necessario un numero indefinito di argomenti, è possibile dichiarare un *matrice di parametri*, che consente una routine di accettare una matrice di valori per un parametro. Non è necessario conoscere il numero di elementi nella matrice di parametri quando si definisce la procedura. Le dimensioni della matrice vengano determinata singolarmente per ogni chiamata alla procedura.  
  
## <a name="declaring-a-paramarray"></a>Dichiarazione di un parametro ParamArray  
 Utilizzare il [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) (parola chiave) per indicare una matrice di parametri nell'elenco di parametri. È necessario attenersi alle regole che seguono:  
  
-   Una stored procedure può definire solo una matrice di parametri e deve essere l'ultimo parametro nella definizione della routine.  
  
-   La matrice di parametri deve essere passata per valore. È buona norma di programmazione includere in modo esplicito il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) parola chiave nella definizione della routine.  
  
-   Matrice di parametri è automaticamente facoltativa. Il valore predefinito è una matrice unidimensionale vuota di tipo di elemento della matrice di parametri.  
  
-   Tutti i parametri che precedono la matrice di parametri devono essere obbligatori. Matrice di parametri deve essere l'unico parametro facoltativo.  
  
## <a name="calling-a-paramarray"></a>La chiamata a un parametro ParamArray  
 Quando si chiama una routine che definisce una matrice di parametri, è possibile fornire l'argomento in uno dei modi seguenti:  
  
-   Nothing, vale a dire, è possibile omettere il [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argomento. In questo caso, una matrice vuota viene passata alla routine. È inoltre possibile passare il [nulla](../../../../visual-basic/language-reference/nothing.md) (parola chiave), con lo stesso effetto.  
  
-   Un elenco di un numero arbitrario di argomenti, separati da virgole. Il tipo di dati di ogni argomento deve essere convertibile in modo implicito il `ParamArray` tipo di elemento.  
  
-   Una matrice con lo stesso tipo di elemento come tipo di elemento della matrice di parametri.  
  
 In tutti i casi, il codice all'interno della routine considera la matrice di parametri come una matrice unidimensionale con gli elementi dello stesso tipo di dati come il `ParamArray` tipo di dati.  
  
> [!IMPORTANT]
>  Ogni volta che gestisce una matrice che può essere elevata per un periodo illimitato, c'è un rischio di sovraccaricare capacità interna dell'applicazione. Se si accetta una matrice di parametri, è necessario verificare le dimensioni della matrice passato al codice chiamante. Adottare se è troppo grande per l'applicazione. Per ulteriori informazioni, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente definisce e chiama la funzione `calcSum`. Il `ParamArray` modificatore per il parametro `args` consente alla funzione di accettare un numero variabile di argomenti.  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 Nell'esempio seguente definisce una routine con una matrice di parametri e restituisce i valori di tutti gli elementi della matrice passati alla matrice di parametri.  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)  
 [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)  
 [Parametri facoltativi](./optional-parameters.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Array](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)

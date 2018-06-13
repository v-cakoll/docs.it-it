---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: f88020c7407fb9c91e06bc2ee177773171e344fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599304"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)
Specifica che un argomento di routine può essere omesso quando viene chiamata la procedura.  
  
## <a name="remarks"></a>Note  
 Per ogni parametro facoltativo, è necessario specificare un'espressione costante come valore predefinito di tale parametro. Se l'espressione restituisce [nulla](../../../visual-basic/language-reference/nothing.md), il valore predefinito del tipo di dati di valore viene utilizzato come valore predefinito del parametro.  
  
 Se l'elenco dei parametri contiene un parametro facoltativo, ogni parametro che segue deve essere facoltativo.  
  
 Il modificatore `Optional` può essere usato nei contesti seguenti:  
  
-   [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  Quando si chiama una routine con o senza parametri facoltativi, è possibile passare argomenti in base alla posizione o al nome. Per ulteriori informazioni, vedere [il passaggio di argomenti in base alla posizione e al nome](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  È inoltre possibile definire una routine con parametri facoltativi utilizzando l'overload. Se si dispone di un parametro facoltativo, è possibile definire due versioni di overload della routine, una che accetta il parametro e uno senza. Per ulteriori informazioni, vedere [overload di routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente definisce una routine che ha un parametro facoltativo.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come chiamare una routine con gli argomenti passati in base alla posizione e con gli argomenti passati per nome. La procedura include due parametri facoltativi.  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Elenco dei parametri](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Parametri facoltativi](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)

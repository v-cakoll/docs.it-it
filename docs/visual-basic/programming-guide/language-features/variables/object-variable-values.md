---
title: Valori di variabili oggetto
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: 8b93063d2d97802b1a7fdbc93e01040ff3337753
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351794"
---
# <a name="object-variable-values-visual-basic"></a>Valori di variabili oggetto (Visual Basic)
Una variabile del [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) può fare riferimento a dati di qualsiasi tipo. Il valore archiviato in una variabile di `Object` viene mantenuto in memoria, mentre la variabile stessa mantiene un puntatore ai dati.  
  
## <a name="object-classifier-functions"></a>Funzioni di classificazione oggetti  
 Visual Basic fornisce funzioni che restituiscono informazioni sul riferimento a una variabile `Object`, come illustrato nella tabella seguente.  
  
|Funzione|Restituisce true se la variabile oggetto fa riferimento a|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Matrice di valori, anziché un singolo valore.|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Valore del [tipo di dati date](../../../../visual-basic/language-reference/data-types/date-data-type.md) oppure stringa che può essere interpretata come valore di data e ora|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Oggetto di tipo <xref:System.DBNull>, che rappresenta dati mancanti o inesistenti|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Oggetto eccezione, che deriva da <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Niente](../../../../visual-basic/language-reference/nothing.md), ovvero nessun oggetto è attualmente assegnato alla variabile|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Un numero o una stringa che può essere interpretata come numero|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Un tipo di riferimento (ad esempio una stringa, una matrice, un delegato o un tipo di classe)|  
  
 È possibile utilizzare queste funzioni per evitare di inviare un valore non valido a un'operazione o a una routine.  
  
## <a name="typeof-operator"></a>Operatore TypeOf  
 È anche possibile usare l' [operatore typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) per determinare se una variabile oggetto si riferisce attualmente a un tipo di dati specifico. L'espressione `TypeOf`...`Is` restituisce `True` se il tipo in fase di esecuzione dell'operando è derivato da o implementa il tipo specificato.  
  
 Nell'esempio seguente viene usato `TypeOf` sulle variabili oggetto che fanno riferimento a tipi di valore e di riferimento.  
  
```vb  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 Nell'esempio precedente vengono scritte le righe seguenti nella finestra di **debug** :  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 La variabile oggetto `num` fa riferimento ai dati di tipo `Integer`e `frm` fa riferimento a un oggetto della classe <xref:System.Windows.Forms.Form>.  
  
## <a name="object-arrays"></a>Matrici di oggetti  
 È possibile dichiarare e utilizzare una matrice di variabili di `Object`. Questa operazione è utile quando è necessario gestire un'ampia gamma di tipi di dati e classi di oggetti. Tutti gli elementi di una matrice devono avere lo stesso tipo di dati dichiarato. Dichiarando questo tipo di dati come `Object`, è possibile archiviare gli oggetti e le istanze di classe insieme ad altri tipi di dati nella matrice.  
  
## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Procedura: fare riferimento all'istanza corrente di un oggetto](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Procedura: determinare a quale tipo fa riferimento una variabile oggetto](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [Procedura: determinare se due oggetti sono correlati](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Procedura: determinare se due oggetti sono identici](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)

---
title: Valori di variabili oggetto
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: 1dd3e8cd68086fe116daf0678a1a19881f1ae9c3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410348"
---
# <a name="object-variable-values-visual-basic"></a>Valori di variabili oggetto (Visual Basic)
Una variabile del [tipo di dati Object](../../../language-reference/data-types/object-data-type.md) può fare riferimento a dati di qualsiasi tipo. Il valore archiviato in una `Object` variabile viene mantenuto altrove in memoria, mentre la variabile stessa mantiene un puntatore ai dati.  
  
## <a name="object-classifier-functions"></a>Funzioni di classificazione oggetti  
 Visual Basic fornisce funzioni che restituiscono informazioni sul `Object` riferimento a una variabile, come illustrato nella tabella seguente.  
  
|Funzione|Restituisce true se la variabile oggetto fa riferimento a|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Matrice di valori, anziché un singolo valore.|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Valore del [tipo di dati date](../../../language-reference/data-types/date-data-type.md) oppure stringa che può essere interpretata come valore di data e ora|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Oggetto di tipo <xref:System.DBNull> , che rappresenta dati mancanti o inesistenti|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Oggetto eccezione, che deriva da<xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Niente](../../../language-reference/nothing.md), ovvero nessun oggetto è attualmente assegnato alla variabile|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Un numero o una stringa che può essere interpretata come numero|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Un tipo di riferimento (ad esempio una stringa, una matrice, un delegato o un tipo di classe)|  
  
 È possibile utilizzare queste funzioni per evitare di inviare un valore non valido a un'operazione o a una routine.  
  
## <a name="typeof-operator"></a>Operatore TypeOf  
 È anche possibile usare l' [operatore typeof](../../../language-reference/operators/typeof-operator.md) per determinare se una variabile oggetto si riferisce attualmente a un tipo di dati specifico. L' `TypeOf` espressione... `Is` restituisce `True` se il tipo in fase di esecuzione dell'operando è derivato da o implementa il tipo specificato.  
  
 Nell'esempio seguente vengono utilizzate le `TypeOf` variabili oggetto che fanno riferimento ai tipi di valore e di riferimento.  
  
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
  
 La variabile oggetto `num` fa riferimento a dati di tipo `Integer` e `frm` fa riferimento a un oggetto della classe <xref:System.Windows.Forms.Form> .  
  
## <a name="object-arrays"></a>Matrici di oggetti  
 È possibile dichiarare e utilizzare una matrice di `Object` variabili. Questa operazione è utile quando è necessario gestire un'ampia gamma di tipi di dati e classi di oggetti. Tutti gli elementi di una matrice devono avere lo stesso tipo di dati dichiarato. La dichiarazione di questo tipo di dati `Object` consente di archiviare oggetti e istanze di classe insieme ad altri tipi di dati nella matrice.  
  
## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](object-variables.md)
- [Dichiarazione di variabili oggetto](object-variable-declaration.md)
- [Assegnazione di variabili oggetto](object-variable-assignment.md)
- [Procedura: fare riferimento all'istanza corrente di un oggetto](how-to-refer-to-the-current-instance-of-an-object.md)
- [Procedura: determinare a quale tipo fa riferimento una variabile oggetto](how-to-determine-what-type-an-object-variable-refers-to.md)
- [Procedura: determinare se due oggetti sono correlati](how-to-determine-whether-two-objects-are-related.md)
- [Procedura: determinare se due oggetti sono identici](how-to-determine-whether-two-objects-are-identical.md)
- [Tipi di dati](../data-types/index.md)

---
title: Operatori condizionali Null (C# e Visual Basic)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6118956a5681ddbeb110f6e01f090b85cdd65089
ms.openlocfilehash: 465a395a33c027132b7890e02d540438096e2073
ms.contentlocale: it-it
ms.lasthandoff: 09/25/2017

---
# <a name="null-conditional-operators-c-and-visual-basic"></a>Operatori condizionali Null (C# e Visual Basic)
Vengono usati per verificare la presenza di valori Null prima di eseguire un'operazione di accesso ai membri (`?.`) o di indice (`?[`).  Questi operatori consentono di scrivere meno codice per gestire i controlli null, soprattutto per l'ordinamento decrescente delle strutture di dati.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 Nell'ultimo esempio viene dimostrato che gli operatori con condizione Null causano un corto circuito.  Se un'operazione in una catena di operazioni condizionali di indice e accesso ai membri restituisce Null, l'esecuzione delle altre operazioni della catena viene interrotta.  L'esecuzione di altre operazioni con precedenza inferiore nell'espressione invece può continuare.  Ad esempio, nel codice seguente `E` viene eseguita nella seconda riga e le operazioni `??` e `==` vengono eseguite.  Nella prima riga `??` restituisce un corto circuito e `E` non viene eseguita quando il lato sinistro restituisce un valore non Null.
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 L'accesso ai membri con condizione Null viene usato anche per richiamare delegati in modo thread-safe scrivendo molto meno codice.  In passato era necessario codice simile al seguente:  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 Ora tutto è molto più semplice:  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 Il codice creato in questo modo è thread-safe perché il compilatore genera il codice per valutare `PropertyChanged` una sola volta, mantenendo il risultato in una variabile temporanea.  
  
 È necessario chiamare esplicitamente il metodo `Invoke` perché non esiste una sintassi di chiamata dei delegati con condizione Null `PropertyChanged?(e)`.  In precedenza esistevano troppe situazioni di analisi ambigue che lo consentivano.  
  
## <a name="language-specifications"></a>Specifiche del linguaggio  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 Per altre informazioni, vedere [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## <a name="see-also"></a>Vedere anche  
 [?? (null-coalescing operator)](null-conditional-operator.md)  ?? (operatore null-coalescing)  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Guida per programmatori Visual Basic](../../../visual-basic/programming-guide/index.md)


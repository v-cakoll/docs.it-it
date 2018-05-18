---
title: readonly (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: c6071e7a3c3bfcc96c57ecb34632a911835685fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="readonly-c-reference"></a>readonly (Riferimenti per C#)
La parola chiave `readonly` è un modificatore utilizzabile nei campi. Quando una dichiarazione di campo include un modificatore `readonly`, le assegnazioni ai campi introdotte dalla dichiarazione possono verificarsi solo come parte della dichiarazione o in un costruttore della stessa classe.  
  
## <a name="readonly-field-example"></a>Esempio di campo di sola lettura  
 In questo esempio, il valore del campo `year` non può essere modificato nel metodo `ChangeYear`, anche se gli viene assegnato un valore nel costruttore della classe:  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:  
  
-   Quando la variabile viene inizializzata nella dichiarazione, ad esempio:  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   Per un campo di istanza, nei costruttori di istanza della classe che contiene la dichiarazione del campo, o per un campo statico, nel costruttore statico della classe che contiene la dichiarazione del campo. Questi sono anche gli unici contesti in cui è possibile passare un campo `readonly` come parametro [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) o [ref](../../../csharp/language-reference/keywords/ref.md).  
  
> [!NOTE]
>  La parola chiave `readonly` è diversa dalla parola chiave [const](../../../csharp/language-reference/keywords/const.md). Un campo `const` può essere inizializzato solo nella dichiarazione del campo. Un campo `readonly` può essere inizializzato nella dichiarazione o in un costruttore. I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato. Inoltre, mentre un campo `const` rappresenta una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nell'esempio seguente:  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="comparing-readonly-and-non-readonly-instance-fields"></a>Confronto tra i campi readonly e non readonly  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 Nell'esempio precedente, se si usa un'istruzione simile alla seguente:  
  
 `p2.y = 66;        // Error`  
  
 si otterrà il messaggio di errore del compilatore:  
  
 `The left-hand side of an assignment must be an l-value`  
  
 ovvero lo stesso errore che si ottiene quando si tenta di assegnare un valore a una costante.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)  
 [const](../../../csharp/language-reference/keywords/const.md)  
 [Campi](../../../csharp/programming-guide/classes-and-structs/fields.md)

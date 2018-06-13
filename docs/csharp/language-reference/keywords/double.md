---
title: double (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: 3683b51dfd0ef653ab8bfff6705b96a37e21a10a
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172516"
---
# <a name="double-c-reference"></a>double (Riferimenti per C#)
La parola chiave `double` indica un tipo semplice che archivia valori a virgola mobile a 64 bit. Nella tabella riportata di seguito sono indicati l'intervallo approssimativo e il grado di precisione del tipo `double`.  
  
|Tipo|Intervallo approssimativo|Precisione|Tipo .NET Framework|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup>|15-16 cifre|<xref:System.Double?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Valori letterali  
 Per impostazione predefinita, un valore letterale numerico reale a destra dell'operatore di assegnazione viene gestito come tipo `double`. Se invece un numero intero deve essere trattato come `double`, usare il suffisso d o D, ad esempio:  
  
```csharp  
double x = 3D;  
```  
  
## <a name="conversions"></a>Conversioni  
 In una stessa espressione è possibile combinare tipi integrali numerici e tipi a virgola mobile. In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile. La valutazione dell'espressione viene eseguita in base alle regole seguenti:  
  
-   Se uno dei tipi a virgola mobile è `double`, l'espressione restituirà un valore `double` o [bool](../../../csharp/language-reference/keywords/bool.md) in caso di espressioni relazionali o booleane.  
  
-   Se l'espressione non contiene alcun tipo `double` restituirà un valore [float](../../../csharp/language-reference/keywords/float.md) o [bool](../../../csharp/language-reference/keywords/bool.md) in caso di espressioni relazionali o booleane.  
  
 Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:  
  
-   Zero positivo e negativo.  
  
-   Infinito positivo e negativo.  
  
-   Non un numero (NaN).  
  
-   Insieme finito di valori diversi da zero.  
  
 Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](http://www.ieee.org).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, i valori [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md), e `double` vengono sommati per restituire un risultato `double`.  
  
 [!code-csharp[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md)  
 [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabella dei tipi a virgola mobile](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
 [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

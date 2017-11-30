---
title: short (Riferimenti per C#)
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords: short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8ca3c5444c4fa7a49b7169be3e2a5b15d1a72207
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="short-c-reference"></a>short (Riferimenti per C#)

`short` denota un tipo di dati integrale che archivia valori in base alla dimensione e all'intervallo illustrato nella tabella seguente.  
  
|Tipo|Intervallo|Dimensioni|Tipo .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`short`|Da –32,768 a 32,767|Valore intero a 16 bit con segno|<xref:System.Int16?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Valori letterali  

È possibile dichiarare e inizializzare una variabile `short` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7) un valore letterale binario.  Se il valore letterale integer è esterno all'intervallo di `short`, vale a dire se è minore di <xref:System.Int16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione. 

Nell'esempio seguente, i valori interi uguali a 1,034 rappresentati come valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](../../../csharp/language-reference/keywords/int.md) a valori `short`.  
  
[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]  

> [!NOTE] 
> Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario. I valori letterali decimali non hanno prefissi.

A partire da c# 7, alcune funzionalità sono state aggiunte migliorare la leggibilità. 
 - C# 7.0 consente l'utilizzo dei caratteri di sottolineatura, `_`, come un separatore di cifre.
 - Consente di c# 7.2 `_` da utilizzare come separatore di cifre per un valore letterale binario o esadecimale, dopo il prefisso. Un valore letterale decimale non è consentito utilizzare un carattere di sottolineatura.

Di seguito sono illustrati alcuni esempi.

[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]  
 
## <a name="compiler-overload-resolution"></a>Risoluzione dell'overload del compilatore

 È necessario usare un cast quando si chiamano metodi di overload. Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `short` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 L'uso del cast `short` garantisce che venga chiamato il tipo corretto, ad esempio:  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a>Conversioni  

 Si verifica una conversione implicita predefinita da `short` a [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Non è possibile convertire in modo implicito tipi numerici non letterali che necessitano di maggiore spazio in memoria in `short`. Per informazioni sullo spazio necessario per l'archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md). Considerare, ad esempio, le due variabili `short` seguenti, `x` e `y`:  
  
```csharp  
short x = 5, y = 12;  
```  
  
 L'istruzione di assegnazione seguente genera un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce [int](../../../csharp/language-reference/keywords/int.md) per impostazione predefinita.  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 Per risolvere il problema, usare un cast:  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 È anche possibile usare le istruzioni seguenti dove la variabile di destinazione ha la stessa dimensione di archiviazione o una dimensione maggiore:  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 Non è disponibile nessuna conversione implicita dai tipi a virgola mobile a `short`. Ad esempio, l'istruzione seguente genera un errore del compilatore, a meno che non venga usato un cast esplicito:  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).  
  
 Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Int16>  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

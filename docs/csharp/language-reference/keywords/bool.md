---
title: bool (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 1045a459491b0d0d6a84c60f6e820297b47efd5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215967"
---
# <a name="bool-c-reference"></a>bool (Riferimenti per C#)
La parola chiave `bool` è un alias per <xref:System.Boolean?displayProperty=nameWithType>. Viene usata per dichiarare le variabili che archiviano i valori booleani, [true](../../../csharp/language-reference/keywords/true.md) e [false](../../../csharp/language-reference/keywords/false.md).  
  
> [!NOTE]
>  Se è necessaria una variabile booleana che può anche avere un valore di `null`, usare `bool?`. Per altre informazioni, vedere [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).  
  
## <a name="literals"></a>Valori letterali  
 È possibile assegnare un valore booleano a una variabile `bool`. È possibile anche assegnare un'espressione che restituisce `bool` per una variabile `bool`.  
  
 [!code-csharp[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]  
  
 Il valore predefinito di una variabile `bool` è `false`. Il valore predefinito di una variabile `bool?` è `null`.  
  
## <a name="conversions"></a>Conversioni  
 In C++, un valore di tipo `bool` può essere convertito in un valore di tipo `int`; in altre parole, `false` equivale a zero e `true` equivale a valori diversi da zero. In C#, non c'è nessuna conversione tra il tipo `bool` e altri tipi. Ad esempio, l'istruzione `if` seguente non è valida in C#:  
  
 [!code-csharp[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]  
  
 Per testare una variabile del tipo `int`, è necessario confrontarla esplicitamente con un valore, ad esempio zero, come indicato di seguito:  
  
 [!code-csharp[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]  
  
## <a name="example"></a>Esempio  
 In questo esempio si immette un carattere dalla tastiera e il programma controlla se il carattere di input è una lettera. Se è una lettera, controlla se è maiuscola o minuscola. Questi controlli vengono eseguiti con <xref:System.Char.IsLetter%2A> e <xref:System.Char.IsLower%2A>, che restituiscono entrambi il tipo `bool`:  
  
 [!code-csharp[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

---
title: Parola chiave decimal (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
ms.openlocfilehash: c9d40238ca4c34238d5663185f93afbce73195cf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506519"
---
# <a name="decimal-c-reference"></a>decimal (Riferimenti per C#)

La parola chiave `decimal` indica un tipo di dati a 128 bit. Rispetto ad altri tipi a virgola mobile, il tipo `decimal` è caratterizzato da una maggiore precisione e da un intervallo minore, che lo rendono appropriato per calcoli finanziari e monetari. Nella tabella riportata di seguito vengono indicati l'intervallo approssimativo e il grado di precisione del tipo `decimal`.

|Tipo|Intervallo approssimativo|Precisione|Tipo .NET|
|----------|-----------------------|---------------|-------------------------|
|`decimal`|Compreso tra ±1.0 x 10<sup>-28</sup> e ±7.9228 x 10<sup>28</sup>|28-29 cifre significative|<xref:System.Decimal?displayProperty=nameWithType>|

Il valore predefinito di un `decimal` è 0m.

## <a name="literals"></a>Valori letterali

Se si desidera che un valore letterale numerico reale venga gestito come `decimal`, utilizzare il suffisso m o M, ad esempio:

```csharp
decimal myMoney = 300.5m;
```

Senza il suffisso m, il numero viene gestito come valore [double](../../../csharp/language-reference/keywords/double.md) e genera un errore del compilatore.

## <a name="conversions"></a>Conversioni

I tipi integrali vengono convertiti in modo implicito in `decimal` e il risultato restituisce `decimal`. È pertanto possibile inizializzare una variabile decimale mediante un valore letterale Integer, senza il suffisso, ad esempio:

```csharp
decimal myMoney = 300;
```

Poiché non esiste alcuna conversione implicita tra altri tipi a virgola mobile e il tipo `decimal`, è necessario usare un cast per eseguire una conversione tra questi due tipi. Ad esempio:

```csharp
decimal myMoney = 99.9m;
double x = (double)myMoney;
myMoney = (decimal)x;
```

È inoltre possibile combinare tipi `decimal` e tipi integrali numerici nella stessa espressione. Tuttavia, la combinazione di `decimal` e altri tipi a virgola mobile senza un cast genera un errore di compilazione.

Per altre informazioni sulle conversioni numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).

Per altre informazioni sulle conversioni numeriche esplicite, vedere [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).

## <a name="formatting-decimal-output"></a>Formattazione dell'output di tipo decimal

È possibile applicare il formato desiderato ai risultati utilizzando il metodo `String.Format` o mediante il metodo <xref:System.Console.Write%2A?displayProperty=nameWithType> che chiama `String.Format()`. Il formato valuta viene specificato tramite la stringa di formato valuta standard "C" o "c", come illustrato nel secondo esempio riportato più avanti. Per ulteriori informazioni sul metodo `String.Format`, vedere <xref:System.String.Format%2A?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

L'esempio seguente causa un errore del compilatore tentando di aggiungere le variabili [double](../../../csharp/language-reference/keywords/double.md) e `decimal`.

```csharp
decimal dec = 0m;
double dub = 9;
// The following line causes an error that reads "Operator '+' cannot be applied to
// operands of type 'double' and 'decimal'"
Console.WriteLine(dec + dub);

// You can fix the error by using explicit casting of either operand.
Console.WriteLine(dec + (decimal)dub);
Console.WriteLine((double)dec + dub);
```

Viene restituito l'errore seguente:

`Operator '+' cannot be applied to operands of type 'double' and 'decimal'`

In questo esempio `decimal` e [int](../../../csharp/language-reference/keywords/int.md) sono combinate nella stessa espressione. Il risultato restituisce il tipo `decimal`.

[!code-csharp[csrefKeywordsTypes#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#6)]

## <a name="example"></a>Esempio

In questo esempio l'output viene formattato mediante la stringa del formato valuta (in dollari). Si noti che `x` viene arrotondato perché le cifre decimali sono superiori a $ 0,99. La variabile `y`, che rappresenta le cifre a precisione massima, viene invece visualizzata nel formato esatto.

[!code-csharp[csrefKeywordsTypes#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#7)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Decimal>  
- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md)
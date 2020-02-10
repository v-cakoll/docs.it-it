---
title: Tipi numerici a virgola mobile - Riferimenti per C#
description: Panoramica dei tipi a virgola mobile incorporati di C#
ms.date: 10/22/2019
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 9c8b11f9337ee9de90f2d4d96b5be162713bfcbd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093214"
---
# <a name="floating-point-numeric-types-c-reference"></a>Tipi numerici a virgola mobile (riferimenti per C#)

I *tipi numerici a virgola mobile* rappresentano i numeri reali. Tutti i tipi numerici a virgola mobile sono [tipi di valore](value-types.md). Sono anche [tipi semplici](value-types.md#built-in-value-types) e possono essere inizializzati con [valori letterali](#real-literals). Tutti i tipi numerici a virgola mobile supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), di [confronto](../operators/comparison-operators.md)e di [uguaglianza](../operators/equality-operators.md) .

## <a name="characteristics-of-the-floating-point-types"></a>Caratteristiche dei tipi a virgola mobile

C# supporta i tipi a virgola mobile predefiniti seguenti:
  
|Tipo/parola chiave C#|Intervallo approssimativo|Precision|Dimensione|Tipo .NET|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|Compreso tra ±1.5 x 10<sup>−45</sup> e ±3.4 x 10<sup>38</sup>|~6-9 cifre|4 byte|<xref:System.Single?displayProperty=nameWithType>|
|`double`|Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup>|~15-17 cifre|8 byte|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|Compreso tra ±1.0 x 10<sup>-28</sup> e ±7.9228 x 10<sup>28</sup>|28-29 cifre|16 byte|<xref:System.Decimal?displayProperty=nameWithType>|

Nella tabella precedente ogni tipo/parola chiave C# nella colonna più a sinistra è un alias per il tipo .NET corrispondente. Sono intercambiabili. Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:

```csharp
double a = 12.3;
System.Double b = 12.3;
```

Il valore predefinito di ogni tipo a virgola mobile è zero `0`. Ogni tipo a virgola mobile ha costanti `MinValue` e `MaxValue` che specificano il valore finito minimo e massimo del tipo. I tipi `float` e `double` forniscono anche costanti che rappresentano valori Not-a-Number (NaN) e infiniti. Ad esempio, il tipo `double` fornisce le costanti seguenti: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> e <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.

Dato che il tipo `decimal` è caratterizzato da una maggiore precisione e da un intervallo più piccolo rispetto a `float` e `double`, è appropriato per calcoli finanziari e monetari.

In un'espressione è possibile combinare tipi [integrali](integral-numeric-types.md) e tipi a virgola mobile. In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile. La valutazione dell'espressione viene eseguita in base alle regole seguenti:

- Se uno dei tipi a virgola mobile è `double`, l'espressione restituisce `double`o a [bool](bool.md) nei confronti relazionali e di uguaglianza.
- Se non è presente alcun tipo di `double` nell'espressione, l'espressione restituisce `float`o a [bool](bool.md) nei confronti relazionali e di uguaglianza.

Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:

- Zero positivo e negativo
- Infinito positivo e negativo
- Non un numero
- Insieme finito di valori diversi da zero

Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](https://www.ieee.org).

È possibile usare [stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md) oppure [stringhe di formato numerico personalizzato](../../../standard/base-types/custom-numeric-format-strings.md) per formattare un valore a virgola mobile.

## <a name="real-literals"></a>Valori letterali reali

Il tipo di un valore letterale reale è determinato dal suffisso, come indicato di seguito:

- Il valore letterale senza suffisso o con il suffisso `d` o `D` è di tipo `double`
- Il valore letterale con il suffisso `f` o `F` è di tipo `float`
- Il valore letterale con il suffisso `m` o `M` è di tipo `decimal`

Il codice seguente illustra un esempio di ogni:

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

Nell'esempio precedente viene inoltre illustrato l'utilizzo di `_` come *separatore di cifre*, supportato a partire C# da 7,0. È possibile usare il separatore di cifre con tutti i tipi di valori letterali numerici.

È anche possibile usare la notazione scientifica, ovvero specificare una parte dell'esponente di un valore letterale reale, come illustrato nell'esempio seguente:

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a>Conversioni

Esiste una sola conversione implicita tra tipi numerici a virgola mobile: da `float` a `double`. Tuttavia, è possibile convertire qualsiasi tipo a virgola mobile in qualsiasi altro tipo a virgola mobile con il [cast esplicito](../operators/type-testing-and-cast.md#cast-operator-). Per altre informazioni, vedere [conversioni numeriche predefinite](numeric-conversions.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Tipi a virgola mobile](~/_csharplang/spec/types.md#floating-point-types)
- [Tipo decimale](~/_csharplang/spec/types.md#the-decimal-type)
- [Valori letterali reali](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Tipi di valore](value-types.md)
- [Tipi integrali](integral-numeric-types.md)
- [Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md)
- [Dati numerici in .NET](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>

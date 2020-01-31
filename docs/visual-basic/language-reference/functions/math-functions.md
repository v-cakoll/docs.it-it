---
title: Funzioni matematiche
ms.date: 01/27/2020
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: ea30ae3b30484c1a13d6d540f121c03afb30ba26
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794601"
---
# <a name="math-functions-visual-basic"></a>Funzioni matematiche (Visual Basic)

I metodi della classe <xref:System.Math?displayProperty=nameWithType> offrono funzioni trigonometriche, logaritmiche e altre funzioni matematiche comuni.

## <a name="remarks"></a>Note

Nella tabella seguente sono elencati i metodi della classe <xref:System.Math?displayProperty=nameWithType>. È possibile usarli in un programma Visual Basic:
  
|Metodo .NET|Descrizione|
|---------------------------|-----------------|
|<xref:System.Math.Abs%2A>|Viene restituito il valore assoluto di un numero.|
|<xref:System.Math.Acos%2A>|Restituisce l'angolo il cui coseno è il numero specificato.|
|<xref:System.Math.Asin%2A>|Restituisce l'angolo il cui seno è il numero specificato.|
|<xref:System.Math.Atan%2A>|Restituisce l'angolo la cui tangente è il numero specificato.|
|<xref:System.Math.Atan2%2A>|Restituisce l'angolo la cui tangente è il quoziente di due numeri specificati.|
|<xref:System.Math.BigMul%2A>|Restituisce il prodotto completo dei numeri a 2 32 bit.|
|<xref:System.Math.Ceiling%2A>|Restituisce il valore integrale minimo maggiore o uguale al `Decimal` o `Double`specificato.|
|<xref:System.Math.Cos%2A>|Restituisce il coseno dell'angolo specificato.|
|<xref:System.Math.Cosh%2A>|Restituisce il coseno iperbolico dell'angolo specificato.|
|<xref:System.Math.DivRem%2A>|Restituisce il quoziente di interi con segno a 2 32 bit o a 64 bit e restituisce anche il resto in un parametro di output.|
|<xref:System.Math.Exp%2A>|Restituisce e (la base dei logaritmi naturali) elevato alla potenza specificata.|
|<xref:System.Math.Floor%2A>|Restituisce l'intero più grande che è minore o uguale all'`Decimal` o al numero di `Double` specificato.|
|<xref:System.Math.IEEERemainder%2A>|Restituisce il resto risultante dalla divisione di un numero specificato per un altro numero specificato.|
|<xref:System.Math.Log%2A>|Restituisce il logaritmo naturale (base e) di un numero specificato o il logaritmo di un numero specificato in una base specificata.|
|<xref:System.Math.Log10%2A>|Restituisce il logaritmo in base 10 del numero specificato.|
|<xref:System.Math.Max%2A>|Restituisce il più elevato tra due numeri.|
|<xref:System.Math.Min%2A>|Restituisce il meno elevato tra due numeri.|
|<xref:System.Math.Pow%2A>|Restituisce il numero specificato elevato alla potenza specificata.|
|<xref:System.Math.Round%2A>|Restituisce un valore `Decimal` o `Double` arrotondato al valore integrale più vicino o a un numero specificato di cifre frazionarie.|
|<xref:System.Math.Sign%2A>|Restituisce un valore `Integer` che indica il segno di un numero.|
|<xref:System.Math.Sin%2A>|Restituisce il seno dell'angolo specificato.|
|<xref:System.Math.Sinh%2A>|Restituisce il seno iperbolico dell'angolo specificato.|
|<xref:System.Math.Sqrt%2A>|Restituisce la radice quadrata del numero specificato.|
|<xref:System.Math.Tan%2A>|Restituisce la tangente dell'angolo specificato.|
|<xref:System.Math.Tanh%2A>|Restituisce la tangente iperbolica dell'angolo specificato.|
|<xref:System.Math.Truncate%2A>|Calcola la parte integrale di un `Decimal` o di un numero di `Double` specificato.|

La tabella seguente elenca i metodi della classe <xref:System.Math?displayProperty=nameWithType> che non esistono in .NET Framework ma che vengono aggiunti in .NET Standard o .NET Core:

|Metodo .NET|Descrizione|Disponibile in|
|---------------------------|-----------------|-----------|
|<xref:System.Math.Acosh%2A>|Restituisce l'angolo il cui coseno iperbolico è il numero specificato.|A partire da .NET Core 2,1 e .NET Standard 2,1|
|<xref:System.Math.Asinh%2A>|Restituisce l'angolo il cui seno iperbolico è il numero specificato.|A partire da .NET Core 2,1 e .NET Standard 2,1|
|<xref:System.Math.Atanh%2A>|Restituisce l'angolo la cui tangente iperbolica è il numero specificato.|A partire da .NET Core 2,1 e .NET Standard 2,1|
|<xref:System.Math.BitDecrement%2A>|Restituisce il successivo valore più piccolo che risulta minore di `x`.|A partire da .NET Core 3,0|
|<xref:System.Math.BitIncrement%2A>|Restituisce il successivo valore più grande che risulta maggiore di `x`.|A partire da .NET Core 3,0|
|<xref:System.Math.Cbrt%2A>|Restituisce la radice cubica di un numero specificato.|A partire da .NET Core 2,1 e .NET Standard 2,1|
|<xref:System.Math.Clamp%2A>|Restituisce il valore `value` fissato all'intervallo inclusivo di `min` e `max`.|A partire da .NET Core 2,0 e .NET Standard 2,1|
|<xref:System.Math.CopySign%2A>|Restituisce un valore con grandezza pari a `x` e segno `y`.|A partire da .NET Core 3,0|
|<xref:System.Math.FusedMultiplyAdd%2A>|Restituisce (x \* y) + z, arrotondato come un'operazione ternaria.|A partire da .NET Core 3,0|
|<xref:System.Math.ILogB%2A>|Restituisce la parte intera del logaritmo in base 2 del numero specificato.|A partire da .NET Core 3,0|
|<xref:System.Math.Log2%2A>|Restituisce il logaritmo in base 2 di un numero specificato.|A partire da .NET Core 3,0|
|<xref:System.Math.MaxMagnitude%2A>|Restituisce la grandezza più elevata tra due numeri a virgola mobile e precisione doppia.|A partire da .NET Core 3,0|
|<xref:System.Math.MinMagnitude%2A>|Restituisce la grandezza meno elevata tra due numeri a virgola mobile e precisione doppia.|A partire da .NET Core 3,0|
|<xref:System.Math.ScaleB%2A>|Restituisce x \* 2 ^ n calcolato in modo efficiente.|A partire da .NET Core 3,0|

Per usare queste funzioni senza qualificazione, importare lo spazio dei nomi <xref:System.Math?displayProperty=nameWithType> nel progetto aggiungendo il codice seguente all'inizio del file di origine:

```vb
Imports System.Math
```

## <a name="example---abs"></a>Esempio-ABS

In questo esempio viene usato il metodo <xref:System.Math.Abs%2A> della classe <xref:System.Math> per calcolare il valore assoluto di un numero.

```vb
Dim x As Double = Math.Abs(50.3)
Dim y As Double = Math.Abs(-50.3)
Console.WriteLine(x)
Console.WriteLine(y)
' This example produces the following output:
' 50.3
' 50.3
```  

## <a name="example---atan"></a>Esempio: atan

In questo esempio viene usato il metodo <xref:System.Math.Atan%2A> della classe <xref:System.Math> per calcolare il valore di pi greco.

```vb
Public Function GetPi() As Double
    ' Calculate the value of pi.
    Return 4.0 * Math.Atan(1.0)
End Function
```

> [!NOTE]
> La classe <xref:System.Math?displayProperty=nameWithType> contiene <xref:System.Math.PI?displayProperty=nameWithType> campo costante. È possibile usarlo anziché calcolarlo.

## <a name="example---cos"></a>Esempio-cos

In questo esempio viene usato il metodo <xref:System.Math.Cos%2A> della classe <xref:System.Math> per restituire il coseno di un angolo.

```vb
Public Function Sec(angle As Double) As Double
    ' Calculate the secant of angle, in radians.
    Return 1.0 / Math.Cos(angle)
End Function
```

## <a name="example---exp"></a>Esempio: Exp

In questo esempio viene usato il metodo <xref:System.Math.Exp%2A> della classe <xref:System.Math> per restituire e elevato a una potenza.

```vb
Public Function Sinh(angle As Double) As Double
    ' Calculate hyperbolic sine of an angle, in radians.
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0
End Function
```

## <a name="example---log"></a>Esempio-log

In questo esempio viene usato il metodo <xref:System.Math.Log%2A> della classe <xref:System.Math> per restituire il logaritmo naturale di un numero.

```vb
Public Function Asinh(value As Double) As Double
    ' Calculate inverse hyperbolic sine, in radians.
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))
End Function
```

## <a name="example---round"></a>Esempio-round

In questo esempio viene usato il metodo <xref:System.Math.Round%2A> della classe <xref:System.Math> per arrotondare un numero all'intero più vicino.

```vb
Dim myVar2 As Double = Math.Round(2.8)
Console.WriteLine(myVar2)
' The code produces the following output:
' 3
```

## <a name="example---sign"></a>Esempio-firma

In questo esempio viene usato il metodo <xref:System.Math.Sign%2A> della classe <xref:System.Math> per determinare il segno di un numero.

```vb
Dim mySign1 As Integer = Math.Sign(12)
Dim mySign2 As Integer = Math.Sign(-2.4)
Dim mySign3 As Integer = Math.Sign(0)
Console.WriteLine(mySign1)
Console.WriteLine(mySign2)
Console.WriteLine(mySign3)
' The code produces the following output:
' 1
' -1
' 0
```

## <a name="example---sin"></a>Esempio-sin

In questo esempio viene usato il metodo <xref:System.Math.Sin%2A> della classe <xref:System.Math> per restituire il seno di un angolo.

```vb
Public Function Csc(angle As Double) As Double
    ' Calculate cosecant of an angle, in radians.
    Return 1.0 / Math.Sin(angle)
End Function
```

## <a name="example---sqrt"></a>Esempio-sqrt

In questo esempio viene usato il metodo <xref:System.Math.Sqrt%2A> della classe <xref:System.Math> per calcolare la radice quadrata di un numero.

```vb
Dim mySqrt1 As Double = Math.Sqrt(4)
Dim mySqrt2 As Double = Math.Sqrt(23)
Dim mySqrt3 As Double = Math.Sqrt(0)
Dim mySqrt4 As Double = Math.Sqrt(-4)
Console.WriteLine(mySqrt1)
Console.WriteLine(mySqrt2)
Console.WriteLine(mySqrt3)
Console.WriteLine(mySqrt4)
' The code produces the following output:
' 2
' 4.79583152331272
' 0
' NaN
```

## <a name="example---tan"></a>Esempio-Tan

In questo esempio viene usato il metodo <xref:System.Math.Tan%2A> della classe <xref:System.Math> per restituire la tangente di un angolo.

```vb
Public Function Ctan(angle As Double) As Double
    ' Calculate cotangent of an angle, in radians.
    Return 1.0 / Math.Tan(angle)
End Function
```

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>
- <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>
- <xref:System.Double.NaN>
- [Funzioni matematiche derivate](../keywords/derived-math-functions.md)
- [Operatori aritmetici](../operators/arithmetic-operators.md)

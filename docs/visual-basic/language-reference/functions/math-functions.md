---
title: Funzioni matematiche
ms.date: 07/20/2015
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: b1cd6a846a7dc1dddcf6bdb5eb99ebc1c57a012c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348071"
---
# <a name="math-functions-visual-basic"></a>Funzioni matematiche (Visual Basic)
I metodi della classe <xref:System.Math?displayProperty=nameWithType> offrono funzioni trigonometriche, logaritmiche e altre funzioni matematiche comuni.  
  
## <a name="remarks"></a>Note  
 Nella tabella seguente sono elencati i metodi della classe <xref:System.Math?displayProperty=nameWithType>. È possibile usarli in un programma Visual Basic.  
  
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
  
 Per usare queste funzioni senza qualificazione, importare lo spazio dei nomi <xref:System.Math?displayProperty=nameWithType> nel progetto aggiungendo il codice seguente all'inizio del file di origine:  
  
```vb
Imports System.Math  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Abs%2A> della classe <xref:System.Math> per calcolare il valore assoluto di un numero.  
  
```vb
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Atan%2A> della classe <xref:System.Math> per calcolare il valore di pi greco.  
  
```vb
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Cos%2A> della classe <xref:System.Math> per restituire il coseno di un angolo.  
  
```vb
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Exp%2A> della classe <xref:System.Math> per restituire e elevato a una potenza.  
  
```vb
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Log%2A> della classe <xref:System.Math> per restituire il logaritmo naturale di un numero.  
  
```vb
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Round%2A> della classe <xref:System.Math> per arrotondare un numero all'intero più vicino.  
  
```vb
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Sign%2A> della classe <xref:System.Math> per determinare il segno di un numero.  
  
```vb
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Sin%2A> della classe <xref:System.Math> per restituire il seno di un angolo.  
  
```vb
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Sqrt%2A> della classe <xref:System.Math> per calcolare la radice quadrata di un numero.  
  
```vb
' Returns 2.  
Dim MySqr1 As Double = Math.Sqrt(4)  
' Returns 4.79583152331272.  
Dim MySqr2 As Double = Math.Sqrt(23)  
' Returns 0.  
Dim MySqr3 As Double = Math.Sqrt(0)  
' Returns NaN (not a number).  
Dim MySqr4 As Double = Math.Sqrt(-4)  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Math.Tan%2A> della classe <xref:System.Math> per restituire la tangente di un angolo.  
  
```vb
Public Function Ctan(ByVal angle As Double) As Double  
    ' Calculate cotangent of an angle, in radians.  
    Return 1.0 / Math.Tan(angle)  
End Function  
```  
  
## <a name="requirements"></a>Requisiti  
 **Classe:** <xref:System.Math>  
  
 **Spazio dei nomi:** <xref:System>  
  
 **Assembly:** mscorlib (in mscorlib. dll)  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>
- <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>
- <xref:System.Double.NaN>
- [Funzioni matematiche derivate](../../../visual-basic/language-reference/keywords/derived-math-functions.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)

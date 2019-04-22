---
title: Funzioni matematiche (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: e5f87a8e367e8c9df65b979fea3781b42ee3ce83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824962"
---
# <a name="math-functions-visual-basic"></a>Funzioni matematiche (Visual Basic)
I metodi del <xref:System.Math?displayProperty=nameWithType> classe fornire trigonometriche, logaritmiche e normali funzioni matematiche.  
  
## <a name="remarks"></a>Note  
 La tabella seguente elenca i metodi del <xref:System.Math?displayProperty=nameWithType> classe. È possibile usare in un programma Visual Basic.  
  
|Metodo .NET|Descrizione|  
|---------------------------|-----------------|  
|<xref:System.Math.Abs%2A>|Restituisce il valore assoluto di un numero.|  
|<xref:System.Math.Acos%2A>|Restituisce l'angolo il cui coseno è il numero specificato.|  
|<xref:System.Math.Asin%2A>|Restituisce l'angolo il cui seno è il numero specificato.|  
|<xref:System.Math.Atan%2A>|Restituisce l'angolo la cui tangente è il numero specificato.|  
|<xref:System.Math.Atan2%2A>|Restituisce l'angolo la cui tangente è il quoziente di due numeri specificati.|  
|<xref:System.Math.BigMul%2A>|Restituisce il prodotto completo di due numeri a 32 bit.|  
|<xref:System.Math.Ceiling%2A>|Restituisce il valore integrale minimo maggiore o uguale all'oggetto specificato `Decimal` o `Double`.|  
|<xref:System.Math.Cos%2A>|Restituisce il coseno dell'angolo specificato.|  
|<xref:System.Math.Cosh%2A>|Restituisce il coseno iperbolico dell'angolo specificato.|  
|<xref:System.Math.DivRem%2A>|Restituisce il quoziente di due interi con segno a 32 o 64 bit e restituisce la parte rimanente di un parametro di output.|  
|<xref:System.Math.Exp%2A>|Restituisce il numero e (la base dei logaritmi naturali) elevato alla potenza specificata.|  
|<xref:System.Math.Floor%2A>|Restituisce l'intero massimo minore o uguale all'oggetto specificato `Decimal` o `Double` numero.|  
|<xref:System.Math.IEEERemainder%2A>|Restituisce il resto risultante dalla divisione di un numero specificato da un altro numero specificato.|  
|<xref:System.Math.Log%2A>|Restituisce il logaritmo naturale (base e) di un numero specificato o il logaritmo del numero specificato in una base specificata.|  
|<xref:System.Math.Log10%2A>|Restituisce il logaritmo in base 10 del numero specificato.|  
|<xref:System.Math.Max%2A>|Restituisce il più elevato tra due numeri.|  
|<xref:System.Math.Min%2A>|Restituisce il meno elevato tra due numeri.|  
|<xref:System.Math.Pow%2A>|Restituisce il numero specificato elevato alla potenza specificata.|  
|<xref:System.Math.Round%2A>|Restituisce un `Decimal` o `Double` valore arrotondato al valore integrale più vicino o su un numero di cifre frazionarie specificato.|  
|<xref:System.Math.Sign%2A>|Restituisce un `Integer` valore che indica il segno di un numero.|  
|<xref:System.Math.Sin%2A>|Restituisce il seno dell'angolo specificato.|  
|<xref:System.Math.Sinh%2A>|Restituisce il seno iperbolico dell'angolo specificato.|  
|<xref:System.Math.Sqrt%2A>|Restituisce la radice quadrata del numero specificato.|  
|<xref:System.Math.Tan%2A>|Restituisce la tangente dell'angolo specificato.|  
|<xref:System.Math.Tanh%2A>|Restituisce la tangente iperbolica dell'angolo specificato.|  
|<xref:System.Math.Truncate%2A>|Calcola la parte integrale di un oggetto specificato `Decimal` o `Double` numero.|  
  
 Per utilizzare queste funzioni senza qualifica, importare il <xref:System.Math?displayProperty=nameWithType> dello spazio dei nomi nel progetto aggiungendo il codice seguente all'inizio del file di origine:  
  
```vb
Imports System.Math  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Math.Abs%2A> metodo del <xref:System.Math> classe per calcolare il valore assoluto di un numero.  
  
```vb
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Math.Atan%2A> metodo del <xref:System.Math> classe per la quale calcolare il valore di pi greco.  
  
```vb
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Math.Cos%2A> metodo del <xref:System.Math> classe per restituire il coseno di un angolo.  
  
```vb
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Math.Exp%2A> metodo del <xref:System.Math> classe per restituire e elevato alla potenza specificata.  
  
```vb
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Math.Log%2A> metodo del <xref:System.Math> classe per restituire il logaritmo naturale di un numero.  
  
```vb
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Math.Round%2A> metodo del <xref:System.Math> classe per arrotondare un numero intero più vicino.  
  
```vb
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Math.Sign%2A> metodo del <xref:System.Math> classe per determinare il segno di un numero.  
  
```vb
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Math.Sin%2A> metodo del <xref:System.Math> classe per restituire il seno di un angolo.  
  
```vb
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Math.Sqrt%2A> metodo del <xref:System.Math> classe per la quale calcolare la radice quadrata di un numero.  
  
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
 Questo esempio Usa la <xref:System.Math.Tan%2A> metodo del <xref:System.Math> classe per restituire la tangente di un angolo.  
  
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

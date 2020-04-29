---
title: SIMD-tipi con accelerazione in .NET
description: Questo articolo descrive i tipi abilitati per SIMD in .NET e illustra come usare le operazioni di SIMD hardware in C# e .NET.
author: FIVIL
ms.author: tagoo
ms.date: 04/28/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 27263931ff0338e194c8fd3d9ec5ba59bfafd9fe
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507782"
---
# <a name="use-simd-accelerated-numeric-types"></a>Usare i tipi numerici con accelerazione SIMD

SIMD (istruzione singola, più dati) fornisce il supporto hardware per l'esecuzione di un'operazione su più parti di dati, in parallelo, usando una singola istruzione. In .NET è disponibile un <xref:System.Numerics> set di tipi con accelerazione SIMD nello spazio dei nomi. Le operazioni SIMD possono essere eseguite in parallelo a livello hardware. Questo approccio aumenta la velocità effettiva dei calcoli vettorializzati, che sono comuni in app matematiche scientifiche e grafiche.

## <a name="net-simd-accelerated-types"></a>Tipi di SIMD con accelerazione .NET

I tipi .NET SIMD-Accelerated includono i tipi seguenti:

- Tipi <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> e <xref:System.Numerics.Vector4>, che rappresentano i vettori con 2, 3 e 4 valori <xref:System.Single>.

- Due tipi di matrice <xref:System.Numerics.Matrix3x2>,, che rappresenta una matrice 3x2, <xref:System.Numerics.Matrix4x4>e, che rappresenta una matrice 4x4 <xref:System.Single> di valori.

- <xref:System.Numerics.Plane> Tipo, che rappresenta un piano nello spazio tridimensionale usando <xref:System.Single> i valori.

- Il <xref:System.Numerics.Quaternion> tipo, che rappresenta un vettore usato per codificare le rotazioni fisiche tridimensionali usando <xref:System.Single> i valori.

- Tipo <xref:System.Numerics.Vector%601>, che rappresenta un vettore di un tipo numerico specificato e fornisce un ampio set di operatori che traggono vantaggio dal supporto per SIMD. Il numero di un' <xref:System.Numerics.Vector%601> istanza è corretto per la durata di un'applicazione, ma il relativo <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> valore dipende dalla CPU del computer che esegue il codice.

  > [!NOTE]
  > Il <xref:System.Numerics.Vector%601> tipo non è incluso nell'.NET Framework. È necessario installare il pacchetto NuGet [System.Numerics.Vectors](https://www.nuget.org/packages/System.Numerics.Vectors) per ottenere l'accesso a questo tipo.
  
I tipi con accelerazione SIMD vengono implementati in modo che possano essere usati con compilatori JIT o hardware non SIMD. Per sfruttare le istruzioni SIMD, le app a 64 bit devono essere eseguite dal runtime che usa il compilatore **RyuJIT** . Un compilatore **RyuJIT** è incluso in .NET Core e in .NET Framework 4,6 e versioni successive. Il supporto di SIMD viene fornito solo quando è destinato a processori a 64 bit.

## <a name="how-to-use-simd"></a>Come usare SIMD

Prima di eseguire algoritmi SIMD personalizzati, è possibile verificare se il computer host supporta SIMD usando <xref:System.Numerics.Vector.IsHardwareAccelerated?displayProperty=nameWithType>, che restituisce. <xref:System.Boolean> Ciò non garantisce che SIMD-Acceleration sia abilitato per un tipo specifico, ma è un indicatore che è supportato da alcuni tipi.

## <a name="simple-vectors"></a>Vettori semplici

I tipi con accelerazione SIMD più primitivi in .NET sono <xref:System.Numerics.Vector2> <xref:System.Numerics.Vector3>i tipi, <xref:System.Numerics.Vector4> e, che rappresentano i vettori con i valori 2, 3 e <xref:System.Single> 4. Nell'esempio seguente viene <xref:System.Numerics.Vector2> usato per aggiungere due vettori.

```csharp
var v1 = new Vector2(0.1f, 0.2f);
var v2 = new Vector2(1.1f, 2.2f);
var vResutl = v1 + v2;
```

È anche possibile usare i vettori .NET per calcolare altre proprietà matematiche dei vettori, ad esempio `Dot product`, `Transform` `Clamp` e così via.

```csharp
var v1 = new Vector2(0.1f, 0.2f);
var v2 = new Vector2(1.1f, 2.2f);
var vResutl1 = Vector2.Dot(v1, v2);
var vResutl2 = Vector2.Distance(v1, v2);
var vResutl3 = Vector2.Clamp(v1, Vector2.Zero, Vector2.One);
```

## <a name="matrix"></a>Matrice

<xref:System.Numerics.Matrix3x2>, che rappresenta una matrice 3x2, e <xref:System.Numerics.Matrix4x4>, che rappresenta una matrice 4x4. Può essere usato per i calcoli correlati a matrici. Nell'esempio seguente viene illustrata la moltiplicazione di una matrice per la matrice di trasposizione corrispondente utilizzando SIMD.

```csharp
var m1 = new Matrix4x4(
            1.1f, 1.2f, 1.3f, 1.4f,
            2.1f, 2.2f, 3.3f, 4.4f,
            3.1f, 3.2f, 3.3f, 3.4f,
            4.1f, 4.2f, 4.3f, 4.4f);

var m2 = Matrix4x4.Transpose(m1);
var mResult = Matrix4x4.Multiply(m1, m2);
```

## <a name="vectort"></a>Vettore\<T>

<xref:System.Numerics.Vector%601> Offre la possibilità di usare vettori più lunghi. Il conteggio di un' <xref:System.Numerics.Vector%601> istanza è fisso, ma il relativo <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> valore dipende dalla CPU del computer in cui è in esecuzione il codice.

Nell'esempio seguente viene illustrata l'aggiunta di elementi <xref:System.Numerics.Vector%601>di matrici Long tramite.

```csharp
double[] SimdVectorProd(double[] left, double[] right)
{
    var offset = Vector<double>.Count;
    double[] result = new double[left.Length];
    int i = 0;
    for (i = 0; i < left.Length; i += offset)
    {
        var v1 = new Vector<double>(left, i);
        var v2 = new Vector<double>(right, i);
        (v1 * v2).CopyTo(result, i);
    }

    //remaining items
    for (; i < left.Length; ++i)
    {
        result[i] = left[i] * right[i];
    }

    return result;
}
```

## <a name="remarks"></a>Osservazioni

È più probabile che SIMD elimini un collo di bottiglia ed esponga il successivo, ad esempio la velocità effettiva della memoria. In generale, i vantaggi a livello di prestazioni derivanti dall'uso di SIMD variano a seconda dello scenario specifico e in alcuni casi può addirittura risultare peggiore del codice equivalente non SIMD più semplice.

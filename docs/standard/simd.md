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
# <a name="use-simd-accelerated-numeric-types"></a><span data-ttu-id="ea60a-103">Usare i tipi numerici con accelerazione SIMD</span><span class="sxs-lookup"><span data-stu-id="ea60a-103">Use SIMD-accelerated numeric types</span></span>

<span data-ttu-id="ea60a-104">SIMD (istruzione singola, più dati) fornisce il supporto hardware per l'esecuzione di un'operazione su più parti di dati, in parallelo, usando una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="ea60a-104">SIMD (Single instruction, multiple data) provides hardware support for performing an operation on multiple pieces of data, in parallel, using a single instruction.</span></span> <span data-ttu-id="ea60a-105">In .NET è disponibile un <xref:System.Numerics> set di tipi con accelerazione SIMD nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ea60a-105">In .NET, there's set of SIMD-accelerated types under the <xref:System.Numerics> namespace.</span></span> <span data-ttu-id="ea60a-106">Le operazioni SIMD possono essere eseguite in parallelo a livello hardware.</span><span class="sxs-lookup"><span data-stu-id="ea60a-106">SIMD operations can be parallelized at the hardware level.</span></span> <span data-ttu-id="ea60a-107">Questo approccio aumenta la velocità effettiva dei calcoli vettorializzati, che sono comuni in app matematiche scientifiche e grafiche.</span><span class="sxs-lookup"><span data-stu-id="ea60a-107">That increases the throughput of the vectorized computations, which are common in mathematical, scientific, and graphics apps.</span></span>

## <a name="net-simd-accelerated-types"></a><span data-ttu-id="ea60a-108">Tipi di SIMD con accelerazione .NET</span><span class="sxs-lookup"><span data-stu-id="ea60a-108">.NET SIMD-accelerated types</span></span>

<span data-ttu-id="ea60a-109">I tipi .NET SIMD-Accelerated includono i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea60a-109">The .NET SIMD-accelerated types include the following types:</span></span>

- <span data-ttu-id="ea60a-110">Tipi <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> e <xref:System.Numerics.Vector4>, che rappresentano i vettori con 2, 3 e 4 valori <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="ea60a-110">The <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, and <xref:System.Numerics.Vector4> types, which represent vectors with 2, 3, and 4 <xref:System.Single> values.</span></span>

- <span data-ttu-id="ea60a-111">Due tipi di matrice <xref:System.Numerics.Matrix3x2>,, che rappresenta una matrice 3x2, <xref:System.Numerics.Matrix4x4>e, che rappresenta una matrice 4x4 <xref:System.Single> di valori.</span><span class="sxs-lookup"><span data-stu-id="ea60a-111">Two matrix types, <xref:System.Numerics.Matrix3x2>, which represents a 3x2 matrix, and <xref:System.Numerics.Matrix4x4>, which represents a 4x4 matrix of <xref:System.Single> values.</span></span>

- <span data-ttu-id="ea60a-112"><xref:System.Numerics.Plane> Tipo, che rappresenta un piano nello spazio tridimensionale usando <xref:System.Single> i valori.</span><span class="sxs-lookup"><span data-stu-id="ea60a-112">The <xref:System.Numerics.Plane> type, which represents a plane in three-dimensional space using <xref:System.Single> values.</span></span>

- <span data-ttu-id="ea60a-113">Il <xref:System.Numerics.Quaternion> tipo, che rappresenta un vettore usato per codificare le rotazioni fisiche tridimensionali usando <xref:System.Single> i valori.</span><span class="sxs-lookup"><span data-stu-id="ea60a-113">The <xref:System.Numerics.Quaternion> type, which represents a vector that is used to encode three-dimensional physical rotations using <xref:System.Single> values.</span></span>

- <span data-ttu-id="ea60a-114">Tipo <xref:System.Numerics.Vector%601>, che rappresenta un vettore di un tipo numerico specificato e fornisce un ampio set di operatori che traggono vantaggio dal supporto per SIMD.</span><span class="sxs-lookup"><span data-stu-id="ea60a-114">The <xref:System.Numerics.Vector%601> type, which represents a vector of a specified numeric type and provides a broad set of operators that benefit from SIMD support.</span></span> <span data-ttu-id="ea60a-115">Il numero di un' <xref:System.Numerics.Vector%601> istanza è corretto per la durata di un'applicazione, ma il relativo <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> valore dipende dalla CPU del computer che esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="ea60a-115">The count of a <xref:System.Numerics.Vector%601> instance is fixed for the lifetime of an application, but its value <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> depends on the CPU of the machine running the code.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ea60a-116">Il <xref:System.Numerics.Vector%601> tipo non è incluso nell'.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea60a-116">The <xref:System.Numerics.Vector%601> type is not included in the .NET Framework.</span></span> <span data-ttu-id="ea60a-117">È necessario installare il pacchetto NuGet [System.Numerics.Vectors](https://www.nuget.org/packages/System.Numerics.Vectors) per ottenere l'accesso a questo tipo.</span><span class="sxs-lookup"><span data-stu-id="ea60a-117">You must install the [System.Numerics.Vectors](https://www.nuget.org/packages/System.Numerics.Vectors) NuGet package to get access to this type.</span></span>
  
<span data-ttu-id="ea60a-118">I tipi con accelerazione SIMD vengono implementati in modo che possano essere usati con compilatori JIT o hardware non SIMD.</span><span class="sxs-lookup"><span data-stu-id="ea60a-118">The SIMD-accelerated types are implemented in such a way that they can be used with non-SIMD-accelerated hardware or JIT compilers.</span></span> <span data-ttu-id="ea60a-119">Per sfruttare le istruzioni SIMD, le app a 64 bit devono essere eseguite dal runtime che usa il compilatore **RyuJIT** .</span><span class="sxs-lookup"><span data-stu-id="ea60a-119">To take advantage of SIMD instructions, your 64-bit apps must be run by the runtime that uses the **RyuJIT** compiler.</span></span> <span data-ttu-id="ea60a-120">Un compilatore **RyuJIT** è incluso in .NET Core e in .NET Framework 4,6 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ea60a-120">A **RyuJIT** compiler is included in .NET Core and in .NET Framework 4.6 and later.</span></span> <span data-ttu-id="ea60a-121">Il supporto di SIMD viene fornito solo quando è destinato a processori a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="ea60a-121">SIMD support is only provided when targeting 64-bit processors.</span></span>

## <a name="how-to-use-simd"></a><span data-ttu-id="ea60a-122">Come usare SIMD</span><span class="sxs-lookup"><span data-stu-id="ea60a-122">How to use SIMD?</span></span>

<span data-ttu-id="ea60a-123">Prima di eseguire algoritmi SIMD personalizzati, è possibile verificare se il computer host supporta SIMD usando <xref:System.Numerics.Vector.IsHardwareAccelerated?displayProperty=nameWithType>, che restituisce. <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="ea60a-123">Before executing custom SIMD algorithms, it's possible to check if the host machine supports SIMD by using <xref:System.Numerics.Vector.IsHardwareAccelerated?displayProperty=nameWithType>, which returns a <xref:System.Boolean>.</span></span> <span data-ttu-id="ea60a-124">Ciò non garantisce che SIMD-Acceleration sia abilitato per un tipo specifico, ma è un indicatore che è supportato da alcuni tipi.</span><span class="sxs-lookup"><span data-stu-id="ea60a-124">This doesn't guarantee that SIMD-acceleration is enabled for a specific type, but is an indicator that it's supported by some types.</span></span>

## <a name="simple-vectors"></a><span data-ttu-id="ea60a-125">Vettori semplici</span><span class="sxs-lookup"><span data-stu-id="ea60a-125">Simple Vectors</span></span>

<span data-ttu-id="ea60a-126">I tipi con accelerazione SIMD più primitivi in .NET sono <xref:System.Numerics.Vector2> <xref:System.Numerics.Vector3>i tipi, <xref:System.Numerics.Vector4> e, che rappresentano i vettori con i valori 2, 3 e <xref:System.Single> 4.</span><span class="sxs-lookup"><span data-stu-id="ea60a-126">The most primitive SIMD-accelerated types in .NET are <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, and <xref:System.Numerics.Vector4> types, which represent vectors with 2, 3, and 4 <xref:System.Single> values.</span></span> <span data-ttu-id="ea60a-127">Nell'esempio seguente viene <xref:System.Numerics.Vector2> usato per aggiungere due vettori.</span><span class="sxs-lookup"><span data-stu-id="ea60a-127">The example below uses <xref:System.Numerics.Vector2> to add two vectors.</span></span>

```csharp
var v1 = new Vector2(0.1f, 0.2f);
var v2 = new Vector2(1.1f, 2.2f);
var vResutl = v1 + v2;
```

<span data-ttu-id="ea60a-128">È anche possibile usare i vettori .NET per calcolare altre proprietà matematiche dei vettori, ad esempio `Dot product`, `Transform` `Clamp` e così via.</span><span class="sxs-lookup"><span data-stu-id="ea60a-128">It's also possible to use .NET vectors to calculate other mathematical properties of vectors such as `Dot product`, `Transform`, `Clamp` and so on.</span></span>

```csharp
var v1 = new Vector2(0.1f, 0.2f);
var v2 = new Vector2(1.1f, 2.2f);
var vResutl1 = Vector2.Dot(v1, v2);
var vResutl2 = Vector2.Distance(v1, v2);
var vResutl3 = Vector2.Clamp(v1, Vector2.Zero, Vector2.One);
```

## <a name="matrix"></a><span data-ttu-id="ea60a-129">Matrice</span><span class="sxs-lookup"><span data-stu-id="ea60a-129">Matrix</span></span>

<span data-ttu-id="ea60a-130"><xref:System.Numerics.Matrix3x2>, che rappresenta una matrice 3x2, e <xref:System.Numerics.Matrix4x4>, che rappresenta una matrice 4x4.</span><span class="sxs-lookup"><span data-stu-id="ea60a-130"><xref:System.Numerics.Matrix3x2>, which represents a 3x2 matrix, and <xref:System.Numerics.Matrix4x4>, which represents a 4x4 matrix.</span></span> <span data-ttu-id="ea60a-131">Può essere usato per i calcoli correlati a matrici.</span><span class="sxs-lookup"><span data-stu-id="ea60a-131">Can be used for matrix-related calculations.</span></span> <span data-ttu-id="ea60a-132">Nell'esempio seguente viene illustrata la moltiplicazione di una matrice per la matrice di trasposizione corrispondente utilizzando SIMD.</span><span class="sxs-lookup"><span data-stu-id="ea60a-132">The example below demonstrates multiplication of a matrix to its correspondent transpose matrix using SIMD.</span></span>

```csharp
var m1 = new Matrix4x4(
            1.1f, 1.2f, 1.3f, 1.4f,
            2.1f, 2.2f, 3.3f, 4.4f,
            3.1f, 3.2f, 3.3f, 3.4f,
            4.1f, 4.2f, 4.3f, 4.4f);

var m2 = Matrix4x4.Transpose(m1);
var mResult = Matrix4x4.Multiply(m1, m2);
```

## <a name="vectort"></a><span data-ttu-id="ea60a-133">Vettore\<T></span><span class="sxs-lookup"><span data-stu-id="ea60a-133">Vector\<T></span></span>

<span data-ttu-id="ea60a-134"><xref:System.Numerics.Vector%601> Offre la possibilità di usare vettori più lunghi.</span><span class="sxs-lookup"><span data-stu-id="ea60a-134">The <xref:System.Numerics.Vector%601> gives the ability to use longer vectors.</span></span> <span data-ttu-id="ea60a-135">Il conteggio di un' <xref:System.Numerics.Vector%601> istanza è fisso, ma il relativo <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> valore dipende dalla CPU del computer in cui è in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="ea60a-135">The count of a <xref:System.Numerics.Vector%601> instance is fixed, but its value <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> depends on the CPU of the machine running the code.</span></span>

<span data-ttu-id="ea60a-136">Nell'esempio seguente viene illustrata l'aggiunta di elementi <xref:System.Numerics.Vector%601>di matrici Long tramite.</span><span class="sxs-lookup"><span data-stu-id="ea60a-136">The example below demonstrates adding long arrays elements using <xref:System.Numerics.Vector%601>.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="ea60a-137">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ea60a-137">Remarks</span></span>

<span data-ttu-id="ea60a-138">È più probabile che SIMD elimini un collo di bottiglia ed esponga il successivo, ad esempio la velocità effettiva della memoria.</span><span class="sxs-lookup"><span data-stu-id="ea60a-138">SIMD is more likely to remove one bottleneck and expose the next, for example memory throughput.</span></span> <span data-ttu-id="ea60a-139">In generale, i vantaggi a livello di prestazioni derivanti dall'uso di SIMD variano a seconda dello scenario specifico e in alcuni casi può addirittura risultare peggiore del codice equivalente non SIMD più semplice.</span><span class="sxs-lookup"><span data-stu-id="ea60a-139">In general the performance benefit of using SIMD varies depending on the specific scenario, and in some cases it can even perform worse than simpler non-SIMD equivalent code.</span></span>

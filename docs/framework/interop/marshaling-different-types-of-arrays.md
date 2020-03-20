---
title: Marshalling di diversi tipi di matrici
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
ms.openlocfilehash: 66c7ba5989952edb55f21aab960ad7395a92ae0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181357"
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="66fb9-102">Marshalling di diversi tipi di matrici</span><span class="sxs-lookup"><span data-stu-id="66fb9-102">Marshaling Different Types of Arrays</span></span>
<span data-ttu-id="66fb9-103">Una matrice è un tipo di riferimento nel codice gestito che contiene uno o più elementi dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="66fb9-103">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="66fb9-104">Anche se le matrici sono tipi di riferimento, vengono passate come parametri in alle funzioni non gestite.</span><span class="sxs-lookup"><span data-stu-id="66fb9-104">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="66fb9-105">Questo comportamento non è coerente con il modo in cui le matrici gestite vengono passate agli oggetti gestiti, ovvero come parametri in/out.</span><span class="sxs-lookup"><span data-stu-id="66fb9-105">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="66fb9-106">Per altri dettagli, vedere [Copia e blocco](copying-and-pinning.md).</span><span class="sxs-lookup"><span data-stu-id="66fb9-106">For additional details, see [Copying and Pinning](copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="66fb9-107">La tabella seguente elenca le opzioni di marshalling delle matrici e ne descrive l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="66fb9-107">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="66fb9-108">Array</span><span class="sxs-lookup"><span data-stu-id="66fb9-108">Array</span></span>|<span data-ttu-id="66fb9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66fb9-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="66fb9-110">Di Integer in base al valore.</span><span class="sxs-lookup"><span data-stu-id="66fb9-110">Of integers by value.</span></span>|<span data-ttu-id="66fb9-111">Passa una matrice di Integer come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="66fb9-111">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="66fb9-112">Di Integer in base al riferimento.</span><span class="sxs-lookup"><span data-stu-id="66fb9-112">Of integers by reference.</span></span>|<span data-ttu-id="66fb9-113">Passa una matrice di Integer come un parametro in/out.</span><span class="sxs-lookup"><span data-stu-id="66fb9-113">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="66fb9-114">Di Integer in base al valore (bidimensionale).</span><span class="sxs-lookup"><span data-stu-id="66fb9-114">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="66fb9-115">Passa una matrice di Integer come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="66fb9-115">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="66fb9-116">Di stringhe in base al valore.</span><span class="sxs-lookup"><span data-stu-id="66fb9-116">Of strings by value.</span></span>|<span data-ttu-id="66fb9-117">Passa una matrice di stringhe come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="66fb9-117">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="66fb9-118">Di strutture con Integer.</span><span class="sxs-lookup"><span data-stu-id="66fb9-118">Of structures with integers.</span></span>|<span data-ttu-id="66fb9-119">Passa una matrice di strutture che contengono Integer come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="66fb9-119">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="66fb9-120">Di strutture con stringhe.</span><span class="sxs-lookup"><span data-stu-id="66fb9-120">Of structures with strings.</span></span>|<span data-ttu-id="66fb9-121">Passa una matrice di strutture che contengono solo stringhe come parametro In/Out.</span><span class="sxs-lookup"><span data-stu-id="66fb9-121">Passes an array of structures that contain only strings as an In/Out parameter.</span></span> <span data-ttu-id="66fb9-122">È possibile modificare i membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="66fb9-122">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="66fb9-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="66fb9-123">Example</span></span>  
 <span data-ttu-id="66fb9-124">Questo esempio illustra come passare i tipi di matrice seguenti:</span><span class="sxs-lookup"><span data-stu-id="66fb9-124">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
- <span data-ttu-id="66fb9-125">Matrice di Integer in base al valore.</span><span class="sxs-lookup"><span data-stu-id="66fb9-125">Array of integers by value.</span></span>  
  
- <span data-ttu-id="66fb9-126">Matrice di Integer in base al riferimento, che è possibile ridimensionare.</span><span class="sxs-lookup"><span data-stu-id="66fb9-126">Array of integers by reference, which can be resized.</span></span>  
  
- <span data-ttu-id="66fb9-127">Matrice multidimensionale di Integer in base al valore.</span><span class="sxs-lookup"><span data-stu-id="66fb9-127">Multidimensional array (matrix) of integers by value.</span></span>  
  
- <span data-ttu-id="66fb9-128">Matrice di stringhe in base al valore.</span><span class="sxs-lookup"><span data-stu-id="66fb9-128">Array of strings by value.</span></span>  
  
- <span data-ttu-id="66fb9-129">Matrice di strutture con Integer.</span><span class="sxs-lookup"><span data-stu-id="66fb9-129">Array of structures with integers.</span></span>  
  
- <span data-ttu-id="66fb9-130">Matrice di strutture con stringhe.</span><span class="sxs-lookup"><span data-stu-id="66fb9-130">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="66fb9-131">A meno che non venga eseguito il marshalling esplicito di una matrice in base al riferimento, il comportamento predefinito esegue il marshalling della matrice come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="66fb9-131">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="66fb9-132">È possibile modificare questo comportamento applicando in modo esplicito gli attributi <xref:System.Runtime.InteropServices.InAttribute> e <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="66fb9-132">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="66fb9-133">Nell'esempio di matrici vengono usate le seguenti funzioni non gestite, illustrate con le dichiarazioni di funzione originali:</span><span class="sxs-lookup"><span data-stu-id="66fb9-133">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
- <span data-ttu-id="66fb9-134">**TestArrayOfInts** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="66fb9-134">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- <span data-ttu-id="66fb9-135">**TestRefArrayOfInts** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="66fb9-135">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- <span data-ttu-id="66fb9-136">**TestMatrixOfInts** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="66fb9-136">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- <span data-ttu-id="66fb9-137">**TestArrayOfStrings** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="66fb9-137">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- <span data-ttu-id="66fb9-138">**TestArrayOfStructs** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="66fb9-138">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- <span data-ttu-id="66fb9-139">**TestArrayOfStructs2** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="66fb9-139">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="66fb9-140">[PinvokeLib](marshaling-data-with-platform-invoke.md#pinvokelibdll) è una libreria non gestita personalizzata contenente implementazioni per le funzioni elencate in precedenza e due variabili di struttura, ovvero **MYPOINT** e **MYPERSON**.</span><span class="sxs-lookup"><span data-stu-id="66fb9-140">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="66fb9-141">Le strutture contengono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="66fb9-141">The structures contain the following elements:</span></span>  
  
```cpp
typedef struct _MYPOINT  
{  
   int x;
   int y;
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;
   char* last;
} MYPERSON;  
```  
  
 <span data-ttu-id="66fb9-142">In questo esempio, le strutture `MyPoint` e `MyPerson` contengono tipi incorporati.</span><span class="sxs-lookup"><span data-stu-id="66fb9-142">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="66fb9-143">L'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> è impostato in modo da garantire che i membri vengano inseriti in memoria in sequenza, nell'ordine in cui appaiono.</span><span class="sxs-lookup"><span data-stu-id="66fb9-143">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="66fb9-144">La classe `NativeMethods` contiene un set di metodi chiamati dalla classe `App` .</span><span class="sxs-lookup"><span data-stu-id="66fb9-144">The `NativeMethods` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="66fb9-145">Per informazioni specifiche sul passaggio di matrici, vedere i commenti nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="66fb9-145">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="66fb9-146">Una matrice, che è un tipo di riferimento, viene passata come un parametro in per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="66fb9-146">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="66fb9-147">Per permettere al chiamante di ricevere i risultati, **InAttribute** e **OutAttribute** devono essere applicati in modo esplicito all'argomento contenente la matrice.</span><span class="sxs-lookup"><span data-stu-id="66fb9-147">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="66fb9-148">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="66fb9-148">Declaring Prototypes</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="66fb9-149">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="66fb9-149">Calling Functions</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="66fb9-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66fb9-150">See also</span></span>

- [<span data-ttu-id="66fb9-151">Tipi di dati PInvoke</span><span class="sxs-lookup"><span data-stu-id="66fb9-151">Platform invoke data types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="66fb9-152">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="66fb9-152">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)

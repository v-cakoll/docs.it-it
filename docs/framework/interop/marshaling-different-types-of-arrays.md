---
title: Marshalling di diversi tipi di matrici
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 157d157eceaa83893df3acf5efc9a8d4c1b27200
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="55bcf-102">Marshalling di diversi tipi di matrici</span><span class="sxs-lookup"><span data-stu-id="55bcf-102">Marshaling Different Types of Arrays</span></span>
<span data-ttu-id="55bcf-103">Una matrice è un tipo di riferimento nel codice gestito che contiene uno o più elementi dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="55bcf-103">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="55bcf-104">Anche se le matrici sono tipi di riferimento, vengono passate come parametri in alle funzioni non gestite.</span><span class="sxs-lookup"><span data-stu-id="55bcf-104">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="55bcf-105">Questo comportamento non è coerente con il modo in cui le matrici gestite vengono passate agli oggetti gestiti, ovvero come parametri in/out.</span><span class="sxs-lookup"><span data-stu-id="55bcf-105">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="55bcf-106">Per altri dettagli, vedere [Copia e blocco](../../../docs/framework/interop/copying-and-pinning.md).</span><span class="sxs-lookup"><span data-stu-id="55bcf-106">For additional details, see [Copying and Pinning](../../../docs/framework/interop/copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="55bcf-107">La tabella seguente elenca le opzioni di marshalling delle matrici e ne descrive l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="55bcf-107">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="55bcf-108">Matrice</span><span class="sxs-lookup"><span data-stu-id="55bcf-108">Array</span></span>|<span data-ttu-id="55bcf-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55bcf-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="55bcf-110">Di Integer in base al valore.</span><span class="sxs-lookup"><span data-stu-id="55bcf-110">Of integers by value.</span></span>|<span data-ttu-id="55bcf-111">Passa una matrice di Integer come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="55bcf-111">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="55bcf-112">Di Integer in base al riferimento.</span><span class="sxs-lookup"><span data-stu-id="55bcf-112">Of integers by reference.</span></span>|<span data-ttu-id="55bcf-113">Passa una matrice di Integer come un parametro in/out.</span><span class="sxs-lookup"><span data-stu-id="55bcf-113">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="55bcf-114">Di Integer in base al valore (bidimensionale).</span><span class="sxs-lookup"><span data-stu-id="55bcf-114">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="55bcf-115">Passa una matrice di Integer come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="55bcf-115">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="55bcf-116">Di stringhe in base al valore.</span><span class="sxs-lookup"><span data-stu-id="55bcf-116">Of strings by value.</span></span>|<span data-ttu-id="55bcf-117">Passa una matrice di stringhe come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="55bcf-117">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="55bcf-118">Di strutture con Integer.</span><span class="sxs-lookup"><span data-stu-id="55bcf-118">Of structures with integers.</span></span>|<span data-ttu-id="55bcf-119">Passa una matrice di strutture che contengono Integer come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="55bcf-119">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="55bcf-120">Di strutture con stringhe.</span><span class="sxs-lookup"><span data-stu-id="55bcf-120">Of structures with strings.</span></span>|<span data-ttu-id="55bcf-121">Passa una matrice di strutture che contengono solo Integer come un parametro in/out.</span><span class="sxs-lookup"><span data-stu-id="55bcf-121">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="55bcf-122">È possibile modificare i membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="55bcf-122">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="55bcf-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="55bcf-123">Example</span></span>  
 <span data-ttu-id="55bcf-124">Questo esempio illustra come passare i tipi di matrice seguenti:</span><span class="sxs-lookup"><span data-stu-id="55bcf-124">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
-   <span data-ttu-id="55bcf-125">Matrice di Integer in base al valore.</span><span class="sxs-lookup"><span data-stu-id="55bcf-125">Array of integers by value.</span></span>  
  
-   <span data-ttu-id="55bcf-126">Matrice di Integer in base al riferimento, che è possibile ridimensionare.</span><span class="sxs-lookup"><span data-stu-id="55bcf-126">Array of integers by reference, which can be resized.</span></span>  
  
-   <span data-ttu-id="55bcf-127">Matrice multidimensionale di Integer in base al valore.</span><span class="sxs-lookup"><span data-stu-id="55bcf-127">Multidimensional array (matrix) of integers by value.</span></span>  
  
-   <span data-ttu-id="55bcf-128">Matrice di stringhe in base al valore.</span><span class="sxs-lookup"><span data-stu-id="55bcf-128">Array of strings by value.</span></span>  
  
-   <span data-ttu-id="55bcf-129">Matrice di strutture con Integer.</span><span class="sxs-lookup"><span data-stu-id="55bcf-129">Array of structures with integers.</span></span>  
  
-   <span data-ttu-id="55bcf-130">Matrice di strutture con stringhe.</span><span class="sxs-lookup"><span data-stu-id="55bcf-130">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="55bcf-131">A meno che non venga eseguito il marshalling esplicito di una matrice in base al riferimento, il comportamento predefinito esegue il marshalling della matrice come un parametro in.</span><span class="sxs-lookup"><span data-stu-id="55bcf-131">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="55bcf-132">È possibile modificare questo comportamento applicando in modo esplicito gli attributi <xref:System.Runtime.InteropServices.InAttribute> e <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="55bcf-132">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="55bcf-133">Nell'esempio di matrici vengono usate le seguenti funzioni non gestite, illustrate con le dichiarazioni di funzione originali:</span><span class="sxs-lookup"><span data-stu-id="55bcf-133">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="55bcf-134">**TestArrayOfInts** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="55bcf-134">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
-   <span data-ttu-id="55bcf-135">**TestRefArrayOfInts** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="55bcf-135">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
-   <span data-ttu-id="55bcf-136">**TestMatrixOfInts** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="55bcf-136">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
-   <span data-ttu-id="55bcf-137">**TestArrayOfStrings** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="55bcf-137">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
-   <span data-ttu-id="55bcf-138">**TestArrayOfStructs** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="55bcf-138">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
-   <span data-ttu-id="55bcf-139">**TestArrayOfStructs2** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="55bcf-139">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="55bcf-140">[PinvokeLib](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) è una libreria non gestita personalizzata contenente implementazioni per le funzioni elencate in precedenza e due variabili di struttura, ovvero **MYPOINT** e **MYPERSON**.</span><span class="sxs-lookup"><span data-stu-id="55bcf-140">[PinvokeLib.dll](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="55bcf-141">Le strutture contengono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="55bcf-141">The structures contain the following elements:</span></span>  
  
```  
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
  
 <span data-ttu-id="55bcf-142">In questo esempio, le strutture `MyPoint` e `MyPerson` contengono tipi incorporati.</span><span class="sxs-lookup"><span data-stu-id="55bcf-142">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="55bcf-143">L'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> è impostato in modo da garantire che i membri vengano inseriti in memoria in sequenza, nell'ordine in cui appaiono.</span><span class="sxs-lookup"><span data-stu-id="55bcf-143">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="55bcf-144">La classe `LibWrap` contiene un set di metodi chiamati dalla classe `App` .</span><span class="sxs-lookup"><span data-stu-id="55bcf-144">The `LibWrap` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="55bcf-145">Per informazioni specifiche sul passaggio di matrici, vedere i commenti nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="55bcf-145">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="55bcf-146">Una matrice, che è un tipo di riferimento, viene passata come un parametro in per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="55bcf-146">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="55bcf-147">Per permettere al chiamante di ricevere i risultati, **InAttribute** e **OutAttribute** devono essere applicati in modo esplicito all'argomento contenente la matrice.</span><span class="sxs-lookup"><span data-stu-id="55bcf-147">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="55bcf-148">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="55bcf-148">Declaring Prototypes</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="55bcf-149">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="55bcf-149">Calling Functions</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="55bcf-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55bcf-150">See Also</span></span>  
 [<span data-ttu-id="55bcf-151">Marshalling di matrici di tipi</span><span class="sxs-lookup"><span data-stu-id="55bcf-151">Marshaling Arrays of Types</span></span>](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)  
 [<span data-ttu-id="55bcf-152">Tipi di dati di Platform Invoke</span><span class="sxs-lookup"><span data-stu-id="55bcf-152">Platform Invoke Data Types</span></span>](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [<span data-ttu-id="55bcf-153">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="55bcf-153">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)

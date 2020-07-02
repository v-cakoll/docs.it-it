---
title: Marshalling di classi, strutture e unioni
description: Esaminare come effettuare il marshalling di classi, strutture e unioni. Visualizzazione di esempi di classi di marshalling, strutture con strutture annidate, matrici di strutture e unioni.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
ms.openlocfilehash: 5e616b5bb513939cadd8fe5c72675ba0b6e070a3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621522"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="1dff0-104">Marshalling di classi, strutture e unioni</span><span class="sxs-lookup"><span data-stu-id="1dff0-104">Marshaling Classes, Structures, and Unions</span></span>

<span data-ttu-id="1dff0-105">In .NET Framework classi e strutture sono simili.</span><span class="sxs-lookup"><span data-stu-id="1dff0-105">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="1dff0-106">Entrambe possono avere campi, proprietà ed eventi</span><span class="sxs-lookup"><span data-stu-id="1dff0-106">Both can have fields, properties, and events.</span></span> <span data-ttu-id="1dff0-107">nonché metodi statici e non statici.</span><span class="sxs-lookup"><span data-stu-id="1dff0-107">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="1dff0-108">Una differenza fondamentale è data dal fatto che le strutture sono tipi di valore e le classi sono tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="1dff0-108">One notable difference is that structures are value types and classes are reference types.</span></span>

<span data-ttu-id="1dff0-109">Nella tabella seguente sono elencate le opzioni di marshalling per le classi, le strutture e le unioni con la descrizione dell'utilizzo e un collegamento all'esempio corrispondente di platform invoke.</span><span class="sxs-lookup"><span data-stu-id="1dff0-109">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>

|<span data-ttu-id="1dff0-110">Type</span><span class="sxs-lookup"><span data-stu-id="1dff0-110">Type</span></span>|<span data-ttu-id="1dff0-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1dff0-111">Description</span></span>|<span data-ttu-id="1dff0-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="1dff0-112">Sample</span></span>|
|----------|-----------------|------------|
|<span data-ttu-id="1dff0-113">Classe per valore.</span><span class="sxs-lookup"><span data-stu-id="1dff0-113">Class by value.</span></span>|<span data-ttu-id="1dff0-114">Passa una classe con membri Integer come parametro in/out, come il case gestito.</span><span class="sxs-lookup"><span data-stu-id="1dff0-114">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|[<span data-ttu-id="1dff0-115">SysTime (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-115">SysTime sample</span></span>](#systime-sample)|
|<span data-ttu-id="1dff0-116">Struttura per valore.</span><span class="sxs-lookup"><span data-stu-id="1dff0-116">Structure by value.</span></span>|<span data-ttu-id="1dff0-117">Passa le strutture come parametri in.</span><span class="sxs-lookup"><span data-stu-id="1dff0-117">Passes structures as In parameters.</span></span>|[<span data-ttu-id="1dff0-118">Structures (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-118">Structures sample</span></span>](#structures-sample)|
|<span data-ttu-id="1dff0-119">Struttura per riferimento.</span><span class="sxs-lookup"><span data-stu-id="1dff0-119">Structure by reference.</span></span>|<span data-ttu-id="1dff0-120">Passa le strutture come parametri in/out.</span><span class="sxs-lookup"><span data-stu-id="1dff0-120">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="1dff0-121">[OSInfo (esempio)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1dff0-121">[OSInfo sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span></span>|
|<span data-ttu-id="1dff0-122">Struttura con strutture annidate (semplificata).</span><span class="sxs-lookup"><span data-stu-id="1dff0-122">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="1dff0-123">Passa una classe che rappresenta una struttura con strutture annidate nella funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="1dff0-123">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="1dff0-124">La struttura viene semplificata in una sola grande struttura nel prototipo gestito.</span><span class="sxs-lookup"><span data-stu-id="1dff0-124">The structure is flattened to one big structure in the managed prototype.</span></span>|[<span data-ttu-id="1dff0-125">FindFile (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-125">FindFile sample</span></span>](#findfile-sample)|
|<span data-ttu-id="1dff0-126">Struttura con puntatore a un'altra struttura.</span><span class="sxs-lookup"><span data-stu-id="1dff0-126">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="1dff0-127">Passa una struttura che contiene un puntatore a una seconda struttura come membro.</span><span class="sxs-lookup"><span data-stu-id="1dff0-127">Passes a structure that contains a pointer to a second structure as a member.</span></span>|[<span data-ttu-id="1dff0-128">Esempio di strutture</span><span class="sxs-lookup"><span data-stu-id="1dff0-128">Structures Sample</span></span>](#structures-sample)|
|<span data-ttu-id="1dff0-129">Matrice di strutture con Integer per valore.</span><span class="sxs-lookup"><span data-stu-id="1dff0-129">Array of structures with integers by value.</span></span>|<span data-ttu-id="1dff0-130">Passa una matrice di strutture che contengono solo Integer come un parametro in/out.</span><span class="sxs-lookup"><span data-stu-id="1dff0-130">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="1dff0-131">È possibile modificare i membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="1dff0-131">Members of the array can be changed.</span></span>|[<span data-ttu-id="1dff0-132">Arrays (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-132">Arrays Sample</span></span>](marshaling-different-types-of-arrays.md)|
|<span data-ttu-id="1dff0-133">Matrice di strutture con Integer e stringhe per riferimento.</span><span class="sxs-lookup"><span data-stu-id="1dff0-133">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="1dff0-134">Passa una matrice di strutture che contengono Integer e stringhe come un parametro out.</span><span class="sxs-lookup"><span data-stu-id="1dff0-134">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="1dff0-135">La memoria per la matrice viene allocata dalla funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="1dff0-135">The called function allocates memory for the array.</span></span>|[<span data-ttu-id="1dff0-136">Esempio OutArrayOfStructs (</span><span class="sxs-lookup"><span data-stu-id="1dff0-136">OutArrayOfStructs Sample</span></span>](#outarrayofstructs-sample)|
|<span data-ttu-id="1dff0-137">Unioni con tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="1dff0-137">Unions with value types.</span></span>|<span data-ttu-id="1dff0-138">Passa le unioni con tipi di valore (Integer e Double).</span><span class="sxs-lookup"><span data-stu-id="1dff0-138">Passes unions with value types (integer and double).</span></span>|[<span data-ttu-id="1dff0-139">unioni (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-139">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="1dff0-140">Unioni con tipi misti.</span><span class="sxs-lookup"><span data-stu-id="1dff0-140">Unions with mixed types.</span></span>|<span data-ttu-id="1dff0-141">Passa unioni con tipi misti (Integer e String).</span><span class="sxs-lookup"><span data-stu-id="1dff0-141">Passes unions with mixed types (integer and string).</span></span>|[<span data-ttu-id="1dff0-142">unioni (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-142">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="1dff0-143">Struct con layout specifico della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="1dff0-143">Struct with platform-specific layout.</span></span>|<span data-ttu-id="1dff0-144">Passa un tipo con le definizioni di compressione native.</span><span class="sxs-lookup"><span data-stu-id="1dff0-144">Passes a type with native-packing definitions.</span></span>|[<span data-ttu-id="1dff0-145">Esempio Platform</span><span class="sxs-lookup"><span data-stu-id="1dff0-145">Platform sample</span></span>](#platform-sample)|
|<span data-ttu-id="1dff0-146">Valori null nella struttura.</span><span class="sxs-lookup"><span data-stu-id="1dff0-146">Null values in structure.</span></span>|<span data-ttu-id="1dff0-147">Passa un riferimento null (**Nothing** in Visual Basic) invece di un riferimento a un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="1dff0-147">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="1dff0-148">[HandleRef (esempio)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="1dff0-148">[HandleRef sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span></span>|

## <a name="structures-sample"></a><span data-ttu-id="1dff0-149">Structures (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-149">Structures sample</span></span>

<span data-ttu-id="1dff0-150">In questo esempio viene dimostrato come passare una struttura che punta a una seconda struttura, una struttura con una struttura incorporata e una struttura con una matrice incorporata.</span><span class="sxs-lookup"><span data-stu-id="1dff0-150">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
<span data-ttu-id="1dff0-151">Nell'esempio di strutture vengono usate le seguenti funzioni non gestite, illustrate con le dichiarazioni di funzione originali:</span><span class="sxs-lookup"><span data-stu-id="1dff0-151">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="1dff0-152">**TestStructInStruct** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="1dff0-152">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- <span data-ttu-id="1dff0-153">**TestStructInStruct3** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="1dff0-153">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- <span data-ttu-id="1dff0-154">**TestArrayInStruct** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="1dff0-154">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

<span data-ttu-id="1dff0-155">[PinvokeLib](marshaling-data-with-platform-invoke.md#pinvokelibdll) è una libreria non gestita personalizzata contenente implementazioni per le funzioni elencate in precedenza e quattro strutture, ovvero: **MYPERSON**, **MYPERSON2**, **MYPERSON3** e **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="1dff0-155">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="1dff0-156">Le strutture contengono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1dff0-156">These structures contain the following elements:</span></span>

```cpp
typedef struct _MYPERSON
{
   char* first;
   char* last;
} MYPERSON, *LP_MYPERSON;

typedef struct _MYPERSON2
{
   MYPERSON* person;
   int age;
} MYPERSON2, *LP_MYPERSON2;

typedef struct _MYPERSON3
{
   MYPERSON person;
   int age;
} MYPERSON3;

typedef struct _MYARRAYSTRUCT
{
   bool flag;
   int vals[ 3 ];
} MYARRAYSTRUCT;
```

<span data-ttu-id="1dff0-157">Le strutture gestite `MyPerson`,`MyPerson2`, `MyPerson3` e `MyArrayStruct` hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="1dff0-157">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>

- <span data-ttu-id="1dff0-158">`MyPerson` contiene solo membri stringa.</span><span class="sxs-lookup"><span data-stu-id="1dff0-158">`MyPerson` contains only string members.</span></span> <span data-ttu-id="1dff0-159">Le stringhe vengono impostate sul formato ANSI dal campo [CharSet](specifying-a-character-set.md), quando viene passato alla funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="1dff0-159">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>

- <span data-ttu-id="1dff0-160">`MyPerson2`contiene un oggetto **IntPtr** per la `MyPerson` struttura.</span><span class="sxs-lookup"><span data-stu-id="1dff0-160">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="1dff0-161">Il tipo **IntPtr** sostituisce il puntatore originale alla struttura non gestita poiché nelle applicazioni .NET Framework non vengono usati i puntatori a meno che il codice non sia contrassegnato come **unsafe**.</span><span class="sxs-lookup"><span data-stu-id="1dff0-161">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>

- <span data-ttu-id="1dff0-162">`MyPerson3` contiene `MyPerson` come struttura incorporata.</span><span class="sxs-lookup"><span data-stu-id="1dff0-162">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="1dff0-163">È possibile semplificare una struttura incorporata in un'altra struttura posizionandone gli elementi direttamente nella struttura principale oppure mantenerla incorporata, come accade in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="1dff0-163">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>

- <span data-ttu-id="1dff0-164">`MyArrayStruct` contiene una matrice di Integer.</span><span class="sxs-lookup"><span data-stu-id="1dff0-164">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="1dff0-165">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> imposta il valore di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> su **ByValArray**, che consente di indicare il numero di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="1dff0-165">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>

<span data-ttu-id="1dff0-166">Per tutte le strutture di questo esempio, l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> viene applicato in modo che i membri vengano disposti in sequenza nella memoria, nell'ordine in cui appaiono.</span><span class="sxs-lookup"><span data-stu-id="1dff0-166">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="1dff0-167">La classe `NativeMethods` contiene prototipi gestiti per i metodi `TestStructInStruct`, `TestStructInStruct3` e `TestArrayInStruct` chiamati dalla classe `App`.</span><span class="sxs-lookup"><span data-stu-id="1dff0-167">The `NativeMethods` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="1dff0-168">Ciascun prototipo dichiara un singolo parametro, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1dff0-168">Each prototype declares a single parameter, as follows:</span></span>

- <span data-ttu-id="1dff0-169">`TestStructInStruct` dichiara un riferimento al tipo `MyPerson2` come parametro.</span><span class="sxs-lookup"><span data-stu-id="1dff0-169">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>

- <span data-ttu-id="1dff0-170">`TestStructInStruct3` dichiara il tipo `MyPerson3` come parametro e passa il parametro per valore.</span><span class="sxs-lookup"><span data-stu-id="1dff0-170">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>

- <span data-ttu-id="1dff0-171">`TestArrayInStruct` dichiara un riferimento al tipo `MyArrayStruct` come parametro.</span><span class="sxs-lookup"><span data-stu-id="1dff0-171">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>

<span data-ttu-id="1dff0-172">Come argomenti per i metodi, le strutture vengono passate per valore a meno che il parametro non contenga la parola chiave **ref** (**ByRef** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="1dff0-172">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="1dff0-173">Ad esempio, il metodo `TestStructInStruct` passa un riferimento, ossia il valore di un indirizzo, a un oggetto di tipo `MyPerson2` al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="1dff0-173">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="1dff0-174">Per modificare la struttura alla quale punta `MyPerson2`, nell'esempio viene creato un buffer di dimensioni specificate e ne viene restituito l'indirizzo combinando i metodi <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> e <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1dff0-174">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="1dff0-175">In seguito, il contenuto della struttura gestita viene copiato nel buffer non gestito.</span><span class="sxs-lookup"><span data-stu-id="1dff0-175">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="1dff0-176">Infine, il metodo <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> viene usato per effettuare il marshalling dei dati dal buffer non gestito in un oggetto gestito, mentre il metodo <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> viene usato per liberare il blocco di memoria non gestito.</span><span class="sxs-lookup"><span data-stu-id="1dff0-176">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="1dff0-177">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="1dff0-177">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a><span data-ttu-id="1dff0-178">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="1dff0-178">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a><span data-ttu-id="1dff0-179">FindFile (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-179">FindFile sample</span></span>

<span data-ttu-id="1dff0-180">In questo esempio viene illustrato come passare una struttura che contiene una seconda struttura incorporata a una funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="1dff0-180">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="1dff0-181">Viene inoltre illustrato come usare l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> per dichiarare una matrice a lunghezza fissa all'interno della struttura.</span><span class="sxs-lookup"><span data-stu-id="1dff0-181">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="1dff0-182">Nell'esempio gli elementi della struttura incorporata vengono aggiunti alla struttura padre.</span><span class="sxs-lookup"><span data-stu-id="1dff0-182">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="1dff0-183">Per un esempio di struttura incorporata non appiattita, vedere [Esempio di strutture](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1dff0-183">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>

<span data-ttu-id="1dff0-184">Nell'esempio FindFile viene usata la seguente funzione non gestita, illustrata con la relativa dichiarazione di funzione originale:</span><span class="sxs-lookup"><span data-stu-id="1dff0-184">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="1dff0-185">**FindFirstFile** esportata da Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="1dff0-185">**FindFirstFile** exported from Kernel32.dll.</span></span>

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

<span data-ttu-id="1dff0-186">La struttura originale passata alla funzione contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1dff0-186">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _WIN32_FIND_DATA
{
  DWORD    dwFileAttributes;
  FILETIME ftCreationTime;
  FILETIME ftLastAccessTime;
  FILETIME ftLastWriteTime;
  DWORD    nFileSizeHigh;
  DWORD    nFileSizeLow;
  DWORD    dwReserved0;
  DWORD    dwReserved1;
  TCHAR    cFileName[ MAX_PATH ];
  TCHAR    cAlternateFileName[ 14 ];
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;
```

<span data-ttu-id="1dff0-187">In questo esempio, la classe `FindData` contiene un membro dati corrispondente per ogni elemento della struttura originale e della struttura incorporata.</span><span class="sxs-lookup"><span data-stu-id="1dff0-187">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="1dff0-188">Al posto di due buffer di caratteri originali, la classe usa delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="1dff0-188">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="1dff0-189">**MarshalAsAttribute** imposta l'enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> su **ByValTStr**, che consente di identificare le matrici di caratteri inline a lunghezza fissa visualizzate all'interno delle strutture non gestite.</span><span class="sxs-lookup"><span data-stu-id="1dff0-189">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>

<span data-ttu-id="1dff0-190">La classe `NativeMethods` contiene un prototipo gestito del metodo `FindFirstFile`, che passa la classe `FindData` come parametro.</span><span class="sxs-lookup"><span data-stu-id="1dff0-190">The `NativeMethods` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="1dff0-191">Il parametro deve essere dichiarato con gli attributi <xref:System.Runtime.InteropServices.InAttribute> e <xref:System.Runtime.InteropServices.OutAttribute> perché le classi, che sono tipi di riferimento, per impostazione predefinita vengono passate come parametri in.</span><span class="sxs-lookup"><span data-stu-id="1dff0-191">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="1dff0-192">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="1dff0-192">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a><span data-ttu-id="1dff0-193">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="1dff0-193">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a><span data-ttu-id="1dff0-194">unioni (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-194">Unions sample</span></span>

<span data-ttu-id="1dff0-195">In questo esempio viene dimostrato come passare le strutture contenenti solo tipi di valore e le strutture contenenti un tipo di valore e una stringa come parametri a una funzione non gestita per la quale è prevista un'unione.</span><span class="sxs-lookup"><span data-stu-id="1dff0-195">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="1dff0-196">Un'unione rappresenta un percorso di memoria che può essere condiviso da due o più variabili.</span><span class="sxs-lookup"><span data-stu-id="1dff0-196">A union represents a memory location that can be shared by two or more variables.</span></span>

<span data-ttu-id="1dff0-197">Nell'esempio di unioni viene usata la seguente funzione non gestita, illustrata con la dichiarazione di funzione originale:</span><span class="sxs-lookup"><span data-stu-id="1dff0-197">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="1dff0-198">**TestUnion** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="1dff0-198">**TestUnion** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

<span data-ttu-id="1dff0-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) è una libreria non gestita personalizzata contenente un'implementazione per la funzione elencata in precedenza e due unioni, **MYUNION** e **MYUNION2**.</span><span class="sxs-lookup"><span data-stu-id="1dff0-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="1dff0-200">Le unioni contengono i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="1dff0-200">The unions contain the following elements:</span></span>

```cpp
union MYUNION
{
    int number;
    double d;
}

union MYUNION2
{
    int i;
    char str[128];
};
```

<span data-ttu-id="1dff0-201">Nel codice gestito, le unioni sono definite come strutture.</span><span class="sxs-lookup"><span data-stu-id="1dff0-201">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="1dff0-202">La struttura `MyUnion` contiene due tipi di valore come membri, ovvero un Integer e un Double.</span><span class="sxs-lookup"><span data-stu-id="1dff0-202">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="1dff0-203">L'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> è impostato in modo da controllare l'esatta posizione di ciascun membro dati.</span><span class="sxs-lookup"><span data-stu-id="1dff0-203">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="1dff0-204">L'attributo <xref:System.Runtime.InteropServices.FieldOffsetAttribute> fornisce la posizione fisica dei campi all'interno della rappresentazione non gestita di un'unione.</span><span class="sxs-lookup"><span data-stu-id="1dff0-204">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="1dff0-205">Poiché entrambi hanno gli stessi valori di offset, i membri possono definire la stessa porzione di memoria.</span><span class="sxs-lookup"><span data-stu-id="1dff0-205">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>

<span data-ttu-id="1dff0-206">`MyUnion2_1` e `MyUnion2_2` contengono rispettivamente un tipo di valore (Integer) e una stringa.</span><span class="sxs-lookup"><span data-stu-id="1dff0-206">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="1dff0-207">Nel codice gestito i tipi di valore e quelli di riferimento non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="1dff0-207">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="1dff0-208">In questo esempio l'overload dei metodi consente al chiamante di usare entrambi i tipi nella chiamata alla stessa funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="1dff0-208">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="1dff0-209">Il layout di `MyUnion2_1` è esplicito e ha un valore di offset preciso.</span><span class="sxs-lookup"><span data-stu-id="1dff0-209">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="1dff0-210">Al contrario, `MyUnion2_2` ha un layout sequenziale, poiché i layout espliciti non sono consentiti con i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="1dff0-210">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="1dff0-211">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> impostazione l'enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> su **ByValTStr**, che consente di identificare le matrici di caratteri inline a lunghezza fissa presenti nella rappresentazione non gestita dell'unione.</span><span class="sxs-lookup"><span data-stu-id="1dff0-211">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>

<span data-ttu-id="1dff0-212">La classe `NativeMethods` contiene i prototipi per i metodi `TestUnion` e `TestUnion2`.</span><span class="sxs-lookup"><span data-stu-id="1dff0-212">The `NativeMethods` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="1dff0-213">`TestUnion2` viene sottoposto a overload allo scopo di dichiarare `MyUnion2_1` o `MyUnion2_2` come parametri.</span><span class="sxs-lookup"><span data-stu-id="1dff0-213">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="1dff0-214">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="1dff0-214">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a><span data-ttu-id="1dff0-215">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="1dff0-215">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="platform-sample"></a><span data-ttu-id="1dff0-216">Esempio Platform</span><span class="sxs-lookup"><span data-stu-id="1dff0-216">Platform sample</span></span>

<span data-ttu-id="1dff0-217">In alcuni scenari, `struct` i `union` layout e possono variare a seconda della piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1dff0-217">In some scenarios, `struct` and `union` layouts can differ depending on the targeted platform.</span></span> <span data-ttu-id="1dff0-218">Si consideri, ad esempio, il [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) tipo se definito in uno scenario com:</span><span class="sxs-lookup"><span data-stu-id="1dff0-218">For example, consider the [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) type when defined in a COM scenario:</span></span>

```c++
#include <pshpack8.h> /* Defines the packing of the struct */
typedef struct _STRRET
    {
    UINT uType;
    /* [switch_is][switch_type] */ union
        {
        /* [case()][string] */ LPWSTR pOleStr;
        /* [case()] */ UINT uOffset;
        /* [case()] */ char cStr[ 260 ];
        }  DUMMYUNIONNAME;
    }  STRRET;
#include <poppack.h>
```

<span data-ttu-id="1dff0-219">Il sopra `struct` è dichiarato con le intestazioni di Windows che influiscono sul layout di memoria del tipo.</span><span class="sxs-lookup"><span data-stu-id="1dff0-219">The above `struct` is declared with Windows' headers that influence the memory layout of the type.</span></span> <span data-ttu-id="1dff0-220">Quando definito in un ambiente gestito, questi dettagli del layout sono necessari per interagire correttamente con il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="1dff0-220">When defined in a managed environment, these layout details are needed to properly interoperate with native code.</span></span>

<span data-ttu-id="1dff0-221">La definizione gestita corretta di questo tipo in un processo a 32 bit è la seguente:</span><span class="sxs-lookup"><span data-stu-id="1dff0-221">The correct managed definition of this type in a 32-bit process is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 264)]
public struct STRRET_32
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(4)]
    public IntPtr pOleStr;

    [FieldOffset(4)]
    public uint uOffset;

    [FieldOffset(4)]
    public IntPtr cStr;
}
```

<span data-ttu-id="1dff0-222">In un processo a 64 bit, le dimensioni *e* gli offset dei campi sono diversi.</span><span class="sxs-lookup"><span data-stu-id="1dff0-222">On a 64-bit process, the size *and* field offsets are different.</span></span> <span data-ttu-id="1dff0-223">Il layout corretto è il seguente:</span><span class="sxs-lookup"><span data-stu-id="1dff0-223">The correct layout is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 272)]
public struct STRRET_64
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(8)]
    public IntPtr pOleStr;

    [FieldOffset(8)]
    public uint uOffset;

    [FieldOffset(8)]
    public IntPtr cStr;
}
```

<span data-ttu-id="1dff0-224">La mancata corretta considerazione del layout nativo in uno scenario di interoperabilità può causare arresti anomali casuali o calcoli peggiori e non corretti.</span><span class="sxs-lookup"><span data-stu-id="1dff0-224">Failure to properly consider the native layout in an interop scenario can result in random crashes or worse, incorrect computations.</span></span>

<span data-ttu-id="1dff0-225">Per impostazione predefinita, gli assembly .NET possono essere eseguiti in una versione a 32 bit e a 64 bit del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="1dff0-225">By default, .NET assemblies can run in both a 32-bit and 64-bit version of the .NET runtime.</span></span> <span data-ttu-id="1dff0-226">L'app deve attendere fino alla fase di esecuzione per decidere quale delle definizioni precedenti usare.</span><span class="sxs-lookup"><span data-stu-id="1dff0-226">The app must wait until run time to decide which of the previous definitions to use.</span></span>

<span data-ttu-id="1dff0-227">Il frammento di codice seguente mostra un esempio di come scegliere tra la definizione a 32 bit e a 64 bit in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1dff0-227">The following code snippet shows an example of how to choose between the 32-bit and 64-bit definition at run time.</span></span>

```CSharp
if (IntPtr.Size == 8)
{
    // Use the STRRET_64 definition
}
else
{
    Debug.Assert(IntPtr.Size == 4);
    // Use the STRRET_32 definition
}
```

## <a name="systime-sample"></a><span data-ttu-id="1dff0-228">SysTime (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-228">SysTime sample</span></span>

<span data-ttu-id="1dff0-229">In questo esempio viene dimostrato come passare un puntatore a una classe a una funzione non gestita per la quale è previsto un puntatore a una struttura.</span><span class="sxs-lookup"><span data-stu-id="1dff0-229">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>

<span data-ttu-id="1dff0-230">Nell'esempio SysTime viene usata la seguente funzione non gestita, illustrata con la dichiarazione di funzione originale:</span><span class="sxs-lookup"><span data-stu-id="1dff0-230">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="1dff0-231">**GetSystemTime** esportata da Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="1dff0-231">**GetSystemTime** exported from Kernel32.dll.</span></span>

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

<span data-ttu-id="1dff0-232">La struttura originale passata alla funzione contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1dff0-232">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="1dff0-233">In questo esempio la classe `SystemTime` contiene gli elementi della struttura originale rappresentati come membri di classe.</span><span class="sxs-lookup"><span data-stu-id="1dff0-233">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="1dff0-234">L'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> è impostato in modo da garantire che i membri vengano inseriti in memoria in sequenza, nell'ordine in cui appaiono.</span><span class="sxs-lookup"><span data-stu-id="1dff0-234">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="1dff0-235">La classe `NativeMethods` contiene un prototipo gestito del metodo `GetSystemTime`, che passa la classe `SystemTime` come parametro in/out per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1dff0-235">The `NativeMethods` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="1dff0-236">Il parametro deve essere dichiarato con gli attributi <xref:System.Runtime.InteropServices.InAttribute> e <xref:System.Runtime.InteropServices.OutAttribute> perché le classi, che sono tipi di riferimento, per impostazione predefinita vengono passate come parametri in.</span><span class="sxs-lookup"><span data-stu-id="1dff0-236">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="1dff0-237">Affinché il chiamante riceva i risultati, è necessario applicare questi [attributi direzionali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="1dff0-237">For the caller to receive the results, these [directional attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="1dff0-238">Con la classe `App` si crea una nuova istanza della classe `SystemTime` e si accede ai relativi campi di dati.</span><span class="sxs-lookup"><span data-stu-id="1dff0-238">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>

### <a name="code-samples"></a><span data-ttu-id="1dff0-239">Esempi di codice</span><span class="sxs-lookup"><span data-stu-id="1dff0-239">Code Samples</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a><span data-ttu-id="1dff0-240">OutArrayOfStructs (esempio)</span><span class="sxs-lookup"><span data-stu-id="1dff0-240">OutArrayOfStructs sample</span></span>

<span data-ttu-id="1dff0-241">In questo esempio viene illustrato come passare una matrice di strutture che contiene Integer e stringhe come parametri out a una funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="1dff0-241">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>

<span data-ttu-id="1dff0-242">L'esempio dimostra come chiamare una funzione nativa usando la classe <xref:System.Runtime.InteropServices.Marshal> e usando codice di tipo unsafe.</span><span class="sxs-lookup"><span data-stu-id="1dff0-242">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>

<span data-ttu-id="1dff0-243">Questo esempio usa funzioni wrapper e operazioni platform invoke definite in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), disponibili anche nei file di origine.</span><span class="sxs-lookup"><span data-stu-id="1dff0-243">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="1dff0-244">Vengono usate la funzione `TestOutArrayOfStructs` e la struttura `MYSTRSTRUCT2`.</span><span class="sxs-lookup"><span data-stu-id="1dff0-244">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="1dff0-245">La struttura contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1dff0-245">The structure contains the following elements:</span></span>

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

<span data-ttu-id="1dff0-246">La classe `MyStruct` contiene un oggetto stringa di caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="1dff0-246">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="1dff0-247">Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> specifica il formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="1dff0-247">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="1dff0-248">`MyUnsafeStruct` è una struttura contenente un tipo <xref:System.IntPtr> anziché una stringa.</span><span class="sxs-lookup"><span data-stu-id="1dff0-248">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>

<span data-ttu-id="1dff0-249">La classe `NativeMethods` contiene il metodo prototipo `TestOutArrayOfStructs` di overload.</span><span class="sxs-lookup"><span data-stu-id="1dff0-249">The `NativeMethods` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="1dff0-250">Se un metodo dichiara un puntatore come parametro, la classe deve essere contrassegnata con la parola chiave `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="1dff0-250">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="1dff0-251">Poiché Visual Basic non può usare codice unsafe, il metodo di overload, il modificatore unsafe e la struttura `MyUnsafeStruct` non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="1dff0-251">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>

<span data-ttu-id="1dff0-252">La `App` classe implementa il metodo `UsingMarshaling` che esegue tutte le attività necessarie per passare la matrice.</span><span class="sxs-lookup"><span data-stu-id="1dff0-252">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="1dff0-253">La matrice è contrassegnata con la parola chiave `out` (`ByRef` in Visual Basic) per indicare che i dati passano dal chiamato al chiamante.</span><span class="sxs-lookup"><span data-stu-id="1dff0-253">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="1dff0-254">L'implementazione usa i seguenti metodi della classe <xref:System.Runtime.InteropServices.Marshal>:</span><span class="sxs-lookup"><span data-stu-id="1dff0-254">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>

- <span data-ttu-id="1dff0-255"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> per il marshalling dei dati dal buffer non gestito a un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="1dff0-255"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>

- <span data-ttu-id="1dff0-256"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> per rilasciare la memoria riservata alle stringhe nella struttura.</span><span class="sxs-lookup"><span data-stu-id="1dff0-256"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>

- <span data-ttu-id="1dff0-257"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> per rilasciare la memoria riservata alla matrice.</span><span class="sxs-lookup"><span data-stu-id="1dff0-257"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>

<span data-ttu-id="1dff0-258">Come accennato in precedenza, C# consente il codice unsafe, mentre Visual Basic non lo consente.</span><span class="sxs-lookup"><span data-stu-id="1dff0-258">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="1dff0-259">Nell'esempio C#, `UsingUnsafePointer` è un'implementazione alternativa del metodo che usa puntatori anziché la classe <xref:System.Runtime.InteropServices.Marshal> per passare nuovamente la matrice che contiene la struttura `MyUnsafeStruct`.</span><span class="sxs-lookup"><span data-stu-id="1dff0-259">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="1dff0-260">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="1dff0-260">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a><span data-ttu-id="1dff0-261">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="1dff0-261">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a><span data-ttu-id="1dff0-262">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dff0-262">See also</span></span>

- [<span data-ttu-id="1dff0-263">Marshalling dei dati con platform invoke</span><span class="sxs-lookup"><span data-stu-id="1dff0-263">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="1dff0-264">Marshalling di stringhe</span><span class="sxs-lookup"><span data-stu-id="1dff0-264">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="1dff0-265">Marshalling di diversi tipi di matrici</span><span class="sxs-lookup"><span data-stu-id="1dff0-265">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)

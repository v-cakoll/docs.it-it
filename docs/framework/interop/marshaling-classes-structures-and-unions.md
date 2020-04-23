---
title: Marshalling di classi, strutture e unioni
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
ms.openlocfilehash: d761d8ed7488e99f29d4844d061867915a624b96
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960013"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="bd378-102">Marshalling di classi, strutture e unioni</span><span class="sxs-lookup"><span data-stu-id="bd378-102">Marshaling Classes, Structures, and Unions</span></span>

<span data-ttu-id="bd378-103">In .NET Framework classi e strutture sono simili.</span><span class="sxs-lookup"><span data-stu-id="bd378-103">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="bd378-104">Entrambe possono avere campi, proprietà ed eventi</span><span class="sxs-lookup"><span data-stu-id="bd378-104">Both can have fields, properties, and events.</span></span> <span data-ttu-id="bd378-105">nonché metodi statici e non statici.</span><span class="sxs-lookup"><span data-stu-id="bd378-105">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="bd378-106">Una differenza fondamentale è data dal fatto che le strutture sono tipi di valore e le classi sono tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="bd378-106">One notable difference is that structures are value types and classes are reference types.</span></span>

<span data-ttu-id="bd378-107">Nella tabella seguente sono elencate le opzioni di marshalling per le classi, le strutture e le unioni con la descrizione dell'utilizzo e un collegamento all'esempio corrispondente di platform invoke.</span><span class="sxs-lookup"><span data-stu-id="bd378-107">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>

|<span data-ttu-id="bd378-108">Type</span><span class="sxs-lookup"><span data-stu-id="bd378-108">Type</span></span>|<span data-ttu-id="bd378-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd378-109">Description</span></span>|<span data-ttu-id="bd378-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd378-110">Sample</span></span>|
|----------|-----------------|------------|
|<span data-ttu-id="bd378-111">Classe per valore.</span><span class="sxs-lookup"><span data-stu-id="bd378-111">Class by value.</span></span>|<span data-ttu-id="bd378-112">Passa una classe con membri Integer come parametro in/out, come il case gestito.</span><span class="sxs-lookup"><span data-stu-id="bd378-112">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|[<span data-ttu-id="bd378-113">SysTime (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-113">SysTime sample</span></span>](#systime-sample)|
|<span data-ttu-id="bd378-114">Struttura per valore.</span><span class="sxs-lookup"><span data-stu-id="bd378-114">Structure by value.</span></span>|<span data-ttu-id="bd378-115">Passa le strutture come parametri in.</span><span class="sxs-lookup"><span data-stu-id="bd378-115">Passes structures as In parameters.</span></span>|[<span data-ttu-id="bd378-116">Structures (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-116">Structures sample</span></span>](#structures-sample)|
|<span data-ttu-id="bd378-117">Struttura per riferimento.</span><span class="sxs-lookup"><span data-stu-id="bd378-117">Structure by reference.</span></span>|<span data-ttu-id="bd378-118">Passa le strutture come parametri in/out.</span><span class="sxs-lookup"><span data-stu-id="bd378-118">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="bd378-119">[OSInfo (esempio)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bd378-119">[OSInfo sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span></span>|
|<span data-ttu-id="bd378-120">Struttura con strutture annidate (semplificata).</span><span class="sxs-lookup"><span data-stu-id="bd378-120">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="bd378-121">Passa una classe che rappresenta una struttura con strutture annidate nella funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="bd378-121">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="bd378-122">La struttura viene semplificata in una sola grande struttura nel prototipo gestito.</span><span class="sxs-lookup"><span data-stu-id="bd378-122">The structure is flattened to one big structure in the managed prototype.</span></span>|[<span data-ttu-id="bd378-123">FindFile (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-123">FindFile sample</span></span>](#findfile-sample)|
|<span data-ttu-id="bd378-124">Struttura con puntatore a un'altra struttura.</span><span class="sxs-lookup"><span data-stu-id="bd378-124">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="bd378-125">Passa una struttura che contiene un puntatore a una seconda struttura come membro.</span><span class="sxs-lookup"><span data-stu-id="bd378-125">Passes a structure that contains a pointer to a second structure as a member.</span></span>|[<span data-ttu-id="bd378-126">Esempio di strutture</span><span class="sxs-lookup"><span data-stu-id="bd378-126">Structures Sample</span></span>](#structures-sample)|
|<span data-ttu-id="bd378-127">Matrice di strutture con Integer per valore.</span><span class="sxs-lookup"><span data-stu-id="bd378-127">Array of structures with integers by value.</span></span>|<span data-ttu-id="bd378-128">Passa una matrice di strutture che contengono solo Integer come un parametro in/out.</span><span class="sxs-lookup"><span data-stu-id="bd378-128">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="bd378-129">È possibile modificare i membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="bd378-129">Members of the array can be changed.</span></span>|[<span data-ttu-id="bd378-130">Arrays (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-130">Arrays Sample</span></span>](marshaling-different-types-of-arrays.md)|
|<span data-ttu-id="bd378-131">Matrice di strutture con Integer e stringhe per riferimento.</span><span class="sxs-lookup"><span data-stu-id="bd378-131">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="bd378-132">Passa una matrice di strutture che contengono Integer e stringhe come un parametro out.</span><span class="sxs-lookup"><span data-stu-id="bd378-132">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="bd378-133">La memoria per la matrice viene allocata dalla funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="bd378-133">The called function allocates memory for the array.</span></span>|[<span data-ttu-id="bd378-134">Esempio OutArrayOfStructs (</span><span class="sxs-lookup"><span data-stu-id="bd378-134">OutArrayOfStructs Sample</span></span>](#outarrayofstructs-sample)|
|<span data-ttu-id="bd378-135">Unioni con tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="bd378-135">Unions with value types.</span></span>|<span data-ttu-id="bd378-136">Passa le unioni con tipi di valore (Integer e Double).</span><span class="sxs-lookup"><span data-stu-id="bd378-136">Passes unions with value types (integer and double).</span></span>|[<span data-ttu-id="bd378-137">unioni (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-137">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="bd378-138">Unioni con tipi misti.</span><span class="sxs-lookup"><span data-stu-id="bd378-138">Unions with mixed types.</span></span>|<span data-ttu-id="bd378-139">Passa unioni con tipi misti (Integer e String).</span><span class="sxs-lookup"><span data-stu-id="bd378-139">Passes unions with mixed types (integer and string).</span></span>|[<span data-ttu-id="bd378-140">unioni (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-140">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="bd378-141">Valori null nella struttura.</span><span class="sxs-lookup"><span data-stu-id="bd378-141">Null values in structure.</span></span>|<span data-ttu-id="bd378-142">Passa un riferimento null (**Nothing** in Visual Basic) invece di un riferimento a un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="bd378-142">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="bd378-143">[HandleRef (esempio)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="bd378-143">[HandleRef sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span></span>|

## <a name="structures-sample"></a><span data-ttu-id="bd378-144">Structures (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-144">Structures sample</span></span>

<span data-ttu-id="bd378-145">In questo esempio viene dimostrato come passare una struttura che punta a una seconda struttura, una struttura con una struttura incorporata e una struttura con una matrice incorporata.</span><span class="sxs-lookup"><span data-stu-id="bd378-145">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
<span data-ttu-id="bd378-146">Nell'esempio di strutture vengono usate le seguenti funzioni non gestite, illustrate con le dichiarazioni di funzione originali:</span><span class="sxs-lookup"><span data-stu-id="bd378-146">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="bd378-147">**TestStructInStruct** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="bd378-147">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- <span data-ttu-id="bd378-148">**TestStructInStruct3** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="bd378-148">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- <span data-ttu-id="bd378-149">**TestArrayInStruct** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="bd378-149">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

<span data-ttu-id="bd378-150">[PinvokeLib](marshaling-data-with-platform-invoke.md#pinvokelibdll) è una libreria non gestita personalizzata contenente implementazioni per le funzioni elencate in precedenza e quattro strutture, ovvero: **MYPERSON**, **MYPERSON2**, **MYPERSON3** e **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="bd378-150">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="bd378-151">Le strutture contengono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd378-151">These structures contain the following elements:</span></span>

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

<span data-ttu-id="bd378-152">Le strutture gestite `MyPerson`,`MyPerson2`, `MyPerson3` e `MyArrayStruct` hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd378-152">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>

- <span data-ttu-id="bd378-153">`MyPerson` contiene solo membri stringa.</span><span class="sxs-lookup"><span data-stu-id="bd378-153">`MyPerson` contains only string members.</span></span> <span data-ttu-id="bd378-154">Le stringhe vengono impostate sul formato ANSI dal campo [CharSet](specifying-a-character-set.md), quando viene passato alla funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="bd378-154">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>

- <span data-ttu-id="bd378-155">`MyPerson2`contiene un oggetto **IntPtr** per `MyPerson` la struttura.</span><span class="sxs-lookup"><span data-stu-id="bd378-155">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="bd378-156">Il tipo **IntPtr** sostituisce il puntatore originale alla struttura non gestita poiché nelle applicazioni .NET Framework non vengono usati i puntatori a meno che il codice non sia contrassegnato come **unsafe**.</span><span class="sxs-lookup"><span data-stu-id="bd378-156">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>

- <span data-ttu-id="bd378-157">`MyPerson3` contiene `MyPerson` come struttura incorporata.</span><span class="sxs-lookup"><span data-stu-id="bd378-157">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="bd378-158">È possibile semplificare una struttura incorporata in un'altra struttura posizionandone gli elementi direttamente nella struttura principale oppure mantenerla incorporata, come accade in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="bd378-158">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>

- <span data-ttu-id="bd378-159">`MyArrayStruct` contiene una matrice di Integer.</span><span class="sxs-lookup"><span data-stu-id="bd378-159">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="bd378-160">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> imposta il valore di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> su **ByValArray**, che consente di indicare il numero di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="bd378-160">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>

<span data-ttu-id="bd378-161">Per tutte le strutture di questo esempio, l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> viene applicato in modo che i membri vengano disposti in sequenza nella memoria, nell'ordine in cui appaiono.</span><span class="sxs-lookup"><span data-stu-id="bd378-161">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="bd378-162">La classe `NativeMethods` contiene prototipi gestiti per i metodi `TestStructInStruct`, `TestStructInStruct3` e `TestArrayInStruct` chiamati dalla classe `App`.</span><span class="sxs-lookup"><span data-stu-id="bd378-162">The `NativeMethods` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="bd378-163">Ciascun prototipo dichiara un singolo parametro, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bd378-163">Each prototype declares a single parameter, as follows:</span></span>

- <span data-ttu-id="bd378-164">`TestStructInStruct` dichiara un riferimento al tipo `MyPerson2` come parametro.</span><span class="sxs-lookup"><span data-stu-id="bd378-164">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>

- <span data-ttu-id="bd378-165">`TestStructInStruct3` dichiara il tipo `MyPerson3` come parametro e passa il parametro per valore.</span><span class="sxs-lookup"><span data-stu-id="bd378-165">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>

- <span data-ttu-id="bd378-166">`TestArrayInStruct` dichiara un riferimento al tipo `MyArrayStruct` come parametro.</span><span class="sxs-lookup"><span data-stu-id="bd378-166">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>

<span data-ttu-id="bd378-167">Come argomenti per i metodi, le strutture vengono passate per valore a meno che il parametro non contenga la parola chiave **ref** (**ByRef** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="bd378-167">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="bd378-168">Ad esempio, il metodo `TestStructInStruct` passa un riferimento, ossia il valore di un indirizzo, a un oggetto di tipo `MyPerson2` al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="bd378-168">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="bd378-169">Per modificare la struttura alla quale punta `MyPerson2`, nell'esempio viene creato un buffer di dimensioni specificate e ne viene restituito l'indirizzo combinando i metodi <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> e <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bd378-169">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="bd378-170">In seguito, il contenuto della struttura gestita viene copiato nel buffer non gestito.</span><span class="sxs-lookup"><span data-stu-id="bd378-170">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="bd378-171">Infine, il metodo <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> viene usato per effettuare il marshalling dei dati dal buffer non gestito in un oggetto gestito, mentre il metodo <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> viene usato per liberare il blocco di memoria non gestito.</span><span class="sxs-lookup"><span data-stu-id="bd378-171">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="bd378-172">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="bd378-172">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a><span data-ttu-id="bd378-173">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="bd378-173">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a><span data-ttu-id="bd378-174">FindFile (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-174">FindFile sample</span></span>

<span data-ttu-id="bd378-175">In questo esempio viene illustrato come passare una struttura che contiene una seconda struttura incorporata a una funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="bd378-175">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="bd378-176">Viene inoltre illustrato come usare l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> per dichiarare una matrice a lunghezza fissa all'interno della struttura.</span><span class="sxs-lookup"><span data-stu-id="bd378-176">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="bd378-177">Nell'esempio gli elementi della struttura incorporata vengono aggiunti alla struttura padre.</span><span class="sxs-lookup"><span data-stu-id="bd378-177">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="bd378-178">Per un esempio di struttura incorporata non appiattita, vedere [Esempio di strutture](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bd378-178">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>

<span data-ttu-id="bd378-179">Nell'esempio FindFile viene usata la seguente funzione non gestita, illustrata con la relativa dichiarazione di funzione originale:</span><span class="sxs-lookup"><span data-stu-id="bd378-179">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="bd378-180">**FindFirstFile** esportata da Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="bd378-180">**FindFirstFile** exported from Kernel32.dll.</span></span>

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

<span data-ttu-id="bd378-181">La struttura originale passata alla funzione contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd378-181">The original structure passed to the function contains the following elements:</span></span>

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

<span data-ttu-id="bd378-182">In questo esempio, la classe `FindData` contiene un membro dati corrispondente per ogni elemento della struttura originale e della struttura incorporata.</span><span class="sxs-lookup"><span data-stu-id="bd378-182">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="bd378-183">Al posto di due buffer di caratteri originali, la classe usa delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="bd378-183">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="bd378-184">**MarshalAsAttribute** imposta l'enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> su **ByValTStr**, che consente di identificare le matrici di caratteri inline a lunghezza fissa visualizzate all'interno delle strutture non gestite.</span><span class="sxs-lookup"><span data-stu-id="bd378-184">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>

<span data-ttu-id="bd378-185">La classe `NativeMethods` contiene un prototipo gestito del metodo `FindFirstFile`, che passa la classe `FindData` come parametro.</span><span class="sxs-lookup"><span data-stu-id="bd378-185">The `NativeMethods` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="bd378-186">Il parametro deve essere dichiarato con gli attributi <xref:System.Runtime.InteropServices.InAttribute> e <xref:System.Runtime.InteropServices.OutAttribute> perché le classi, che sono tipi di riferimento, per impostazione predefinita vengono passate come parametri in.</span><span class="sxs-lookup"><span data-stu-id="bd378-186">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="bd378-187">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="bd378-187">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a><span data-ttu-id="bd378-188">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="bd378-188">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a><span data-ttu-id="bd378-189">unioni (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-189">Unions sample</span></span>

<span data-ttu-id="bd378-190">In questo esempio viene dimostrato come passare le strutture contenenti solo tipi di valore e le strutture contenenti un tipo di valore e una stringa come parametri a una funzione non gestita per la quale è prevista un'unione.</span><span class="sxs-lookup"><span data-stu-id="bd378-190">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="bd378-191">Un'unione rappresenta un percorso di memoria che può essere condiviso da due o più variabili.</span><span class="sxs-lookup"><span data-stu-id="bd378-191">A union represents a memory location that can be shared by two or more variables.</span></span>

<span data-ttu-id="bd378-192">Nell'esempio di unioni viene usata la seguente funzione non gestita, illustrata con la dichiarazione di funzione originale:</span><span class="sxs-lookup"><span data-stu-id="bd378-192">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="bd378-193">**TestUnion** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="bd378-193">**TestUnion** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

<span data-ttu-id="bd378-194">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) è una libreria non gestita personalizzata contenente un'implementazione per la funzione elencata in precedenza e due unioni, **MYUNION** e **MYUNION2**.</span><span class="sxs-lookup"><span data-stu-id="bd378-194">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="bd378-195">Le unioni contengono i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="bd378-195">The unions contain the following elements:</span></span>

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

<span data-ttu-id="bd378-196">Nel codice gestito, le unioni sono definite come strutture.</span><span class="sxs-lookup"><span data-stu-id="bd378-196">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="bd378-197">La struttura `MyUnion` contiene due tipi di valore come membri, ovvero un Integer e un Double.</span><span class="sxs-lookup"><span data-stu-id="bd378-197">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="bd378-198">L'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> è impostato in modo da controllare l'esatta posizione di ciascun membro dati.</span><span class="sxs-lookup"><span data-stu-id="bd378-198">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="bd378-199">L'attributo <xref:System.Runtime.InteropServices.FieldOffsetAttribute> fornisce la posizione fisica dei campi all'interno della rappresentazione non gestita di un'unione.</span><span class="sxs-lookup"><span data-stu-id="bd378-199">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="bd378-200">Poiché entrambi hanno gli stessi valori di offset, i membri possono definire la stessa porzione di memoria.</span><span class="sxs-lookup"><span data-stu-id="bd378-200">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>

<span data-ttu-id="bd378-201">`MyUnion2_1` e `MyUnion2_2` contengono rispettivamente un tipo di valore (Integer) e una stringa.</span><span class="sxs-lookup"><span data-stu-id="bd378-201">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="bd378-202">Nel codice gestito i tipi di valore e quelli di riferimento non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="bd378-202">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="bd378-203">In questo esempio l'overload dei metodi consente al chiamante di usare entrambi i tipi nella chiamata alla stessa funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="bd378-203">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="bd378-204">Il layout di `MyUnion2_1` è esplicito e ha un valore di offset preciso.</span><span class="sxs-lookup"><span data-stu-id="bd378-204">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="bd378-205">Al contrario, `MyUnion2_2` ha un layout sequenziale, poiché i layout espliciti non sono consentiti con i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="bd378-205">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="bd378-206">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> impostazione l'enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> su **ByValTStr**, che consente di identificare le matrici di caratteri inline a lunghezza fissa presenti nella rappresentazione non gestita dell'unione.</span><span class="sxs-lookup"><span data-stu-id="bd378-206">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>

<span data-ttu-id="bd378-207">La classe `NativeMethods` contiene i prototipi per i metodi `TestUnion` e `TestUnion2`.</span><span class="sxs-lookup"><span data-stu-id="bd378-207">The `NativeMethods` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="bd378-208">`TestUnion2` viene sottoposto a overload allo scopo di dichiarare `MyUnion2_1` o `MyUnion2_2` come parametri.</span><span class="sxs-lookup"><span data-stu-id="bd378-208">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="bd378-209">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="bd378-209">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a><span data-ttu-id="bd378-210">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="bd378-210">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="systime-sample"></a><span data-ttu-id="bd378-211">SysTime (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-211">SysTime sample</span></span>

<span data-ttu-id="bd378-212">In questo esempio viene dimostrato come passare un puntatore a una classe a una funzione non gestita per la quale è previsto un puntatore a una struttura.</span><span class="sxs-lookup"><span data-stu-id="bd378-212">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>

<span data-ttu-id="bd378-213">Nell'esempio SysTime viene usata la seguente funzione non gestita, illustrata con la dichiarazione di funzione originale:</span><span class="sxs-lookup"><span data-stu-id="bd378-213">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="bd378-214">**GetSystemTime** esportata da Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="bd378-214">**GetSystemTime** exported from Kernel32.dll.</span></span>

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

<span data-ttu-id="bd378-215">La struttura originale passata alla funzione contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd378-215">The original structure passed to the function contains the following elements:</span></span>

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

<span data-ttu-id="bd378-216">In questo esempio la classe `SystemTime` contiene gli elementi della struttura originale rappresentati come membri di classe.</span><span class="sxs-lookup"><span data-stu-id="bd378-216">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="bd378-217">L'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> è impostato in modo da garantire che i membri vengano inseriti in memoria in sequenza, nell'ordine in cui appaiono.</span><span class="sxs-lookup"><span data-stu-id="bd378-217">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="bd378-218">La classe `NativeMethods` contiene un prototipo gestito del metodo `GetSystemTime`, che passa la classe `SystemTime` come parametro in/out per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bd378-218">The `NativeMethods` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="bd378-219">Il parametro deve essere dichiarato con gli attributi <xref:System.Runtime.InteropServices.InAttribute> e <xref:System.Runtime.InteropServices.OutAttribute> perché le classi, che sono tipi di riferimento, per impostazione predefinita vengono passate come parametri in.</span><span class="sxs-lookup"><span data-stu-id="bd378-219">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="bd378-220">Affinché il chiamante riceva i risultati, è necessario applicare questi [attributi direzionali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="bd378-220">For the caller to receive the results, these [directional attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="bd378-221">Con la classe `App` si crea una nuova istanza della classe `SystemTime` e si accede ai relativi campi di dati.</span><span class="sxs-lookup"><span data-stu-id="bd378-221">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>

### <a name="code-samples"></a><span data-ttu-id="bd378-222">Esempi di codice</span><span class="sxs-lookup"><span data-stu-id="bd378-222">Code Samples</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a><span data-ttu-id="bd378-223">OutArrayOfStructs (esempio)</span><span class="sxs-lookup"><span data-stu-id="bd378-223">OutArrayOfStructs sample</span></span>

<span data-ttu-id="bd378-224">In questo esempio viene illustrato come passare una matrice di strutture che contiene Integer e stringhe come parametri out a una funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="bd378-224">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>

<span data-ttu-id="bd378-225">L'esempio dimostra come chiamare una funzione nativa usando la classe <xref:System.Runtime.InteropServices.Marshal> e usando codice di tipo unsafe.</span><span class="sxs-lookup"><span data-stu-id="bd378-225">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>

<span data-ttu-id="bd378-226">Questo esempio usa funzioni wrapper e operazioni platform invoke definite in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), disponibili anche nei file di origine.</span><span class="sxs-lookup"><span data-stu-id="bd378-226">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="bd378-227">Vengono usate la funzione `TestOutArrayOfStructs` e la struttura `MYSTRSTRUCT2`.</span><span class="sxs-lookup"><span data-stu-id="bd378-227">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="bd378-228">La struttura contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd378-228">The structure contains the following elements:</span></span>

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

<span data-ttu-id="bd378-229">La classe `MyStruct` contiene un oggetto stringa di caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="bd378-229">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="bd378-230">Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> specifica il formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="bd378-230">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="bd378-231">`MyUnsafeStruct` è una struttura contenente un tipo <xref:System.IntPtr> anziché una stringa.</span><span class="sxs-lookup"><span data-stu-id="bd378-231">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>

<span data-ttu-id="bd378-232">La classe `NativeMethods` contiene il metodo prototipo `TestOutArrayOfStructs` di overload.</span><span class="sxs-lookup"><span data-stu-id="bd378-232">The `NativeMethods` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="bd378-233">Se un metodo dichiara un puntatore come parametro, la classe deve essere contrassegnata con la parola chiave `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="bd378-233">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="bd378-234">Poiché Visual Basic non può usare codice unsafe, il metodo di overload, il modificatore unsafe e la struttura `MyUnsafeStruct` non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="bd378-234">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>

<span data-ttu-id="bd378-235">La `App` classe implementa il metodo `UsingMarshaling` che esegue tutte le attività necessarie per passare la matrice.</span><span class="sxs-lookup"><span data-stu-id="bd378-235">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="bd378-236">La matrice è contrassegnata con la parola chiave `out` (`ByRef` in Visual Basic) per indicare che i dati passano dal chiamato al chiamante.</span><span class="sxs-lookup"><span data-stu-id="bd378-236">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="bd378-237">L'implementazione usa i seguenti metodi della classe <xref:System.Runtime.InteropServices.Marshal>:</span><span class="sxs-lookup"><span data-stu-id="bd378-237">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>

- <span data-ttu-id="bd378-238"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> per il marshalling dei dati dal buffer non gestito a un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="bd378-238"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>

- <span data-ttu-id="bd378-239"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> per rilasciare la memoria riservata alle stringhe nella struttura.</span><span class="sxs-lookup"><span data-stu-id="bd378-239"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>

- <span data-ttu-id="bd378-240"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> per rilasciare la memoria riservata alla matrice.</span><span class="sxs-lookup"><span data-stu-id="bd378-240"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>

<span data-ttu-id="bd378-241">Come accennato in precedenza, C# consente il codice unsafe, mentre Visual Basic non lo consente.</span><span class="sxs-lookup"><span data-stu-id="bd378-241">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="bd378-242">Nell'esempio C#, `UsingUnsafePointer` è un'implementazione alternativa del metodo che usa puntatori anziché la classe <xref:System.Runtime.InteropServices.Marshal> per passare nuovamente la matrice che contiene la struttura `MyUnsafeStruct`.</span><span class="sxs-lookup"><span data-stu-id="bd378-242">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="bd378-243">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="bd378-243">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a><span data-ttu-id="bd378-244">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="bd378-244">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a><span data-ttu-id="bd378-245">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd378-245">See also</span></span>

- [<span data-ttu-id="bd378-246">Marshalling dei dati con platform invoke</span><span class="sxs-lookup"><span data-stu-id="bd378-246">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="bd378-247">Marshalling di stringhe</span><span class="sxs-lookup"><span data-stu-id="bd378-247">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="bd378-248">Marshalling di diversi tipi di matrici</span><span class="sxs-lookup"><span data-stu-id="bd378-248">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)

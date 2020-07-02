---
title: Marshalling predefinito per le matrici
description: Informazioni sul marshalling predefinito per le matrici. Esaminare matrici gestite, matrici non gestite, passare parametri di matrici al codice .NET e passare matrici a COM.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
ms.openlocfilehash: eafed0e0a0150923aae0fa68a1b96e6d9d66b07a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622562"
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="471d1-104">Marshalling predefinito per le matrici</span><span class="sxs-lookup"><span data-stu-id="471d1-104">Default Marshaling for Arrays</span></span>
<span data-ttu-id="471d1-105">In un'applicazione costituita interamente da codice gestito Common Language Runtime passa i tipi di matrice come parametri In/Out.</span><span class="sxs-lookup"><span data-stu-id="471d1-105">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="471d1-106">Il gestore di marshalling di interoperabilità invece passa una matrice come parametro In per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="471d1-106">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="471d1-107">Con l'[ottimizzazione del blocco](copying-and-pinning.md), può sembrare che una matrice copiabile da BLT funzioni come parametro In/Out quando interagisce con oggetti nello stesso apartment.</span><span class="sxs-lookup"><span data-stu-id="471d1-107">With [pinning optimization](copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="471d1-108">Se tuttavia in seguito si esporta il codice in una libreria dei tipi usata per generare il proxy tra computer e la libreria viene usata per effettuare il marshalling delle chiamate tra gli apartment, le chiamate possono ripristinare il vero e proprio comportamento del parametro In.</span><span class="sxs-lookup"><span data-stu-id="471d1-108">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="471d1-109">Le matrici sono complesse per natura e le distinzioni tra matrici gestite e non gestite richiedono più informazioni degli altri tipi non copiabili da BLT.</span><span class="sxs-lookup"><span data-stu-id="471d1-109">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span>  
  
## <a name="managed-arrays"></a><span data-ttu-id="471d1-110">Matrici gestite</span><span class="sxs-lookup"><span data-stu-id="471d1-110">Managed Arrays</span></span>  
 <span data-ttu-id="471d1-111">I tipi di matrici gestite possono variare, ma la classe <xref:System.Array?displayProperty=nameWithType> è la classe base di tutti i tipi di matrici.</span><span class="sxs-lookup"><span data-stu-id="471d1-111">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="471d1-112">La classe **System.Array** ha proprietà per determinare priorità, lunghezza e limiti inferiori e superiori di una matrice, oltre a metodi per accedere, ordinare, cercare, copiare e creare matrici.</span><span class="sxs-lookup"><span data-stu-id="471d1-112">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="471d1-113">Questi tipi di matrici sono dinamici e non devono avere un tipo statico corrispondente definito nella libreria di classi base.</span><span class="sxs-lookup"><span data-stu-id="471d1-113">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="471d1-114">È utile considerare ogni combinazione di tipo di elemento e priorità come un tipo distinto di matrice.</span><span class="sxs-lookup"><span data-stu-id="471d1-114">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="471d1-115">Una matrice unidimensionale di integer è quindi di un tipo diverso da una matrice unidimensionale di tipi double.</span><span class="sxs-lookup"><span data-stu-id="471d1-115">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="471d1-116">Analogamente una matrice bidimensionale di integer è diversa da una matrice unidimensionale di integer.</span><span class="sxs-lookup"><span data-stu-id="471d1-116">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="471d1-117">I limiti della matrice non vengono considerati quando si confrontano i tipi.</span><span class="sxs-lookup"><span data-stu-id="471d1-117">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="471d1-118">Come illustra la tabella seguente, tutte le istanze di una matrice gestita devono essere di uno specifico tipo di elemento, priorità e limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="471d1-118">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="471d1-119">Tipo di matrice gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-119">Managed array type</span></span>|<span data-ttu-id="471d1-120">Tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="471d1-120">Element type</span></span>|<span data-ttu-id="471d1-121">Classifica</span><span class="sxs-lookup"><span data-stu-id="471d1-121">Rank</span></span>|<span data-ttu-id="471d1-122">Limite inferiore</span><span class="sxs-lookup"><span data-stu-id="471d1-122">Lower bound</span></span>|<span data-ttu-id="471d1-123">Notazione della firma</span><span class="sxs-lookup"><span data-stu-id="471d1-123">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="471d1-124">**ELEMENT_TYPE_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="471d1-124">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="471d1-125">Specificato dal tipo.</span><span class="sxs-lookup"><span data-stu-id="471d1-125">Specified by type.</span></span>|<span data-ttu-id="471d1-126">Specificata dalla priorità.</span><span class="sxs-lookup"><span data-stu-id="471d1-126">Specified by rank.</span></span>|<span data-ttu-id="471d1-127">Specificato facoltativamente dai limiti.</span><span class="sxs-lookup"><span data-stu-id="471d1-127">Optionally specified by bounds.</span></span>|<span data-ttu-id="471d1-128">*tipo* **[** *n*,*m* **]**</span><span class="sxs-lookup"><span data-stu-id="471d1-128">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="471d1-129">**ELEMENT_TYPE_CLASS**</span><span class="sxs-lookup"><span data-stu-id="471d1-129">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="471d1-130">Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="471d1-130">Unknown</span></span>|<span data-ttu-id="471d1-131">Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="471d1-131">Unknown</span></span>|<span data-ttu-id="471d1-132">Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="471d1-132">Unknown</span></span>|<span data-ttu-id="471d1-133">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="471d1-133">**System.Array**</span></span>|  
|<span data-ttu-id="471d1-134">**ELEMENT_TYPE_SZARRAY**</span><span class="sxs-lookup"><span data-stu-id="471d1-134">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="471d1-135">Specificato dal tipo.</span><span class="sxs-lookup"><span data-stu-id="471d1-135">Specified by type.</span></span>|<span data-ttu-id="471d1-136">1</span><span class="sxs-lookup"><span data-stu-id="471d1-136">1</span></span>|<span data-ttu-id="471d1-137">0</span><span class="sxs-lookup"><span data-stu-id="471d1-137">0</span></span>|<span data-ttu-id="471d1-138">*tipo* **[** *n* **]**</span><span class="sxs-lookup"><span data-stu-id="471d1-138">*type* **[** *n* **]**</span></span>|  
  
## <a name="unmanaged-arrays"></a><span data-ttu-id="471d1-139">Matrici non gestite</span><span class="sxs-lookup"><span data-stu-id="471d1-139">Unmanaged Arrays</span></span>  
 <span data-ttu-id="471d1-140">Le matrici non gestite sono matrici protette di tipo COM o matrici di tipo C con lunghezza fissa o variabile.</span><span class="sxs-lookup"><span data-stu-id="471d1-140">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="471d1-141">Le matrici protette sono matrici autodescrittive che contengono il tipo, la priorità e i limiti dei dati della matrice associati.</span><span class="sxs-lookup"><span data-stu-id="471d1-141">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="471d1-142">Le matrici di tipo C sono matrici tipizzate unidimensionali con un limite inferiore fisso pari a 0.</span><span class="sxs-lookup"><span data-stu-id="471d1-142">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="471d1-143">Il servizio di marshalling ha un supporto limitato per entrambi i tipi di matrici.</span><span class="sxs-lookup"><span data-stu-id="471d1-143">The marshaling service has limited support for both types of arrays.</span></span>  
  
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="471d1-144">Passaggio dei parametri delle matrici al codice .NET</span><span class="sxs-lookup"><span data-stu-id="471d1-144">Passing Array Parameters to .NET Code</span></span>  
 <span data-ttu-id="471d1-145">Sia le matrici di tipo C che le matrici protette possono essere passate al codice .NET dal codice non gestito come matrice protetta o matrice di tipo C.</span><span class="sxs-lookup"><span data-stu-id="471d1-145">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="471d1-146">La tabella seguente illustra il valore del tipo non gestito e il tipo importato.</span><span class="sxs-lookup"><span data-stu-id="471d1-146">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="471d1-147">Tipo non gestito</span><span class="sxs-lookup"><span data-stu-id="471d1-147">Unmanaged type</span></span>|<span data-ttu-id="471d1-148">Tipo importato</span><span class="sxs-lookup"><span data-stu-id="471d1-148">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="471d1-149">**SAFEARRAY (** *tipo* **)**</span><span class="sxs-lookup"><span data-stu-id="471d1-149">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="471d1-150">**ELEMENT_TYPE_SZARRAY\*\*\*\*\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="471d1-150">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="471d1-151">Priorità = 1, limite inferiore = 0.</span><span class="sxs-lookup"><span data-stu-id="471d1-151">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="471d1-152">La dimensione è nota solo se specificata nella firma gestita.</span><span class="sxs-lookup"><span data-stu-id="471d1-152">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="471d1-153">Non è possibile effettuare il marshalling delle matrici protette che non hanno priorità = 1 o limite inferiore = 0 come **SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="471d1-153">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="471d1-154">*Tipo*  **[]**</span><span class="sxs-lookup"><span data-stu-id="471d1-154">*Type*  **[]**</span></span>|<span data-ttu-id="471d1-155">**ELEMENT_TYPE_SZARRAY\*\*\*\*\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="471d1-155">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="471d1-156">Priorità = 1, limite inferiore = 0.</span><span class="sxs-lookup"><span data-stu-id="471d1-156">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="471d1-157">La dimensione è nota solo se specificata nella firma gestita.</span><span class="sxs-lookup"><span data-stu-id="471d1-157">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="471d1-158">Matrici protette</span><span class="sxs-lookup"><span data-stu-id="471d1-158">Safe Arrays</span></span>  
 <span data-ttu-id="471d1-159">Quando una matrice protetta viene importata da una libreria dei tipi in un assembly .NET, la matrice viene convertita in una matrice unidimensionale di tipo noto (ad esempio, **int**).</span><span class="sxs-lookup"><span data-stu-id="471d1-159">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="471d1-160">Le stesse regole di conversione del tipo applicate ai parametri si applicano anche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="471d1-160">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="471d1-161">Una matrice protetta di tipi **BSTR**, ad esempio, diventa una matrice gestita di stringhe e una matrice protetta di varianti diventa una matrice gestita di oggetti.</span><span class="sxs-lookup"><span data-stu-id="471d1-161">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="471d1-162">Il tipo di elemento **SAFEARRAY** viene acquisito dalla libreria dei tipi e salvato nel valore **SAFEARRAY** dell'enumerazione <xref:System.Runtime.InteropServices.UnmanagedType>.</span><span class="sxs-lookup"><span data-stu-id="471d1-162">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="471d1-163">Poiché la priorità e i limiti della matrice protetta non possono essere determinati dalla libreria dei tipi, si presuppone che la priorità sia pari a 1 e che il limite inferiore sia pari a 0.</span><span class="sxs-lookup"><span data-stu-id="471d1-163">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="471d1-164">La priorità e i limiti devono essere definiti nella firma gestita prodotta dall'[utilità di importazione della libreria dei tipi (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="471d1-164">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="471d1-165">Se la priorità passata al metodo in fase di esecuzione è diversa, viene generata un'eccezione <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="471d1-165">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="471d1-166">Se il tipo della matrice passata in fase di esecuzione è diverso, viene generata un'eccezione <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="471d1-166">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="471d1-167">L'esempio seguente illustra le matrici protette nel codice gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="471d1-167">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="471d1-168">**Firma non gestita**</span><span class="sxs-lookup"><span data-stu-id="471d1-168">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="471d1-169">**Firma gestita**</span><span class="sxs-lookup"><span data-stu-id="471d1-169">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]
   ref String[] ar);  
```  
  
 <span data-ttu-id="471d1-170">È possibile effettuare il marshalling delle matrici protette multidimensionali, o con limiti diversi da zero, nel codice gestito se la firma del metodo prodotta da Tlbimp.exe viene modificata per indicare un tipo di elemento **ELEMENT_TYPE_ARRAY** invece di **ELEMENT_TYPE_SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="471d1-170">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="471d1-171">In alternativa, è possibile usare l'opzione **/sysarray** con Tlbimp.exe per importare tutte le matrici come oggetti <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="471d1-171">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="471d1-172">Nei casi in cui la matrice passata è multidimensionale, è possibile modificare il codice Microsoft Intermediate Language (MSIL) prodotto da Tlbimp.exe e quindi ricompilarla.</span><span class="sxs-lookup"><span data-stu-id="471d1-172">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="471d1-173">Per informazioni dettagliate su come modificare il codice MSIL, vedere [Personalizzazione dei Runtime Callable Wrapper](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="471d1-173">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="471d1-174">Matrici di tipo C</span><span class="sxs-lookup"><span data-stu-id="471d1-174">C-Style Arrays</span></span>  
 <span data-ttu-id="471d1-175">Quando una matrice di tipo C viene importata da una libreria dei tipi in un assembly .NET, la matrice viene convertita in **ELEMENT_TYPE_SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="471d1-175">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="471d1-176">Il tipo di elemento della matrice è determinato dalla libreria dei tipi e mantenuto durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="471d1-176">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="471d1-177">Le stesse regole di conversione applicate ai parametri si applicano anche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="471d1-177">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="471d1-178">Ad esempio, una matrice di tipi **LPStr** diventa una matrice di tipi **String**.</span><span class="sxs-lookup"><span data-stu-id="471d1-178">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="471d1-179">Tlbimp.exe acquisisce il tipo di elemento della matrice e applica l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parametro.</span><span class="sxs-lookup"><span data-stu-id="471d1-179">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="471d1-180">Si presuppone che la priorità della matrice sia uguale a 1.</span><span class="sxs-lookup"><span data-stu-id="471d1-180">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="471d1-181">Se la priorità è superiore a 1, la matrice viene sottoposta a marshalling come matrice unidimensionale in ordine column-major.</span><span class="sxs-lookup"><span data-stu-id="471d1-181">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="471d1-182">Il limite inferiore è sempre uguale a 0.</span><span class="sxs-lookup"><span data-stu-id="471d1-182">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="471d1-183">Le librerie dei tipi possono contenere matrici a lunghezza fissa o variabile.</span><span class="sxs-lookup"><span data-stu-id="471d1-183">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="471d1-184">Tlbimp.exe può importare solo matrici a lunghezza fissa dalle librerie dei tipi perché le librerie dei tipi sono prive delle informazioni necessarie per effettuare il marshalling delle matrici a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="471d1-184">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="471d1-185">Con le matrici a lunghezza fissa, la dimensione viene importata dalla libreria dei tipi e acquisita in **MarshalAsAttribute** che viene applicato al parametro.</span><span class="sxs-lookup"><span data-stu-id="471d1-185">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="471d1-186">È necessario definire manualmente le librerie dei tipi contenenti le matrici a lunghezza variabile, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="471d1-186">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="471d1-187">**Firma non gestita**</span><span class="sxs-lookup"><span data-stu-id="471d1-187">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="471d1-188">**Firma gestita**</span><span class="sxs-lookup"><span data-stu-id="471d1-188">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 <span data-ttu-id="471d1-189">Anche se è possibile applicare gli attributi **size_is** o **length_is** a una matrice nell'origine Interface Definition Language (IDL) per comunicare la dimensione a un client, il compilatore Microsoft Interface Definition Language (MIDL) non propaga tali informazioni alla libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="471d1-189">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="471d1-190">Senza conoscere la dimensione, il servizio di marshalling di interoperabilità non può effettuare il marshalling degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="471d1-190">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="471d1-191">Di conseguenza, le matrici a lunghezza variabile vengono importate come argomenti di riferimento.</span><span class="sxs-lookup"><span data-stu-id="471d1-191">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="471d1-192">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="471d1-192">For example:</span></span>  
  
 <span data-ttu-id="471d1-193">**Firma non gestita**</span><span class="sxs-lookup"><span data-stu-id="471d1-193">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="471d1-194">**Firma gestita**</span><span class="sxs-lookup"><span data-stu-id="471d1-194">**Managed signature**</span></span>  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);
void New2(ref double ar);
void New3(ref String ar);
```  
  
 <span data-ttu-id="471d1-195">Per fornire al gestore di marshalling la dimensione della matrice, è possibile modificare il codice Microsoft Intermediate Language (MSIL) prodotto da Tlbimp.exe e quindi ricompilarlo.</span><span class="sxs-lookup"><span data-stu-id="471d1-195">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="471d1-196">Per informazioni dettagliate su come modificare il codice MSIL, vedere [Personalizzazione dei Runtime Callable Wrapper](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="471d1-196">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span> <span data-ttu-id="471d1-197">Per indicare il numero di elementi della matrice, applicare il tipo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parametro matrice della definizione di metodo gestito in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="471d1-197">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
- <span data-ttu-id="471d1-198">Identificare un altro parametro che contiene il numero di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="471d1-198">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="471d1-199">I parametri vengono identificati in base alla posizione, considerando il primo parametro come numero 0.</span><span class="sxs-lookup"><span data-stu-id="471d1-199">The parameters are identified by position, starting with the first parameter as number 0.</span></span>
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
- <span data-ttu-id="471d1-200">Definire la dimensione della matrice come costante.</span><span class="sxs-lookup"><span data-stu-id="471d1-200">Define the size of the array as a constant.</span></span> <span data-ttu-id="471d1-201">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="471d1-201">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="471d1-202">Quando si effettua il marshalling delle matrici dal codice non gestito al codice gestito, il gestore di marshalling controlla **MarshalAsAttribute** associato al parametro per determinare la dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="471d1-202">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="471d1-203">Se la dimensione della matrice non viene specificata, viene effettuato il marshalling di un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="471d1-203">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="471d1-204">**MarshalAsAttribute** non ha effetto sul marshalling delle matrici gestite al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="471d1-204">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="471d1-205">In tal senso, la dimensione della matrice viene determinata con un'analisi.</span><span class="sxs-lookup"><span data-stu-id="471d1-205">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="471d1-206">Non è possibile effettuare il marshalling di un subset di una matrice gestita.</span><span class="sxs-lookup"><span data-stu-id="471d1-206">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="471d1-207">Il gestore di marshalling di interoperabilità usa i metodi **CoTaskMemAlloc** e **CoTaskMemFree** per allocare e recuperare la memoria.</span><span class="sxs-lookup"><span data-stu-id="471d1-207">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="471d1-208">Anche l'allocazione della memoria eseguita dal codice non gestito deve usare questi metodi.</span><span class="sxs-lookup"><span data-stu-id="471d1-208">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
## <a name="passing-arrays-to-com"></a><span data-ttu-id="471d1-209">Passaggio di matrici a COM</span><span class="sxs-lookup"><span data-stu-id="471d1-209">Passing Arrays to COM</span></span>  
 <span data-ttu-id="471d1-210">Tutti i tipi di matrici gestite possono essere passati al codice non gestito dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="471d1-210">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="471d1-211">A seconda del tipo gestito e degli attributi applicati, la matrice è accessibile come matrice protetta o matrice di tipo C, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="471d1-211">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="471d1-212">Tipo di matrice gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-212">Managed array type</span></span>|<span data-ttu-id="471d1-213">Esportato come</span><span class="sxs-lookup"><span data-stu-id="471d1-213">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="471d1-214">**ELEMENT_TYPE_SZARRAY\*\*\*\*\<** *type* **>**</span><span class="sxs-lookup"><span data-stu-id="471d1-214">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="471d1-215"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="471d1-215"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="471d1-216">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="471d1-216">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="471d1-217">Il tipo viene specificato nella firma.</span><span class="sxs-lookup"><span data-stu-id="471d1-217">Type is provided in the signature.</span></span> <span data-ttu-id="471d1-218">La priorità è sempre 1, il limite inferiore è sempre 0.</span><span class="sxs-lookup"><span data-stu-id="471d1-218">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="471d1-219">La dimensione è sempre nota in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="471d1-219">Size is always known at run time.</span></span>|  
|<span data-ttu-id="471d1-220">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span><span class="sxs-lookup"><span data-stu-id="471d1-220">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="471d1-221">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="471d1-221">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="471d1-222">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="471d1-222">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="471d1-223">Tipo, priorità e limiti vengono specificati nella firma.</span><span class="sxs-lookup"><span data-stu-id="471d1-223">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="471d1-224">La dimensione è sempre nota in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="471d1-224">Size is always known at run time.</span></span>|  
|<span data-ttu-id="471d1-225">**ELEMENT_TYPE_CLASS\*\*\*\*\<**<xref:System.Array?displayProperty=nameWithType>**>\*\*</span><span class="sxs-lookup"><span data-stu-id="471d1-225">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>\*\*</span></span>|<span data-ttu-id="471d1-226">**UT_Interface**</span><span class="sxs-lookup"><span data-stu-id="471d1-226">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="471d1-227">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="471d1-227">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="471d1-228">Tipo, priorità, limite e dimensione sono sempre noti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="471d1-228">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="471d1-229">Nell'automazione OLE esiste una limitazione relativa alle matrici di strutture contenenti LPSTR o LPWSTR.</span><span class="sxs-lookup"><span data-stu-id="471d1-229">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="471d1-230">È quindi necessario effettuare il marshalling dei campi **String** come **UnmanagedType.BSTR**.</span><span class="sxs-lookup"><span data-stu-id="471d1-230">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="471d1-231">In caso contrario, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="471d1-231">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="element_type_szarray"></a><span data-ttu-id="471d1-232">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="471d1-232">ELEMENT_TYPE_SZARRAY</span></span>  
 <span data-ttu-id="471d1-233">Quando un metodo contenente un parametro **ELEMENT_TYPE_SZARRAY** (matrice unidimensionale) viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un elemento **SAFEARRAY** di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="471d1-233">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="471d1-234">Le stesse regole di conversione si applicano ai tipi di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="471d1-234">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="471d1-235">I contenuti della matrice gestita vengono automaticamente copiati dalla memoria gestita in **SAFEARRAY**.</span><span class="sxs-lookup"><span data-stu-id="471d1-235">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="471d1-236">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="471d1-236">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="471d1-237">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-237">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="471d1-238">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-238">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="471d1-239">La priorità delle matrici protette è sempre 1 e il limite inferiore è sempre 0.</span><span class="sxs-lookup"><span data-stu-id="471d1-239">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="471d1-240">La dimensione viene determinata in fase di esecuzione dalla dimensione della matrice gestita che viene passata.</span><span class="sxs-lookup"><span data-stu-id="471d1-240">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="471d1-241">È anche possibile effettuare il marshalling della matrice come matrice di tipo C usando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="471d1-241">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="471d1-242">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="471d1-242">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="471d1-243">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-243">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=
   UnmanagedType.LPStr, SizeParamIndex=1)]
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="471d1-244">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-244">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="471d1-245">Anche se gestore di marshalling ha le informazioni sulla lunghezza necessarie per effettuare il marshalling della matrice, la lunghezza della matrice viene in genere passata come argomento separato per comunicare la lunghezza al computer chiamato.</span><span class="sxs-lookup"><span data-stu-id="471d1-245">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="element_type_array"></a><span data-ttu-id="471d1-246">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="471d1-246">ELEMENT_TYPE_ARRAY</span></span>  
 <span data-ttu-id="471d1-247">Quando un metodo contenente un parametro **ELEMENT_TYPE_ARRAY** viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un elemento **SAFEARRAY** di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="471d1-247">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="471d1-248">I contenuti della matrice gestita vengono automaticamente copiati dalla memoria gestita in **SAFEARRAY**.</span><span class="sxs-lookup"><span data-stu-id="471d1-248">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="471d1-249">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="471d1-249">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="471d1-250">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-250">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="471d1-251">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-251">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="471d1-252">Priorità, dimensione e limiti delle matrici protette vengono determinati in fase di esecuzione dalle caratteristiche della matrice gestita.</span><span class="sxs-lookup"><span data-stu-id="471d1-252">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="471d1-253">È anche possibile effettuare il marshalling della matrice come matrice di tipo C applicando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="471d1-253">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="471d1-254">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="471d1-254">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="471d1-255">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-255">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="471d1-256">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-256">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="471d1-257">Non è possibile effettuare il marshalling di matrici annidate.</span><span class="sxs-lookup"><span data-stu-id="471d1-257">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="471d1-258">La firma seguente, ad esempio, genera un errore quando viene esportata con l'[utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="471d1-258">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="471d1-259">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-259">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a><span data-ttu-id="471d1-260">ELEMENT_TYPE_CLASS\<System.Array></span><span class="sxs-lookup"><span data-stu-id="471d1-260">ELEMENT_TYPE_CLASS \<System.Array></span></span>  
 <span data-ttu-id="471d1-261">Quando un metodo contenente un parametro <xref:System.Array?displayProperty=nameWithType> viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un'interfaccia **_Array**.</span><span class="sxs-lookup"><span data-stu-id="471d1-261">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="471d1-262">I contenuti della matrice gestita sono accessibili solo tramite i metodi e le proprietà dell'interfaccia **_Array**.</span><span class="sxs-lookup"><span data-stu-id="471d1-262">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="471d1-263">È anche possibile effettuare il marshalling di **System.Array** come **SAFEARRAY** usando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="471d1-263">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="471d1-264">Se sottoposti a marshalling come matrice protetta, gli elementi della matrice vengono sottoposti a marshalling come varianti.</span><span class="sxs-lookup"><span data-stu-id="471d1-264">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="471d1-265">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="471d1-265">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="471d1-266">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-266">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="471d1-267">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-267">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="471d1-268">Matrici all'interno di strutture</span><span class="sxs-lookup"><span data-stu-id="471d1-268">Arrays within Structures</span></span>  
 <span data-ttu-id="471d1-269">Le strutture non gestite possono contenere matrici incorporate.</span><span class="sxs-lookup"><span data-stu-id="471d1-269">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="471d1-270">Per impostazione predefinita, viene effettuato il marshalling di questi campi di matrici incorporate come SAFEARRAY.</span><span class="sxs-lookup"><span data-stu-id="471d1-270">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="471d1-271">Nell'esempio seguente `s1` è una matrice incorporata che viene allocata direttamente nella struttura stessa.</span><span class="sxs-lookup"><span data-stu-id="471d1-271">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="471d1-272">Rappresentazione non gestita</span><span class="sxs-lookup"><span data-stu-id="471d1-272">Unmanaged representation</span></span>  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="471d1-273">È possibile effettuare il marshalling delle matrici come <xref:System.Runtime.InteropServices.UnmanagedType>. A questo scopo è necessario impostare il campo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="471d1-273">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="471d1-274">La dimensione può essere impostata solo come costante.</span><span class="sxs-lookup"><span data-stu-id="471d1-274">The size can be set only as a constant.</span></span> <span data-ttu-id="471d1-275">Il codice seguente mostra la definizione gestita corrispondente di `MyStruct`.</span><span class="sxs-lookup"><span data-stu-id="471d1-275">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="471d1-276">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="471d1-276">See also</span></span>

- [<span data-ttu-id="471d1-277">comportamento predefinito del marshalling</span><span class="sxs-lookup"><span data-stu-id="471d1-277">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="471d1-278">tipi copiabili e non copiabili</span><span class="sxs-lookup"><span data-stu-id="471d1-278">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="471d1-279">[Attributi direzionali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="471d1-279">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="471d1-280">copia e blocco</span><span class="sxs-lookup"><span data-stu-id="471d1-280">Copying and Pinning</span></span>](copying-and-pinning.md)

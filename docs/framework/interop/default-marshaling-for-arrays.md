---
title: Marshalling predefinito per le matrici
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
ms.openlocfilehash: f0094ac572834b2cf0d74fb53c94877da55669e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181454"
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="f26cb-102">Marshalling predefinito per le matrici</span><span class="sxs-lookup"><span data-stu-id="f26cb-102">Default Marshaling for Arrays</span></span>
<span data-ttu-id="f26cb-103">In un'applicazione costituita interamente da codice gestito Common Language Runtime passa i tipi di matrice come parametri In/Out.</span><span class="sxs-lookup"><span data-stu-id="f26cb-103">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="f26cb-104">Il gestore di marshalling di interoperabilità invece passa una matrice come parametro In per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f26cb-104">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="f26cb-105">Con l'[ottimizzazione del blocco](copying-and-pinning.md), può sembrare che una matrice copiabile da BLT funzioni come parametro In/Out quando interagisce con oggetti nello stesso apartment.</span><span class="sxs-lookup"><span data-stu-id="f26cb-105">With [pinning optimization](copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="f26cb-106">Se tuttavia in seguito si esporta il codice in una libreria dei tipi usata per generare il proxy tra computer e la libreria viene usata per effettuare il marshalling delle chiamate tra gli apartment, le chiamate possono ripristinare il vero e proprio comportamento del parametro In.</span><span class="sxs-lookup"><span data-stu-id="f26cb-106">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="f26cb-107">Le matrici sono complesse per natura e le distinzioni tra matrici gestite e non gestite richiedono più informazioni degli altri tipi non copiabili da BLT.</span><span class="sxs-lookup"><span data-stu-id="f26cb-107">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span>  
  
## <a name="managed-arrays"></a><span data-ttu-id="f26cb-108">Matrici gestite</span><span class="sxs-lookup"><span data-stu-id="f26cb-108">Managed Arrays</span></span>  
 <span data-ttu-id="f26cb-109">I tipi di matrici gestite possono variare, ma la classe <xref:System.Array?displayProperty=nameWithType> è la classe base di tutti i tipi di matrici.</span><span class="sxs-lookup"><span data-stu-id="f26cb-109">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="f26cb-110">La classe **System.Array** ha proprietà per determinare priorità, lunghezza e limiti inferiori e superiori di una matrice, oltre a metodi per accedere, ordinare, cercare, copiare e creare matrici.</span><span class="sxs-lookup"><span data-stu-id="f26cb-110">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="f26cb-111">Questi tipi di matrici sono dinamici e non devono avere un tipo statico corrispondente definito nella libreria di classi base.</span><span class="sxs-lookup"><span data-stu-id="f26cb-111">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="f26cb-112">È utile considerare ogni combinazione di tipo di elemento e priorità come un tipo distinto di matrice.</span><span class="sxs-lookup"><span data-stu-id="f26cb-112">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="f26cb-113">Una matrice unidimensionale di integer è quindi di un tipo diverso da una matrice unidimensionale di tipi double.</span><span class="sxs-lookup"><span data-stu-id="f26cb-113">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="f26cb-114">Analogamente una matrice bidimensionale di integer è diversa da una matrice unidimensionale di integer.</span><span class="sxs-lookup"><span data-stu-id="f26cb-114">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="f26cb-115">I limiti della matrice non vengono considerati quando si confrontano i tipi.</span><span class="sxs-lookup"><span data-stu-id="f26cb-115">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="f26cb-116">Come illustra la tabella seguente, tutte le istanze di una matrice gestita devono essere di uno specifico tipo di elemento, priorità e limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="f26cb-116">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="f26cb-117">Tipo di matrice gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-117">Managed array type</span></span>|<span data-ttu-id="f26cb-118">Tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="f26cb-118">Element type</span></span>|<span data-ttu-id="f26cb-119">Rank</span><span class="sxs-lookup"><span data-stu-id="f26cb-119">Rank</span></span>|<span data-ttu-id="f26cb-120">Limite inferiore</span><span class="sxs-lookup"><span data-stu-id="f26cb-120">Lower bound</span></span>|<span data-ttu-id="f26cb-121">Notazione della firma</span><span class="sxs-lookup"><span data-stu-id="f26cb-121">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="f26cb-122">**ELEMENT_TYPE_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="f26cb-122">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="f26cb-123">Specificato dal tipo.</span><span class="sxs-lookup"><span data-stu-id="f26cb-123">Specified by type.</span></span>|<span data-ttu-id="f26cb-124">Specificata dalla priorità.</span><span class="sxs-lookup"><span data-stu-id="f26cb-124">Specified by rank.</span></span>|<span data-ttu-id="f26cb-125">Specificato facoltativamente dai limiti.</span><span class="sxs-lookup"><span data-stu-id="f26cb-125">Optionally specified by bounds.</span></span>|<span data-ttu-id="f26cb-126">*tipo* **[** *n*,*m* **]**</span><span class="sxs-lookup"><span data-stu-id="f26cb-126">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="f26cb-127">**ELEMENT_TYPE_CLASS**</span><span class="sxs-lookup"><span data-stu-id="f26cb-127">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="f26cb-128">Unknown</span><span class="sxs-lookup"><span data-stu-id="f26cb-128">Unknown</span></span>|<span data-ttu-id="f26cb-129">Unknown</span><span class="sxs-lookup"><span data-stu-id="f26cb-129">Unknown</span></span>|<span data-ttu-id="f26cb-130">Unknown</span><span class="sxs-lookup"><span data-stu-id="f26cb-130">Unknown</span></span>|<span data-ttu-id="f26cb-131">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="f26cb-131">**System.Array**</span></span>|  
|<span data-ttu-id="f26cb-132">**ELEMENT_TYPE_SZARRAY**</span><span class="sxs-lookup"><span data-stu-id="f26cb-132">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="f26cb-133">Specificato dal tipo.</span><span class="sxs-lookup"><span data-stu-id="f26cb-133">Specified by type.</span></span>|<span data-ttu-id="f26cb-134">1</span><span class="sxs-lookup"><span data-stu-id="f26cb-134">1</span></span>|<span data-ttu-id="f26cb-135">0</span><span class="sxs-lookup"><span data-stu-id="f26cb-135">0</span></span>|<span data-ttu-id="f26cb-136">*tipo* **[** *n* **]**</span><span class="sxs-lookup"><span data-stu-id="f26cb-136">*type* **[** *n* **]**</span></span>|  
  
## <a name="unmanaged-arrays"></a><span data-ttu-id="f26cb-137">Matrici non gestite</span><span class="sxs-lookup"><span data-stu-id="f26cb-137">Unmanaged Arrays</span></span>  
 <span data-ttu-id="f26cb-138">Le matrici non gestite sono matrici protette di tipo COM o matrici di tipo C con lunghezza fissa o variabile.</span><span class="sxs-lookup"><span data-stu-id="f26cb-138">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="f26cb-139">Le matrici protette sono matrici autodescrittive che contengono il tipo, la priorità e i limiti dei dati della matrice associati.</span><span class="sxs-lookup"><span data-stu-id="f26cb-139">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="f26cb-140">Le matrici di tipo C sono matrici tipizzate unidimensionali con un limite inferiore fisso pari a 0.</span><span class="sxs-lookup"><span data-stu-id="f26cb-140">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="f26cb-141">Il servizio di marshalling ha un supporto limitato per entrambi i tipi di matrici.</span><span class="sxs-lookup"><span data-stu-id="f26cb-141">The marshaling service has limited support for both types of arrays.</span></span>  
  
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="f26cb-142">Passaggio dei parametri delle matrici al codice .NET</span><span class="sxs-lookup"><span data-stu-id="f26cb-142">Passing Array Parameters to .NET Code</span></span>  
 <span data-ttu-id="f26cb-143">Sia le matrici di tipo C che le matrici protette possono essere passate al codice .NET dal codice non gestito come matrice protetta o matrice di tipo C.</span><span class="sxs-lookup"><span data-stu-id="f26cb-143">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="f26cb-144">La tabella seguente illustra il valore del tipo non gestito e il tipo importato.</span><span class="sxs-lookup"><span data-stu-id="f26cb-144">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="f26cb-145">Tipo non gestito</span><span class="sxs-lookup"><span data-stu-id="f26cb-145">Unmanaged type</span></span>|<span data-ttu-id="f26cb-146">Tipo importato</span><span class="sxs-lookup"><span data-stu-id="f26cb-146">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="f26cb-147">**SAFEARRAY (** *tipo* **)**</span><span class="sxs-lookup"><span data-stu-id="f26cb-147">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="f26cb-148">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType\*\*\*>*\*</span><span class="sxs-lookup"><span data-stu-id="f26cb-148">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="f26cb-149">Priorità = 1, limite inferiore = 0.</span><span class="sxs-lookup"><span data-stu-id="f26cb-149">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="f26cb-150">La dimensione è nota solo se specificata nella firma gestita.</span><span class="sxs-lookup"><span data-stu-id="f26cb-150">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="f26cb-151">Non è possibile effettuare il marshalling delle matrici protette che non hanno priorità = 1 o limite inferiore = 0 come **SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="f26cb-151">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="f26cb-152">*Tipo*  **[]**</span><span class="sxs-lookup"><span data-stu-id="f26cb-152">*Type*  **[]**</span></span>|<span data-ttu-id="f26cb-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType\*\*\*>*\*</span><span class="sxs-lookup"><span data-stu-id="f26cb-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="f26cb-154">Priorità = 1, limite inferiore = 0.</span><span class="sxs-lookup"><span data-stu-id="f26cb-154">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="f26cb-155">La dimensione è nota solo se specificata nella firma gestita.</span><span class="sxs-lookup"><span data-stu-id="f26cb-155">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="f26cb-156">Matrici protette</span><span class="sxs-lookup"><span data-stu-id="f26cb-156">Safe Arrays</span></span>  
 <span data-ttu-id="f26cb-157">Quando una matrice protetta viene importata da una libreria dei tipi in un assembly .NET, la matrice viene convertita in una matrice unidimensionale di tipo noto (ad esempio, **int**).</span><span class="sxs-lookup"><span data-stu-id="f26cb-157">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="f26cb-158">Le stesse regole di conversione del tipo applicate ai parametri si applicano anche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f26cb-158">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="f26cb-159">Una matrice protetta di tipi **BSTR**, ad esempio, diventa una matrice gestita di stringhe e una matrice protetta di varianti diventa una matrice gestita di oggetti.</span><span class="sxs-lookup"><span data-stu-id="f26cb-159">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="f26cb-160">Il tipo di elemento **SAFEARRAY** viene acquisito dalla libreria dei tipi e salvato nel valore **SAFEARRAY** dell'enumerazione <xref:System.Runtime.InteropServices.UnmanagedType>.</span><span class="sxs-lookup"><span data-stu-id="f26cb-160">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="f26cb-161">Poiché la priorità e i limiti della matrice protetta non possono essere determinati dalla libreria dei tipi, si presuppone che la priorità sia pari a 1 e che il limite inferiore sia pari a 0.</span><span class="sxs-lookup"><span data-stu-id="f26cb-161">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="f26cb-162">La priorità e i limiti devono essere definiti nella firma gestita prodotta dall'[utilità di importazione della libreria dei tipi (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="f26cb-162">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="f26cb-163">Se la priorità passata al metodo in fase di esecuzione è diversa, viene generata un'eccezione <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="f26cb-163">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="f26cb-164">Se il tipo della matrice passata in fase di esecuzione è diverso, viene generata un'eccezione <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="f26cb-164">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="f26cb-165">L'esempio seguente illustra le matrici protette nel codice gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="f26cb-165">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="f26cb-166">**Firma non gestita**</span><span class="sxs-lookup"><span data-stu-id="f26cb-166">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="f26cb-167">**Firma gestita**</span><span class="sxs-lookup"><span data-stu-id="f26cb-167">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="f26cb-168">È possibile effettuare il marshalling delle matrici protette multidimensionali, o con limiti diversi da zero, nel codice gestito se la firma del metodo prodotta da Tlbimp.exe viene modificata per indicare un tipo di elemento **ELEMENT_TYPE_ARRAY** invece di **ELEMENT_TYPE_SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="f26cb-168">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="f26cb-169">In alternativa, è possibile usare l'opzione **/sysarray** con Tlbimp.exe per importare tutte le matrici come oggetti <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f26cb-169">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="f26cb-170">Nei casi in cui la matrice passata è multidimensionale, è possibile modificare il codice Microsoft Intermediate Language (MSIL) prodotto da Tlbimp.exe e quindi ricompilarla.</span><span class="sxs-lookup"><span data-stu-id="f26cb-170">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="f26cb-171">Per informazioni dettagliate su come modificare il codice MSIL, vedere [Personalizzazione dei Runtime Callable Wrapper](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f26cb-171">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="f26cb-172">Matrici di tipo C</span><span class="sxs-lookup"><span data-stu-id="f26cb-172">C-Style Arrays</span></span>  
 <span data-ttu-id="f26cb-173">Quando una matrice di tipo C viene importata da una libreria dei tipi in un assembly .NET, la matrice viene convertita in **ELEMENT_TYPE_SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="f26cb-173">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="f26cb-174">Il tipo di elemento della matrice è determinato dalla libreria dei tipi e mantenuto durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="f26cb-174">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="f26cb-175">Le stesse regole di conversione applicate ai parametri si applicano anche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f26cb-175">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="f26cb-176">Ad esempio, una matrice di tipi **LPStr** diventa una matrice di tipi **String**.</span><span class="sxs-lookup"><span data-stu-id="f26cb-176">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="f26cb-177">Tlbimp.exe acquisisce il tipo di elemento della matrice e applica l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parametro.</span><span class="sxs-lookup"><span data-stu-id="f26cb-177">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="f26cb-178">Si presuppone che la priorità della matrice sia uguale a 1.</span><span class="sxs-lookup"><span data-stu-id="f26cb-178">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="f26cb-179">Se la priorità è superiore a 1, la matrice viene sottoposta a marshalling come matrice unidimensionale in ordine column-major.</span><span class="sxs-lookup"><span data-stu-id="f26cb-179">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="f26cb-180">Il limite inferiore è sempre uguale a 0.</span><span class="sxs-lookup"><span data-stu-id="f26cb-180">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="f26cb-181">Le librerie dei tipi possono contenere matrici a lunghezza fissa o variabile.</span><span class="sxs-lookup"><span data-stu-id="f26cb-181">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="f26cb-182">Tlbimp.exe può importare solo matrici a lunghezza fissa dalle librerie dei tipi perché le librerie dei tipi sono prive delle informazioni necessarie per effettuare il marshalling delle matrici a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="f26cb-182">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="f26cb-183">Con le matrici a lunghezza fissa, la dimensione viene importata dalla libreria dei tipi e acquisita in **MarshalAsAttribute** che viene applicato al parametro.</span><span class="sxs-lookup"><span data-stu-id="f26cb-183">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="f26cb-184">È necessario definire manualmente le librerie dei tipi contenenti le matrici a lunghezza variabile, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f26cb-184">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="f26cb-185">**Firma non gestita**</span><span class="sxs-lookup"><span data-stu-id="f26cb-185">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="f26cb-186">**Firma gestita**</span><span class="sxs-lookup"><span data-stu-id="f26cb-186">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="f26cb-187">Anche se è possibile applicare gli attributi **size_is** o **length_is** a una matrice nell'origine Interface Definition Language (IDL) per comunicare la dimensione a un client, il compilatore Microsoft Interface Definition Language (MIDL) non propaga tali informazioni alla libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="f26cb-187">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="f26cb-188">Senza conoscere la dimensione, il servizio di marshalling di interoperabilità non può effettuare il marshalling degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f26cb-188">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="f26cb-189">Di conseguenza, le matrici a lunghezza variabile vengono importate come argomenti di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f26cb-189">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="f26cb-190">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f26cb-190">For example:</span></span>  
  
 <span data-ttu-id="f26cb-191">**Firma non gestita**</span><span class="sxs-lookup"><span data-stu-id="f26cb-191">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="f26cb-192">**Firma gestita**</span><span class="sxs-lookup"><span data-stu-id="f26cb-192">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="f26cb-193">Per fornire al gestore di marshalling la dimensione della matrice, è possibile modificare il codice Microsoft Intermediate Language (MSIL) prodotto da Tlbimp.exe e quindi ricompilarlo.</span><span class="sxs-lookup"><span data-stu-id="f26cb-193">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="f26cb-194">Per informazioni dettagliate su come modificare il codice MSIL, vedere [Personalizzazione dei Runtime Callable Wrapper](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f26cb-194">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span> <span data-ttu-id="f26cb-195">Per indicare il numero di elementi della matrice, applicare il tipo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parametro matrice della definizione di metodo gestito in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f26cb-195">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
- <span data-ttu-id="f26cb-196">Identificare un altro parametro che contiene il numero di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="f26cb-196">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="f26cb-197">I parametri vengono identificati in base alla posizione, considerando il primo parametro come numero 0.</span><span class="sxs-lookup"><span data-stu-id="f26cb-197">The parameters are identified by position, starting with the first parameter as number 0.</span></span>
  
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
  
- <span data-ttu-id="f26cb-198">Definire la dimensione della matrice come costante.</span><span class="sxs-lookup"><span data-stu-id="f26cb-198">Define the size of the array as a constant.</span></span> <span data-ttu-id="f26cb-199">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f26cb-199">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="f26cb-200">Quando si effettua il marshalling delle matrici dal codice non gestito al codice gestito, il gestore di marshalling controlla **MarshalAsAttribute** associato al parametro per determinare la dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="f26cb-200">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="f26cb-201">Se la dimensione della matrice non viene specificata, viene effettuato il marshalling di un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="f26cb-201">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f26cb-202">**MarshalAsAttribute** non ha effetto sul marshalling delle matrici gestite al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="f26cb-202">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="f26cb-203">In tal senso, la dimensione della matrice viene determinata con un'analisi.</span><span class="sxs-lookup"><span data-stu-id="f26cb-203">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="f26cb-204">Non è possibile effettuare il marshalling di un subset di una matrice gestita.</span><span class="sxs-lookup"><span data-stu-id="f26cb-204">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="f26cb-205">Il gestore di marshalling di interoperabilità usa i metodi **CoTaskMemAlloc** e **CoTaskMemFree** per allocare e recuperare la memoria.</span><span class="sxs-lookup"><span data-stu-id="f26cb-205">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="f26cb-206">Anche l'allocazione della memoria eseguita dal codice non gestito deve usare questi metodi.</span><span class="sxs-lookup"><span data-stu-id="f26cb-206">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
## <a name="passing-arrays-to-com"></a><span data-ttu-id="f26cb-207">Passaggio di matrici a COM</span><span class="sxs-lookup"><span data-stu-id="f26cb-207">Passing Arrays to COM</span></span>  
 <span data-ttu-id="f26cb-208">Tutti i tipi di matrici gestite possono essere passati al codice non gestito dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f26cb-208">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="f26cb-209">A seconda del tipo gestito e degli attributi applicati, la matrice è accessibile come matrice protetta o matrice di tipo C, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f26cb-209">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="f26cb-210">Tipo di matrice gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-210">Managed array type</span></span>|<span data-ttu-id="f26cb-211">Esportato come</span><span class="sxs-lookup"><span data-stu-id="f26cb-211">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="f26cb-212">**ELEMENT_TYPE_SZARRAY** **\<** *Tipo* di ELEMENT_TYPE_SZARRAY**>**</span><span class="sxs-lookup"><span data-stu-id="f26cb-212">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="f26cb-213"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="f26cb-213"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="f26cb-214">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="f26cb-214">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="f26cb-215">Il tipo viene specificato nella firma.</span><span class="sxs-lookup"><span data-stu-id="f26cb-215">Type is provided in the signature.</span></span> <span data-ttu-id="f26cb-216">La priorità è sempre 1, il limite inferiore è sempre 0.</span><span class="sxs-lookup"><span data-stu-id="f26cb-216">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="f26cb-217">La dimensione è sempre nota in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f26cb-217">Size is always known at run time.</span></span>|  
|<span data-ttu-id="f26cb-218">**ELEMENT_TYPE_ARRAY** **\<** *type* Tipo **>** **>** *rank* **>** di ELEMENT_TYPE_ARRAY Rank**\<** [ *bounds* ] **\<**</span><span class="sxs-lookup"><span data-stu-id="f26cb-218">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="f26cb-219">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="f26cb-219">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="f26cb-220">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="f26cb-220">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="f26cb-221">Tipo, priorità e limiti vengono specificati nella firma.</span><span class="sxs-lookup"><span data-stu-id="f26cb-221">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="f26cb-222">La dimensione è sempre nota in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f26cb-222">Size is always known at run time.</span></span>|  
|<span data-ttu-id="f26cb-223">**ELEMENT_TYPE_CLASS\*\*\*\*\<**<xref:System.Array?displayProperty=nameWithType>**>**</span><span class="sxs-lookup"><span data-stu-id="f26cb-223">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span></span>|<span data-ttu-id="f26cb-224">**UT_Interface**</span><span class="sxs-lookup"><span data-stu-id="f26cb-224">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="f26cb-225">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="f26cb-225">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="f26cb-226">Tipo, priorità, limite e dimensione sono sempre noti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f26cb-226">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="f26cb-227">Nell'automazione OLE esiste una limitazione relativa alle matrici di strutture contenenti LPSTR o LPWSTR.</span><span class="sxs-lookup"><span data-stu-id="f26cb-227">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="f26cb-228">È quindi necessario effettuare il marshalling dei campi **String** come **UnmanagedType.BSTR**.</span><span class="sxs-lookup"><span data-stu-id="f26cb-228">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="f26cb-229">In caso contrario, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f26cb-229">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="element_type_szarray"></a><span data-ttu-id="f26cb-230">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="f26cb-230">ELEMENT_TYPE_SZARRAY</span></span>  
 <span data-ttu-id="f26cb-231">Quando un metodo contenente un parametro **ELEMENT_TYPE_SZARRAY** (matrice unidimensionale) viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un elemento **SAFEARRAY** di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="f26cb-231">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="f26cb-232">Le stesse regole di conversione si applicano ai tipi di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f26cb-232">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="f26cb-233">I contenuti della matrice gestita vengono automaticamente copiati dalla memoria gestita in **SAFEARRAY**.</span><span class="sxs-lookup"><span data-stu-id="f26cb-233">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="f26cb-234">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f26cb-234">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="f26cb-235">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-235">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="f26cb-236">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-236">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="f26cb-237">La priorità delle matrici protette è sempre 1 e il limite inferiore è sempre 0.</span><span class="sxs-lookup"><span data-stu-id="f26cb-237">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="f26cb-238">La dimensione viene determinata in fase di esecuzione dalla dimensione della matrice gestita che viene passata.</span><span class="sxs-lookup"><span data-stu-id="f26cb-238">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="f26cb-239">È anche possibile effettuare il marshalling della matrice come matrice di tipo C usando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f26cb-239">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="f26cb-240">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f26cb-240">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="f26cb-241">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-241">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="f26cb-242">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-242">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="f26cb-243">Anche se gestore di marshalling ha le informazioni sulla lunghezza necessarie per effettuare il marshalling della matrice, la lunghezza della matrice viene in genere passata come argomento separato per comunicare la lunghezza al computer chiamato.</span><span class="sxs-lookup"><span data-stu-id="f26cb-243">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="element_type_array"></a><span data-ttu-id="f26cb-244">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="f26cb-244">ELEMENT_TYPE_ARRAY</span></span>  
 <span data-ttu-id="f26cb-245">Quando un metodo contenente un parametro **ELEMENT_TYPE_ARRAY** viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un elemento **SAFEARRAY** di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="f26cb-245">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="f26cb-246">I contenuti della matrice gestita vengono automaticamente copiati dalla memoria gestita in **SAFEARRAY**.</span><span class="sxs-lookup"><span data-stu-id="f26cb-246">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="f26cb-247">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f26cb-247">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="f26cb-248">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-248">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="f26cb-249">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-249">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="f26cb-250">Priorità, dimensione e limiti delle matrici protette vengono determinati in fase di esecuzione dalle caratteristiche della matrice gestita.</span><span class="sxs-lookup"><span data-stu-id="f26cb-250">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="f26cb-251">È anche possibile effettuare il marshalling della matrice come matrice di tipo C applicando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f26cb-251">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="f26cb-252">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f26cb-252">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="f26cb-253">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-253">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="f26cb-254">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-254">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="f26cb-255">Non è possibile effettuare il marshalling di matrici annidate.</span><span class="sxs-lookup"><span data-stu-id="f26cb-255">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="f26cb-256">La firma seguente, ad esempio, genera un errore quando viene esportata con l'[utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="f26cb-256">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="f26cb-257">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-257">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a><span data-ttu-id="f26cb-258">ELEMENT_TYPE_CLASS \<System.Array></span><span class="sxs-lookup"><span data-stu-id="f26cb-258">ELEMENT_TYPE_CLASS \<System.Array></span></span>  
 <span data-ttu-id="f26cb-259">Quando un metodo contenente un parametro <xref:System.Array?displayProperty=nameWithType> viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un'interfaccia **_Array**.</span><span class="sxs-lookup"><span data-stu-id="f26cb-259">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="f26cb-260">I contenuti della matrice gestita sono accessibili solo tramite i metodi e le proprietà dell'interfaccia **_Array**.</span><span class="sxs-lookup"><span data-stu-id="f26cb-260">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="f26cb-261">È anche possibile effettuare il marshalling di **System.Array** come **SAFEARRAY** usando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f26cb-261">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="f26cb-262">Se sottoposti a marshalling come matrice protetta, gli elementi della matrice vengono sottoposti a marshalling come varianti.</span><span class="sxs-lookup"><span data-stu-id="f26cb-262">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="f26cb-263">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f26cb-263">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="f26cb-264">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-264">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="f26cb-265">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-265">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="f26cb-266">Matrici all'interno di strutture</span><span class="sxs-lookup"><span data-stu-id="f26cb-266">Arrays within Structures</span></span>  
 <span data-ttu-id="f26cb-267">Le strutture non gestite possono contenere matrici incorporate.</span><span class="sxs-lookup"><span data-stu-id="f26cb-267">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="f26cb-268">Per impostazione predefinita, viene effettuato il marshalling di questi campi di matrici incorporate come SAFEARRAY.</span><span class="sxs-lookup"><span data-stu-id="f26cb-268">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="f26cb-269">Nell'esempio seguente `s1` è una matrice incorporata che viene allocata direttamente nella struttura stessa.</span><span class="sxs-lookup"><span data-stu-id="f26cb-269">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="f26cb-270">Rappresentazione non gestita</span><span class="sxs-lookup"><span data-stu-id="f26cb-270">Unmanaged representation</span></span>  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="f26cb-271">È possibile effettuare il marshalling delle matrici come <xref:System.Runtime.InteropServices.UnmanagedType>. A questo scopo è necessario impostare il campo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f26cb-271">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="f26cb-272">La dimensione può essere impostata solo come costante.</span><span class="sxs-lookup"><span data-stu-id="f26cb-272">The size can be set only as a constant.</span></span> <span data-ttu-id="f26cb-273">Il codice seguente mostra la definizione gestita corrispondente di `MyStruct`.</span><span class="sxs-lookup"><span data-stu-id="f26cb-273">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f26cb-274">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f26cb-274">See also</span></span>

- [<span data-ttu-id="f26cb-275">Comportamento di marshalling predefinito</span><span class="sxs-lookup"><span data-stu-id="f26cb-275">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="f26cb-276">Tipi copiabili e non copiabili</span><span class="sxs-lookup"><span data-stu-id="f26cb-276">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="f26cb-277">[Attributi direzionali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f26cb-277">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="f26cb-278">copia e blocco</span><span class="sxs-lookup"><span data-stu-id="f26cb-278">Copying and Pinning</span></span>](copying-and-pinning.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b05ac1016710109110c3ff9d0d318a71fe0827f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393150"
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="88141-102">Marshalling predefinito per le matrici</span><span class="sxs-lookup"><span data-stu-id="88141-102">Default Marshaling for Arrays</span></span>
<span data-ttu-id="88141-103">In un'applicazione costituita interamente da codice gestito Common Language Runtime passa i tipi di matrice come parametri In/Out.</span><span class="sxs-lookup"><span data-stu-id="88141-103">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="88141-104">Il gestore di marshalling di interoperabilità invece passa una matrice come parametro In per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="88141-104">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="88141-105">Con l'[ottimizzazione del blocco](copying-and-pinning.md), può sembrare che una matrice copiabile da BLT funzioni come parametro In/Out quando interagisce con oggetti nello stesso apartment.</span><span class="sxs-lookup"><span data-stu-id="88141-105">With [pinning optimization](copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="88141-106">Se tuttavia in seguito si esporta il codice in una libreria dei tipi usata per generare il proxy tra computer e la libreria viene usata per effettuare il marshalling delle chiamate tra gli apartment, le chiamate possono ripristinare il vero e proprio comportamento del parametro In.</span><span class="sxs-lookup"><span data-stu-id="88141-106">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="88141-107">Le matrici sono complesse per natura e le distinzioni tra matrici gestite e non gestite richiedono più informazioni degli altri tipi non copiabili da BLT.</span><span class="sxs-lookup"><span data-stu-id="88141-107">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span> <span data-ttu-id="88141-108">Questo argomento fornisce le informazioni seguenti sul marshalling delle matrici:</span><span class="sxs-lookup"><span data-stu-id="88141-108">This topic provides the following information on marshaling arrays:</span></span>  
  
-   [<span data-ttu-id="88141-109">Matrici gestite</span><span class="sxs-lookup"><span data-stu-id="88141-109">Managed Arrays</span></span>](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [<span data-ttu-id="88141-110">Matrici non gestite</span><span class="sxs-lookup"><span data-stu-id="88141-110">Unmanaged Arrays</span></span>](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [<span data-ttu-id="88141-111">Passaggio dei parametri delle matrici al codice .NET</span><span class="sxs-lookup"><span data-stu-id="88141-111">Passing Array Parameters to .NET Code</span></span>](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [<span data-ttu-id="88141-112">Passaggio di matrici a COM</span><span class="sxs-lookup"><span data-stu-id="88141-112">Passing Arrays to COM</span></span>](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## <a name="managed-arrays"></a><span data-ttu-id="88141-113">Matrici gestite</span><span class="sxs-lookup"><span data-stu-id="88141-113">Managed Arrays</span></span>  
 <span data-ttu-id="88141-114">I tipi di matrici gestite possono variare, ma la classe <xref:System.Array?displayProperty=nameWithType> è la classe base di tutti i tipi di matrici.</span><span class="sxs-lookup"><span data-stu-id="88141-114">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="88141-115">La classe **System.Array** ha proprietà per determinare priorità, lunghezza e limiti inferiori e superiori di una matrice, oltre a metodi per accedere, ordinare, cercare, copiare e creare matrici.</span><span class="sxs-lookup"><span data-stu-id="88141-115">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="88141-116">Questi tipi di matrici sono dinamici e non devono avere un tipo statico corrispondente definito nella libreria di classi base.</span><span class="sxs-lookup"><span data-stu-id="88141-116">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="88141-117">È utile considerare ogni combinazione di tipo di elemento e priorità come un tipo distinto di matrice.</span><span class="sxs-lookup"><span data-stu-id="88141-117">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="88141-118">Una matrice unidimensionale di integer è quindi di un tipo diverso da una matrice unidimensionale di tipi double.</span><span class="sxs-lookup"><span data-stu-id="88141-118">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="88141-119">Analogamente una matrice bidimensionale di integer è diversa da una matrice unidimensionale di integer.</span><span class="sxs-lookup"><span data-stu-id="88141-119">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="88141-120">I limiti della matrice non vengono considerati quando si confrontano i tipi.</span><span class="sxs-lookup"><span data-stu-id="88141-120">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="88141-121">Come illustra la tabella seguente, tutte le istanze di una matrice gestita devono essere di uno specifico tipo di elemento, priorità e limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="88141-121">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="88141-122">Tipo di matrice gestita</span><span class="sxs-lookup"><span data-stu-id="88141-122">Managed array type</span></span>|<span data-ttu-id="88141-123">Tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="88141-123">Element type</span></span>|<span data-ttu-id="88141-124">Classifica</span><span class="sxs-lookup"><span data-stu-id="88141-124">Rank</span></span>|<span data-ttu-id="88141-125">Limite inferiore</span><span class="sxs-lookup"><span data-stu-id="88141-125">Lower bound</span></span>|<span data-ttu-id="88141-126">Notazione della firma</span><span class="sxs-lookup"><span data-stu-id="88141-126">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="88141-127">**ELEMENT_TYPE_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="88141-127">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="88141-128">Specificato dal tipo.</span><span class="sxs-lookup"><span data-stu-id="88141-128">Specified by type.</span></span>|<span data-ttu-id="88141-129">Specificata dalla priorità.</span><span class="sxs-lookup"><span data-stu-id="88141-129">Specified by rank.</span></span>|<span data-ttu-id="88141-130">Specificato facoltativamente dai limiti.</span><span class="sxs-lookup"><span data-stu-id="88141-130">Optionally specified by bounds.</span></span>|<span data-ttu-id="88141-131">*type* **[** *n*,*m* **]**</span><span class="sxs-lookup"><span data-stu-id="88141-131">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="88141-132">**ELEMENT_TYPE_CLASS**</span><span class="sxs-lookup"><span data-stu-id="88141-132">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="88141-133">Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="88141-133">Unknown</span></span>|<span data-ttu-id="88141-134">Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="88141-134">Unknown</span></span>|<span data-ttu-id="88141-135">Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="88141-135">Unknown</span></span>|<span data-ttu-id="88141-136">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="88141-136">**System.Array**</span></span>|  
|<span data-ttu-id="88141-137">**ELEMENT_TYPE_SZARRAY**</span><span class="sxs-lookup"><span data-stu-id="88141-137">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="88141-138">Specificato dal tipo.</span><span class="sxs-lookup"><span data-stu-id="88141-138">Specified by type.</span></span>|<span data-ttu-id="88141-139">1</span><span class="sxs-lookup"><span data-stu-id="88141-139">1</span></span>|<span data-ttu-id="88141-140">0</span><span class="sxs-lookup"><span data-stu-id="88141-140">0</span></span>|<span data-ttu-id="88141-141">*type* **[** *n* **]**</span><span class="sxs-lookup"><span data-stu-id="88141-141">*type* **[** *n* **]**</span></span>|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## <a name="unmanaged-arrays"></a><span data-ttu-id="88141-142">Matrici non gestite</span><span class="sxs-lookup"><span data-stu-id="88141-142">Unmanaged Arrays</span></span>  
 <span data-ttu-id="88141-143">Le matrici non gestite sono matrici protette di tipo COM o matrici di tipo C con lunghezza fissa o variabile.</span><span class="sxs-lookup"><span data-stu-id="88141-143">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="88141-144">Le matrici protette sono matrici autodescrittive che contengono il tipo, la priorità e i limiti dei dati della matrice associati.</span><span class="sxs-lookup"><span data-stu-id="88141-144">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="88141-145">Le matrici di tipo C sono matrici tipizzate unidimensionali con un limite inferiore fisso pari a 0.</span><span class="sxs-lookup"><span data-stu-id="88141-145">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="88141-146">Il servizio di marshalling ha un supporto limitato per entrambi i tipi di matrici.</span><span class="sxs-lookup"><span data-stu-id="88141-146">The marshaling service has limited support for both types of arrays.</span></span>  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="88141-147">Passaggio dei parametri delle matrici al codice .NET</span><span class="sxs-lookup"><span data-stu-id="88141-147">Passing Array Parameters to .NET Code</span></span>  
 <span data-ttu-id="88141-148">Sia le matrici di tipo C che le matrici protette possono essere passate al codice .NET dal codice non gestito come matrice protetta o matrice di tipo C.</span><span class="sxs-lookup"><span data-stu-id="88141-148">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="88141-149">La tabella seguente illustra il valore del tipo non gestito e il tipo importato.</span><span class="sxs-lookup"><span data-stu-id="88141-149">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="88141-150">Tipo non gestito</span><span class="sxs-lookup"><span data-stu-id="88141-150">Unmanaged type</span></span>|<span data-ttu-id="88141-151">Tipo importato</span><span class="sxs-lookup"><span data-stu-id="88141-151">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="88141-152">**SafeArray(** *Type* **)**</span><span class="sxs-lookup"><span data-stu-id="88141-152">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="88141-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="88141-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="88141-154">Priorità = 1, limite inferiore = 0.</span><span class="sxs-lookup"><span data-stu-id="88141-154">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="88141-155">La dimensione è nota solo se specificata nella firma gestita.</span><span class="sxs-lookup"><span data-stu-id="88141-155">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="88141-156">Non è possibile effettuare il marshalling delle matrici protette che non hanno priorità = 1 o limite inferiore = 0 come **SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="88141-156">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="88141-157">*Type*  **[]**</span><span class="sxs-lookup"><span data-stu-id="88141-157">*Type*  **[]**</span></span>|<span data-ttu-id="88141-158">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="88141-158">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="88141-159">Priorità = 1, limite inferiore = 0.</span><span class="sxs-lookup"><span data-stu-id="88141-159">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="88141-160">La dimensione è nota solo se specificata nella firma gestita.</span><span class="sxs-lookup"><span data-stu-id="88141-160">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="88141-161">Matrici protette</span><span class="sxs-lookup"><span data-stu-id="88141-161">Safe Arrays</span></span>  
 <span data-ttu-id="88141-162">Quando una matrice protetta viene importata da una libreria dei tipi in un assembly .NET, la matrice viene convertita in una matrice unidimensionale di tipo noto (ad esempio, **int**).</span><span class="sxs-lookup"><span data-stu-id="88141-162">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="88141-163">Le stesse regole di conversione del tipo applicate ai parametri si applicano anche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="88141-163">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="88141-164">Una matrice protetta di tipi **BSTR**, ad esempio, diventa una matrice gestita di stringhe e una matrice protetta di varianti diventa una matrice gestita di oggetti.</span><span class="sxs-lookup"><span data-stu-id="88141-164">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="88141-165">Il tipo di elemento **SAFEARRAY** viene acquisito dalla libreria dei tipi e salvato nel valore **SAFEARRAY** dell'enumerazione <xref:System.Runtime.InteropServices.UnmanagedType>.</span><span class="sxs-lookup"><span data-stu-id="88141-165">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="88141-166">Poiché la priorità e i limiti della matrice protetta non possono essere determinati dalla libreria dei tipi, si presuppone che la priorità sia pari a 1 e che il limite inferiore sia pari a 0.</span><span class="sxs-lookup"><span data-stu-id="88141-166">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="88141-167">La priorità e i limiti devono essere definiti nella firma gestita prodotta dall'[utilità di importazione della libreria dei tipi (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="88141-167">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="88141-168">Se la priorità passata al metodo in fase di esecuzione è diversa, viene generata un'eccezione <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="88141-168">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="88141-169">Se il tipo della matrice passata in fase di esecuzione è diverso, viene generata un'eccezione <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="88141-169">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="88141-170">L'esempio seguente illustra le matrici protette nel codice gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="88141-170">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="88141-171">**Firma non gestita**</span><span class="sxs-lookup"><span data-stu-id="88141-171">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="88141-172">**Firma gestita**</span><span class="sxs-lookup"><span data-stu-id="88141-172">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="88141-173">È possibile effettuare il marshalling delle matrici protette multidimensionali, o con limiti diversi da zero, nel codice gestito se la firma del metodo prodotta da Tlbimp.exe viene modificata per indicare un tipo di elemento **ELEMENT_TYPE_ARRAY** invece di **ELEMENT_TYPE_SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="88141-173">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="88141-174">In alternativa, è possibile usare l'opzione **/sysarray** con Tlbimp.exe per importare tutte le matrici come oggetti <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="88141-174">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="88141-175">Nei casi in cui la matrice passata è multidimensionale, è possibile modificare il codice Microsoft Intermediate Language (MSIL) prodotto da Tlbimp.exe e quindi ricompilarla.</span><span class="sxs-lookup"><span data-stu-id="88141-175">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="88141-176">Per informazioni dettagliate su come modificare il codice MSIL, vedere [Personalizzazione dei Runtime Callable Wrapper](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="88141-176">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100)).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="88141-177">Matrici di tipo C</span><span class="sxs-lookup"><span data-stu-id="88141-177">C-Style Arrays</span></span>  
 <span data-ttu-id="88141-178">Quando una matrice di tipo C viene importata da una libreria dei tipi in un assembly .NET, la matrice viene convertita in **ELEMENT_TYPE_SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="88141-178">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="88141-179">Il tipo di elemento della matrice è determinato dalla libreria dei tipi e mantenuto durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="88141-179">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="88141-180">Le stesse regole di conversione applicate ai parametri si applicano anche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="88141-180">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="88141-181">Ad esempio, una matrice di tipi **LPStr** diventa una matrice di tipi **String**.</span><span class="sxs-lookup"><span data-stu-id="88141-181">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="88141-182">Tlbimp.exe acquisisce il tipo di elemento della matrice e applica l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parametro.</span><span class="sxs-lookup"><span data-stu-id="88141-182">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="88141-183">Si presuppone che la priorità della matrice sia uguale a 1.</span><span class="sxs-lookup"><span data-stu-id="88141-183">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="88141-184">Se la priorità è superiore a 1, la matrice viene sottoposta a marshalling come matrice unidimensionale in ordine column-major.</span><span class="sxs-lookup"><span data-stu-id="88141-184">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="88141-185">Il limite inferiore è sempre uguale a 0.</span><span class="sxs-lookup"><span data-stu-id="88141-185">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="88141-186">Le librerie dei tipi possono contenere matrici a lunghezza fissa o variabile.</span><span class="sxs-lookup"><span data-stu-id="88141-186">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="88141-187">Tlbimp.exe può importare solo matrici a lunghezza fissa dalle librerie dei tipi perché le librerie dei tipi sono prive delle informazioni necessarie per effettuare il marshalling delle matrici a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="88141-187">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="88141-188">Con le matrici a lunghezza fissa, la dimensione viene importata dalla libreria dei tipi e acquisita in **MarshalAsAttribute** che viene applicato al parametro.</span><span class="sxs-lookup"><span data-stu-id="88141-188">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="88141-189">È necessario definire manualmente le librerie dei tipi contenenti le matrici a lunghezza variabile, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="88141-189">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="88141-190">**Firma non gestita**</span><span class="sxs-lookup"><span data-stu-id="88141-190">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="88141-191">**Firma gestita**</span><span class="sxs-lookup"><span data-stu-id="88141-191">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="88141-192">Anche se è possibile applicare gli attributi **size_is** o **length_is** a una matrice nell'origine Interface Definition Language (IDL) per comunicare la dimensione a un client, il compilatore Microsoft Interface Definition Language (MIDL) non propaga tali informazioni alla libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="88141-192">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="88141-193">Senza conoscere la dimensione, il servizio di marshalling di interoperabilità non può effettuare il marshalling degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="88141-193">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="88141-194">Di conseguenza, le matrici a lunghezza variabile vengono importate come argomenti di riferimento.</span><span class="sxs-lookup"><span data-stu-id="88141-194">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="88141-195">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88141-195">For example:</span></span>  
  
 <span data-ttu-id="88141-196">**Firma non gestita**</span><span class="sxs-lookup"><span data-stu-id="88141-196">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="88141-197">**Firma gestita**</span><span class="sxs-lookup"><span data-stu-id="88141-197">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="88141-198">Per fornire al gestore di marshalling la dimensione della matrice, è possibile modificare il codice Microsoft Intermediate Language (MSIL) prodotto da Tlbimp.exe e quindi ricompilarlo.</span><span class="sxs-lookup"><span data-stu-id="88141-198">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="88141-199">Per informazioni dettagliate su come modificare il codice MSIL, vedere [Personalizzazione dei Runtime Callable Wrapper](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="88141-199">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100)).</span></span> <span data-ttu-id="88141-200">Per indicare il numero di elementi della matrice, applicare il tipo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parametro matrice della definizione di metodo gestito in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="88141-200">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
-   <span data-ttu-id="88141-201">Identificare un altro parametro che contiene il numero di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="88141-201">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="88141-202">I parametri vengono identificati in base alla posizione, considerando il primo parametro come numero 0.</span><span class="sxs-lookup"><span data-stu-id="88141-202">The parameters are identified by position, starting with the first parameter as number 0.</span></span>     
  
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
  
-   <span data-ttu-id="88141-203">Definire la dimensione della matrice come costante.</span><span class="sxs-lookup"><span data-stu-id="88141-203">Define the size of the array as a constant.</span></span> <span data-ttu-id="88141-204">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88141-204">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="88141-205">Quando si effettua il marshalling delle matrici dal codice non gestito al codice gestito, il gestore di marshalling controlla **MarshalAsAttribute** associato al parametro per determinare la dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="88141-205">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="88141-206">Se la dimensione della matrice non viene specificata, viene effettuato il marshalling di un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="88141-206">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88141-207">**MarshalAsAttribute** non ha effetto sul marshalling delle matrici gestite al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="88141-207">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="88141-208">In tal senso, la dimensione della matrice viene determinata con un'analisi.</span><span class="sxs-lookup"><span data-stu-id="88141-208">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="88141-209">Non è possibile effettuare il marshalling di un subset di una matrice gestita.</span><span class="sxs-lookup"><span data-stu-id="88141-209">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="88141-210">Il gestore di marshalling di interoperabilità usa i metodi **CoTaskMemAlloc** e **CoTaskMemFree** per allocare e recuperare la memoria.</span><span class="sxs-lookup"><span data-stu-id="88141-210">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="88141-211">Anche l'allocazione della memoria eseguita dal codice non gestito deve usare questi metodi.</span><span class="sxs-lookup"><span data-stu-id="88141-211">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## <a name="passing-arrays-to-com"></a><span data-ttu-id="88141-212">Passaggio di matrici a COM</span><span class="sxs-lookup"><span data-stu-id="88141-212">Passing Arrays to COM</span></span>  
 <span data-ttu-id="88141-213">Tutti i tipi di matrici gestite possono essere passati al codice non gestito dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="88141-213">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="88141-214">A seconda del tipo gestito e degli attributi applicati, la matrice è accessibile come matrice protetta o matrice di tipo C, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="88141-214">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="88141-215">Tipo di matrice gestita</span><span class="sxs-lookup"><span data-stu-id="88141-215">Managed array type</span></span>|<span data-ttu-id="88141-216">Esportato come</span><span class="sxs-lookup"><span data-stu-id="88141-216">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="88141-217">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span><span class="sxs-lookup"><span data-stu-id="88141-217">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="88141-218"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="88141-218"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="88141-219">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="88141-219">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="88141-220">Il tipo viene specificato nella firma.</span><span class="sxs-lookup"><span data-stu-id="88141-220">Type is provided in the signature.</span></span> <span data-ttu-id="88141-221">La priorità è sempre 1, il limite inferiore è sempre 0.</span><span class="sxs-lookup"><span data-stu-id="88141-221">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="88141-222">La dimensione è sempre nota in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="88141-222">Size is always known at run time.</span></span>|  
|<span data-ttu-id="88141-223">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span><span class="sxs-lookup"><span data-stu-id="88141-223">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="88141-224">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="88141-224">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="88141-225">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="88141-225">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="88141-226">Tipo, priorità e limiti vengono specificati nella firma.</span><span class="sxs-lookup"><span data-stu-id="88141-226">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="88141-227">La dimensione è sempre nota in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="88141-227">Size is always known at run time.</span></span>|  
|<span data-ttu-id="88141-228">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span><span class="sxs-lookup"><span data-stu-id="88141-228">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span></span>|<span data-ttu-id="88141-229">**UT_Interface**</span><span class="sxs-lookup"><span data-stu-id="88141-229">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="88141-230">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="88141-230">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="88141-231">Tipo, priorità, limite e dimensione sono sempre noti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="88141-231">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="88141-232">Nell'automazione OLE esiste una limitazione relativa alle matrici di strutture contenenti LPSTR o LPWSTR.</span><span class="sxs-lookup"><span data-stu-id="88141-232">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="88141-233">È quindi necessario effettuare il marshalling dei campi **String** come **UnmanagedType.BSTR**.</span><span class="sxs-lookup"><span data-stu-id="88141-233">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="88141-234">In caso contrario, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="88141-234">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="elementtypeszarray"></a><span data-ttu-id="88141-235">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="88141-235">ELEMENT_TYPE_SZARRAY</span></span>  
 <span data-ttu-id="88141-236">Quando un metodo contenente un parametro **ELEMENT_TYPE_SZARRAY** (matrice unidimensionale) viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un elemento **SAFEARRAY** di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="88141-236">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="88141-237">Le stesse regole di conversione si applicano ai tipi di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="88141-237">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="88141-238">I contenuti della matrice gestita vengono automaticamente copiati dalla memoria gestita in **SAFEARRAY**.</span><span class="sxs-lookup"><span data-stu-id="88141-238">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="88141-239">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88141-239">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="88141-240">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="88141-240">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="88141-241">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="88141-241">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="88141-242">La priorità delle matrici protette è sempre 1 e il limite inferiore è sempre 0.</span><span class="sxs-lookup"><span data-stu-id="88141-242">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="88141-243">La dimensione viene determinata in fase di esecuzione dalla dimensione della matrice gestita che viene passata.</span><span class="sxs-lookup"><span data-stu-id="88141-243">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="88141-244">È anche possibile effettuare il marshalling della matrice come matrice di tipo C usando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="88141-244">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="88141-245">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88141-245">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="88141-246">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="88141-246">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="88141-247">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="88141-247">Unmanaged signature</span></span>  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="88141-248">Anche se gestore di marshalling ha le informazioni sulla lunghezza necessarie per effettuare il marshalling della matrice, la lunghezza della matrice viene in genere passata come argomento separato per comunicare la lunghezza al computer chiamato.</span><span class="sxs-lookup"><span data-stu-id="88141-248">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="elementtypearray"></a><span data-ttu-id="88141-249">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="88141-249">ELEMENT_TYPE_ARRAY</span></span>  
 <span data-ttu-id="88141-250">Quando un metodo contenente un parametro **ELEMENT_TYPE_ARRAY** viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un elemento **SAFEARRAY** di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="88141-250">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="88141-251">I contenuti della matrice gestita vengono automaticamente copiati dalla memoria gestita in **SAFEARRAY**.</span><span class="sxs-lookup"><span data-stu-id="88141-251">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="88141-252">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88141-252">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="88141-253">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="88141-253">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="88141-254">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="88141-254">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="88141-255">Priorità, dimensione e limiti delle matrici protette vengono determinati in fase di esecuzione dalle caratteristiche della matrice gestita.</span><span class="sxs-lookup"><span data-stu-id="88141-255">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="88141-256">È anche possibile effettuare il marshalling della matrice come matrice di tipo C applicando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="88141-256">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="88141-257">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88141-257">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="88141-258">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="88141-258">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="88141-259">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="88141-259">Unmanaged signature</span></span>  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="88141-260">Non è possibile effettuare il marshalling di matrici annidate.</span><span class="sxs-lookup"><span data-stu-id="88141-260">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="88141-261">La firma seguente, ad esempio, genera un errore quando viene esportata con l'[utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="88141-261">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="88141-262">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="88141-262">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="elementtypeclass-systemarray"></a><span data-ttu-id="88141-263">ELEMENT_TYPE_CLASS \<System.Array></span><span class="sxs-lookup"><span data-stu-id="88141-263">ELEMENT_TYPE_CLASS \<System.Array></span></span>  
 <span data-ttu-id="88141-264">Quando un metodo contenente un parametro <xref:System.Array?displayProperty=nameWithType> viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un'interfaccia **_Array**.</span><span class="sxs-lookup"><span data-stu-id="88141-264">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="88141-265">I contenuti della matrice gestita sono accessibili solo tramite i metodi e le proprietà dell'interfaccia **_Array**.</span><span class="sxs-lookup"><span data-stu-id="88141-265">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="88141-266">È anche possibile effettuare il marshalling di **System.Array** come **SAFEARRAY** usando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="88141-266">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="88141-267">Se sottoposti a marshalling come matrice protetta, gli elementi della matrice vengono sottoposti a marshalling come varianti.</span><span class="sxs-lookup"><span data-stu-id="88141-267">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="88141-268">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88141-268">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="88141-269">Firma gestita</span><span class="sxs-lookup"><span data-stu-id="88141-269">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="88141-270">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="88141-270">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="88141-271">Matrici all'interno di strutture</span><span class="sxs-lookup"><span data-stu-id="88141-271">Arrays within Structures</span></span>  
 <span data-ttu-id="88141-272">Le strutture non gestite possono contenere matrici incorporate.</span><span class="sxs-lookup"><span data-stu-id="88141-272">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="88141-273">Per impostazione predefinita, viene effettuato il marshalling di questi campi di matrici incorporate come SAFEARRAY.</span><span class="sxs-lookup"><span data-stu-id="88141-273">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="88141-274">Nell'esempio seguente `s1` è una matrice incorporata che viene allocata direttamente nella struttura stessa.</span><span class="sxs-lookup"><span data-stu-id="88141-274">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="88141-275">Rappresentazione non gestita</span><span class="sxs-lookup"><span data-stu-id="88141-275">Unmanaged representation</span></span>  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="88141-276">È possibile effettuare il marshalling delle matrici come <xref:System.Runtime.InteropServices.UnmanagedType>. A questo scopo è necessario impostare il campo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="88141-276">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="88141-277">La dimensione può essere impostata solo come costante.</span><span class="sxs-lookup"><span data-stu-id="88141-277">The size can be set only as a constant.</span></span> <span data-ttu-id="88141-278">Il codice seguente mostra la definizione gestita corrispondente di `MyStruct`.</span><span class="sxs-lookup"><span data-stu-id="88141-278">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88141-279">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88141-279">See Also</span></span>  
 [<span data-ttu-id="88141-280">Comportamento di marshalling predefinito</span><span class="sxs-lookup"><span data-stu-id="88141-280">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)  
 [<span data-ttu-id="88141-281">Tipi copiabili e non copiabili</span><span class="sxs-lookup"><span data-stu-id="88141-281">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)  
 <span data-ttu-id="88141-282">[Attributi direzionali](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="88141-282">[Directional Attributes](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span></span>  
 [<span data-ttu-id="88141-283">Copia e blocco</span><span class="sxs-lookup"><span data-stu-id="88141-283">Copying and Pinning</span></span>](copying-and-pinning.md)

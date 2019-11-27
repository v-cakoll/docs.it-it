---
title: Metodo IMetaDataEmit::DefineMethod
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
ms.openlocfilehash: c46b075341742aac605537a08b762b3cf47ef35b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431813"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="c22fb-102">Metodo IMetaDataEmit::DefineMethod</span><span class="sxs-lookup"><span data-stu-id="c22fb-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="c22fb-103">Crea una definizione per un metodo o una funzione globale con la firma specificata e restituisce un token a tale definizione del metodo.</span><span class="sxs-lookup"><span data-stu-id="c22fb-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c22fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c22fb-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c22fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c22fb-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c22fb-106">in Token `mdTypedef` della classe padre o dell'interfaccia padre del metodo.</span><span class="sxs-lookup"><span data-stu-id="c22fb-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="c22fb-107">Impostare `td` su `mdTokenNil`, se si definisce una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="c22fb-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="c22fb-108">in Nome del membro in Unicode.</span><span class="sxs-lookup"><span data-stu-id="c22fb-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="c22fb-109">in Valore dell'enumerazione [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) che specifica gli attributi del metodo o della funzione globale.</span><span class="sxs-lookup"><span data-stu-id="c22fb-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c22fb-110">in Firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="c22fb-110">[in] The method signature.</span></span> <span data-ttu-id="c22fb-111">La firma viene salvata in modo permanente come fornito.</span><span class="sxs-lookup"><span data-stu-id="c22fb-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="c22fb-112">Se è necessario specificare informazioni aggiuntive per qualsiasi parametro, usare il metodo [IMetaDataEmit:: SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c22fb-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c22fb-113">in Conteggio dei byte in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="c22fb-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="c22fb-114">in Indirizzo del codice.</span><span class="sxs-lookup"><span data-stu-id="c22fb-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="c22fb-115">in Valore dell'enumerazione [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) che specifica le funzionalità di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="c22fb-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="c22fb-116">out Token del membro.</span><span class="sxs-lookup"><span data-stu-id="c22fb-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c22fb-117">Note</span><span class="sxs-lookup"><span data-stu-id="c22fb-117">Remarks</span></span>  
 <span data-ttu-id="c22fb-118">L'API dei metadati garantisce la conservazione dei metodi nello stesso ordine in cui il chiamante li emette per una classe o un'interfaccia contenitore specificata, specificata nel parametro `td`.</span><span class="sxs-lookup"><span data-stu-id="c22fb-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="c22fb-119">Di seguito sono riportate informazioni aggiuntive sull'uso di `DefineMethod` e delle impostazioni dei parametri particolari.</span><span class="sxs-lookup"><span data-stu-id="c22fb-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="c22fb-120">Slot nella tabella V</span><span class="sxs-lookup"><span data-stu-id="c22fb-120">Slots in the V-table</span></span>  
 <span data-ttu-id="c22fb-121">Il runtime usa definizioni di metodo per configurare gli slot della tabella v.</span><span class="sxs-lookup"><span data-stu-id="c22fb-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="c22fb-122">Nel caso in cui uno o più slot debbano essere ignorati, ad esempio per mantenere la parità con un layout dell'interfaccia COM, viene definito un metodo fittizio per occupare lo slot o gli slot nella tabella v. impostare il `dwMethodFlags` sul valore `mdRTSpecialName` dell'enumerazione [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) e specificare il nome come:</span><span class="sxs-lookup"><span data-stu-id="c22fb-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="c22fb-123">_VtblGap\<*SequenceNumber*>\<\_*NumeroDiSlot*></span><span class="sxs-lookup"><span data-stu-id="c22fb-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="c22fb-124">dove *SequenceNumber* è il numero di sequenza del metodo e *NumeroDiSlot* è il numero di slot da ignorare nella tabella v.</span><span class="sxs-lookup"><span data-stu-id="c22fb-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="c22fb-125">Se *NumeroDiSlot* viene omesso, viene utilizzato 1.</span><span class="sxs-lookup"><span data-stu-id="c22fb-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="c22fb-126">Questi metodi fittizi non possono essere richiamati dal codice gestito o non gestito e qualsiasi tentativo di chiamarli, dal codice gestito o non gestito, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c22fb-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="c22fb-127">Il loro unico scopo è quello di assumere spazio nella tabella v generata dal runtime per l'integrazione COM.</span><span class="sxs-lookup"><span data-stu-id="c22fb-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="c22fb-128">Metodi duplicati</span><span class="sxs-lookup"><span data-stu-id="c22fb-128">Duplicate Methods</span></span>  
 <span data-ttu-id="c22fb-129">Non definire metodi duplicati.</span><span class="sxs-lookup"><span data-stu-id="c22fb-129">You should not define duplicate methods.</span></span> <span data-ttu-id="c22fb-130">In altre parole, non è necessario chiamare `DefineMethod` con un set di valori duplicati nei parametri `td`, `wzName`e `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="c22fb-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="c22fb-131">Questi tre parametri definiscono insieme in modo univoco il metodo.</span><span class="sxs-lookup"><span data-stu-id="c22fb-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="c22fb-132">Tuttavia, è possibile utilizzare una tripla duplicata purché, per una delle definizioni del metodo, si imposti il bit `mdPrivateScope` nel parametro `dwMethodFlags`.</span><span class="sxs-lookup"><span data-stu-id="c22fb-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="c22fb-133">Il bit `mdPrivateScope` indica che il compilatore non genererà un riferimento a questa definizione del metodo.</span><span class="sxs-lookup"><span data-stu-id="c22fb-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="c22fb-134">Informazioni sull'implementazione del metodo</span><span class="sxs-lookup"><span data-stu-id="c22fb-134">Method Implementation Information</span></span>  
 <span data-ttu-id="c22fb-135">Le informazioni sull'implementazione del metodo spesso non sono note nel momento in cui viene dichiarato il metodo.</span><span class="sxs-lookup"><span data-stu-id="c22fb-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="c22fb-136">Non è quindi necessario passare i valori nei parametri `ulCodeRVA` e `dwImplFlags` quando si chiama `DefineMethod`.</span><span class="sxs-lookup"><span data-stu-id="c22fb-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="c22fb-137">I valori possono essere specificati in un secondo momento tramite [IMetaDataEmit:: SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit:: SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="c22fb-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="c22fb-138">In alcune situazioni, ad esempio gli scenari di chiamata della piattaforma (PInvoke) o di interoperabilità COM, il corpo del metodo non verrà fornito e `ulCodeRVA` deve essere impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="c22fb-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="c22fb-139">In queste situazioni, il metodo non deve essere contrassegnato come abstract, perché il runtime individuerà l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="c22fb-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="c22fb-140">Definizione di un metodo per PInvoke</span><span class="sxs-lookup"><span data-stu-id="c22fb-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="c22fb-141">Per ogni funzione non gestita da chiamare tramite PInvoke, è necessario definire un metodo gestito che rappresenti la funzione non gestita di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c22fb-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="c22fb-142">Per definire il metodo gestito, utilizzare `DefineMethod` con alcuni parametri impostati su determinati valori, a seconda della modalità di utilizzo di PInvoke:</span><span class="sxs-lookup"><span data-stu-id="c22fb-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="c22fb-143">True PInvoke: implica la chiamata di un metodo esterno non gestito che risiede in una DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="c22fb-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="c22fb-144">PInvoke locale: implica la chiamata di un metodo non gestito nativo incorporato nel modulo gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="c22fb-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="c22fb-145">Le impostazioni dei parametri sono fornite nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c22fb-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="c22fb-146">Parametro</span><span class="sxs-lookup"><span data-stu-id="c22fb-146">Parameter</span></span>|<span data-ttu-id="c22fb-147">Valori per true PInvoke</span><span class="sxs-lookup"><span data-stu-id="c22fb-147">Values for true PInvoke</span></span>|<span data-ttu-id="c22fb-148">Valori per PInvoke locale</span><span class="sxs-lookup"><span data-stu-id="c22fb-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="c22fb-149">Imposta `mdStatic`; deselezionare `mdSynchronized` e `mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="c22fb-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="c22fb-150">Firma di un metodo di Common Language Runtime (CLR) valida con parametri che sono tipi gestiti validi.</span><span class="sxs-lookup"><span data-stu-id="c22fb-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="c22fb-151">Firma di un metodo CLR valida con parametri che sono tipi gestiti validi.</span><span class="sxs-lookup"><span data-stu-id="c22fb-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="c22fb-152">0</span><span class="sxs-lookup"><span data-stu-id="c22fb-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="c22fb-153">Impostare `miCil` e `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="c22fb-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="c22fb-154">Impostare `miNative` e `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="c22fb-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c22fb-155">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c22fb-155">Requirements</span></span>  
 <span data-ttu-id="c22fb-156">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c22fb-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c22fb-157">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c22fb-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c22fb-158">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c22fb-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c22fb-159">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c22fb-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22fb-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c22fb-160">See also</span></span>

- [<span data-ttu-id="c22fb-161">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c22fb-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c22fb-162">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c22fb-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

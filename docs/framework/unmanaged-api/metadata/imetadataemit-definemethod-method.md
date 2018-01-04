---
title: Metodo IMetaDataEmit::DefineMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fa136f5e6669e58ef709db5b53f538804cfcac2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="a5662-102">Metodo IMetaDataEmit::DefineMethod</span><span class="sxs-lookup"><span data-stu-id="a5662-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="a5662-103">Crea una definizione per un metodo o una funzione globale con la firma specificata e restituisce un token per tale definizione.</span><span class="sxs-lookup"><span data-stu-id="a5662-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5662-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5662-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="a5662-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5662-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a5662-106">[in] Il `mdTypedef` token della classe padre o dell'interfaccia padre del metodo.</span><span class="sxs-lookup"><span data-stu-id="a5662-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="a5662-107">Impostare `td` a `mdTokenNil`, se si definisce una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="a5662-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="a5662-108">[in] Il nome del membro in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="a5662-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="a5662-109">[in] Il valore di [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumerazione che specifica gli attributi del metodo o della funzione globale.</span><span class="sxs-lookup"><span data-stu-id="a5662-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="a5662-110">[in] La firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="a5662-110">[in] The method signature.</span></span> <span data-ttu-id="a5662-111">La firma viene mantenuta come fornito.</span><span class="sxs-lookup"><span data-stu-id="a5662-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="a5662-112">Se è necessario specificare informazioni aggiuntive per i parametri, utilizzare il [IMetaDataEmit:: SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="a5662-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="a5662-113">[in] Il numero di byte in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="a5662-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="a5662-114">[in] L'indirizzo del codice.</span><span class="sxs-lookup"><span data-stu-id="a5662-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="a5662-115">[in] Il valore di [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione che specifica le funzionalità di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="a5662-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="a5662-116">[out] Il token di membro.</span><span class="sxs-lookup"><span data-stu-id="a5662-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5662-117">Note</span><span class="sxs-lookup"><span data-stu-id="a5662-117">Remarks</span></span>  
 <span data-ttu-id="a5662-118">L'API dei metadati garantisce che vengano mantenuti metodi nello stesso ordine in cui il chiamante vengono generati per una determinata classe o un'interfaccia, specificata nel `td` parametro.</span><span class="sxs-lookup"><span data-stu-id="a5662-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="a5662-119">Informazioni aggiuntive relative all'uso di `DefineMethod` e impostazioni particolari dei parametri sono specificati di seguito.</span><span class="sxs-lookup"><span data-stu-id="a5662-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="a5662-120">Slot nella tabella V-table.</span><span class="sxs-lookup"><span data-stu-id="a5662-120">Slots in the V-table</span></span>  
 <span data-ttu-id="a5662-121">Il runtime utilizza le definizioni di metodo per impostare gli slot v-table.</span><span class="sxs-lookup"><span data-stu-id="a5662-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="a5662-122">Nel caso in cui devono essere ignorate, ad esempio uno o più slot per mantenere la parità con un layout di interfaccia COM, viene definito un metodo fittizio in modo da occupare lo slot o slot nella tabella v. impostare il `dwMethodFlags` per il `mdRTSpecialName` valore il [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumerazione e specificare il nome come:</span><span class="sxs-lookup"><span data-stu-id="a5662-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="a5662-123">VtblGap\<*SequenceNumber*>\<\_*NumeroDiSlot*></span><span class="sxs-lookup"><span data-stu-id="a5662-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>  
  
 <span data-ttu-id="a5662-124">dove *SequenceNumber* è il numero di sequenza del metodo e *NumeroDiSlot* è il numero di slot da ignorare nella v-table.</span><span class="sxs-lookup"><span data-stu-id="a5662-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="a5662-125">Se *NumeroDiSlot* viene omesso, viene utilizzato il valore 1.</span><span class="sxs-lookup"><span data-stu-id="a5662-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="a5662-126">Questi metodi fittizi non richiamabili da codice gestito o non gestito e qualsiasi tentativo di chiamarle da codice gestito o non gestito, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a5662-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="a5662-127">Il solo scopo è occupare spazio nella tabella v generati dal runtime per l'integrazione con COM.</span><span class="sxs-lookup"><span data-stu-id="a5662-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="a5662-128">Metodi duplicati</span><span class="sxs-lookup"><span data-stu-id="a5662-128">Duplicate Methods</span></span>  
 <span data-ttu-id="a5662-129">Non è necessario definire metodi duplicati.</span><span class="sxs-lookup"><span data-stu-id="a5662-129">You should not define duplicate methods.</span></span> <span data-ttu-id="a5662-130">Ovvero, non è necessario chiamare `DefineMethod` con un set di valori duplicati di `td`, `wzName`, e `pvSig` parametri.</span><span class="sxs-lookup"><span data-stu-id="a5662-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="a5662-131">(Questi tre parametri insieme definiscono in modo univoco il metodo.).</span><span class="sxs-lookup"><span data-stu-id="a5662-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="a5662-132">Tuttavia, è possibile utilizzare un duplicata condizione che, per una delle definizioni di metodo, è impostato il `mdPrivateScope` bit il `dwMethodFlags` parametro.</span><span class="sxs-lookup"><span data-stu-id="a5662-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="a5662-133">(Il `mdPrivateScope` bit significa che il compilatore non genererà un riferimento a questa definizione di metodo.)</span><span class="sxs-lookup"><span data-stu-id="a5662-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="a5662-134">Informazioni sul metodo di implementazione</span><span class="sxs-lookup"><span data-stu-id="a5662-134">Method Implementation Information</span></span>  
 <span data-ttu-id="a5662-135">Informazioni sull'implementazione del metodo spesso non sono noto al momento che il metodo viene dichiarato.</span><span class="sxs-lookup"><span data-stu-id="a5662-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="a5662-136">Pertanto, non è necessario passare valori di `ulCodeRVA` e `dwImplFlags` parametri quando si chiama `DefineMethod`.</span><span class="sxs-lookup"><span data-stu-id="a5662-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="a5662-137">I valori possono essere forniti in un secondo momento tramite [SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit:: SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="a5662-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="a5662-138">In alcune situazioni, ad esempio la chiamata di platform (invoke PInvoke) o scenari di interoperabilità COM, non verrà fornito il corpo del metodo, e `ulCodeRVA` deve essere impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="a5662-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="a5662-139">In questi casi, il metodo non deve essere contrassegnato come abstract, perché il runtime consente di trovare l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="a5662-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="a5662-140">Definizione di un metodo per PInvoke</span><span class="sxs-lookup"><span data-stu-id="a5662-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="a5662-141">Per ogni funzione non gestita a essere chiamati tramite PInvoke, è necessario definire un metodo gestito che rappresenta la funzione non gestita di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5662-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="a5662-142">Per definire il metodo gestito, utilizzare `DefineMethod` con alcuni parametri impostati su determinati valori, a seconda della modalità in cui viene utilizzato PInvoke:</span><span class="sxs-lookup"><span data-stu-id="a5662-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
-   <span data-ttu-id="a5662-143">True PInvoke: comporta la chiamata di un metodo esterno non gestito che si trova in una DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="a5662-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
-   <span data-ttu-id="a5662-144">PInvoke locale - comporta la chiamata di un metodo nativo non gestito che è incorporato nel modulo gestito di corrente.</span><span class="sxs-lookup"><span data-stu-id="a5662-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="a5662-145">Le impostazioni dei parametri sono indicate nella tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="a5662-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="a5662-146">Parametro</span><span class="sxs-lookup"><span data-stu-id="a5662-146">Parameter</span></span>|<span data-ttu-id="a5662-147">Valori per PInvoke true</span><span class="sxs-lookup"><span data-stu-id="a5662-147">Values for true PInvoke</span></span>|<span data-ttu-id="a5662-148">Valori per PInvoke locale</span><span class="sxs-lookup"><span data-stu-id="a5662-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="a5662-149">Impostare `mdStatic`; deselezionare `mdSynchronized` e `mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="a5662-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="a5662-150">Una firma del metodo di common language runtime (CLR) valido con i parametri validi di tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="a5662-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="a5662-151">Una firma del metodo CLR valida con i parametri validi di tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="a5662-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="a5662-152">0</span><span class="sxs-lookup"><span data-stu-id="a5662-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="a5662-153">Impostare `miCil` e `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="a5662-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="a5662-154">Impostare `miNative` e `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="a5662-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5662-155">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5662-155">Requirements</span></span>  
 <span data-ttu-id="a5662-156">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5662-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5662-157">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a5662-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5662-158">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5662-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5662-159">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5662-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5662-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5662-160">See Also</span></span>  
 [<span data-ttu-id="a5662-161">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a5662-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a5662-162">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a5662-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

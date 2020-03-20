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
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177669"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="90847-102">Metodo IMetaDataEmit::DefineMethod</span><span class="sxs-lookup"><span data-stu-id="90847-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="90847-103">Crea una definizione per un metodo o una funzione globale con la firma specificata e restituisce un token a tale definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="90847-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90847-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90847-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="90847-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="90847-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="90847-106">[in] Token `mdTypedef` della classe padre o dell'interfaccia padre del metodo.</span><span class="sxs-lookup"><span data-stu-id="90847-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="90847-107">Impostare `mdTokenNil`su `td` , se si definisce una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="90847-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="90847-108">[in] Nome del membro in Unicode.</span><span class="sxs-lookup"><span data-stu-id="90847-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="90847-109">[in] Valore dell'enumerazione [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) che specifica gli attributi del metodo o della funzione globale.</span><span class="sxs-lookup"><span data-stu-id="90847-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="90847-110">[in] Firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="90847-110">[in] The method signature.</span></span> <span data-ttu-id="90847-111">La firma viene mantenuta come fornito.</span><span class="sxs-lookup"><span data-stu-id="90847-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="90847-112">Se è necessario specificare informazioni aggiuntive per qualsiasi parametro, utilizzare il [metodo IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) .</span><span class="sxs-lookup"><span data-stu-id="90847-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="90847-113">[in] Numero di byte `pvSigBlob`in .</span><span class="sxs-lookup"><span data-stu-id="90847-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="90847-114">[in] Indirizzo del codice.</span><span class="sxs-lookup"><span data-stu-id="90847-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="90847-115">[in] Valore dell'enumerazione [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) che specifica le funzionalità di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="90847-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="90847-116">[fuori] Token del membro.</span><span class="sxs-lookup"><span data-stu-id="90847-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90847-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="90847-117">Remarks</span></span>  
 <span data-ttu-id="90847-118">L'API dei metadati garantisce la persistenza dei metodi nello stesso ordine in cui il `td` chiamante li genera per una determinata classe o interfaccia di inclusione, specificata nel parametro.</span><span class="sxs-lookup"><span data-stu-id="90847-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="90847-119">Ulteriori informazioni relative `DefineMethod` all'utilizzo e alle impostazioni dei parametri particolari sono riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="90847-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="90847-120">Slot nella tabella a V</span><span class="sxs-lookup"><span data-stu-id="90847-120">Slots in the V-table</span></span>  
 <span data-ttu-id="90847-121">Il runtime utilizza le definizioni di metodo per impostare gli slot v-table.</span><span class="sxs-lookup"><span data-stu-id="90847-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="90847-122">Nel caso in cui uno o più slot devono essere saltati, ad esempio per mantenere la parità con un layout di interfaccia COM, viene definito un metodo fittizio per occupare lo slot o gli slot nella tabella v; impostare `dwMethodFlags` il `mdRTSpecialName` sul valore dell'enumerazione [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) e specificare il nome come:</span><span class="sxs-lookup"><span data-stu-id="90847-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="90847-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="90847-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="90847-124">dove *NumeroSequenzo* è il numero di sequenza del metodo e *CountOfSlots* è il numero di slot da ignorare nella tabella v.</span><span class="sxs-lookup"><span data-stu-id="90847-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="90847-125">Se *CountOfSlots* viene omesso, si presuppone 1.</span><span class="sxs-lookup"><span data-stu-id="90847-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="90847-126">Questi metodi fittizi non sono chiamabili da codice gestito o non gestito e qualsiasi tentativo di chiamarli, da codice gestito o non gestito, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="90847-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="90847-127">Il loro unico scopo è occupare spazio nella v-table che il runtime genera per l'integrazione COM.</span><span class="sxs-lookup"><span data-stu-id="90847-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="90847-128">Metodi duplicati</span><span class="sxs-lookup"><span data-stu-id="90847-128">Duplicate Methods</span></span>  
 <span data-ttu-id="90847-129">Non è consigliabile definire metodi duplicati.</span><span class="sxs-lookup"><span data-stu-id="90847-129">You should not define duplicate methods.</span></span> <span data-ttu-id="90847-130">Ovvero, non è `DefineMethod` necessario chiamare con un `td`set `wzName`duplicato di valori nei parametri , e `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="90847-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="90847-131">(Questi tre parametri insieme definiscono in modo univoco il metodo.).</span><span class="sxs-lookup"><span data-stu-id="90847-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="90847-132">Tuttavia, è possibile utilizzare una tripla duplicata a `mdPrivateScope` condizione che, per una delle definizioni di metodo, si imposta il bit nel `dwMethodFlags` parametro.</span><span class="sxs-lookup"><span data-stu-id="90847-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="90847-133">Il `mdPrivateScope` bit indica che il compilatore non genera un riferimento a questa definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="90847-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="90847-134">Informazioni sull'implementazione del metodo</span><span class="sxs-lookup"><span data-stu-id="90847-134">Method Implementation Information</span></span>  
 <span data-ttu-id="90847-135">Le informazioni sull'implementazione del metodo spesso non sono note al momento della proprietà del metodo.</span><span class="sxs-lookup"><span data-stu-id="90847-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="90847-136">Pertanto, non è necessario passare `ulCodeRVA` `dwImplFlags` valori nei `DefineMethod`parametri e quando si chiama .</span><span class="sxs-lookup"><span data-stu-id="90847-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="90847-137">I valori possono essere forniti in un secondo momento tramite [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit::SetRVA,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="90847-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="90847-138">In alcune situazioni, ad esempio la chiamata alla piattaforma (PInvoke) o gli `ulCodeRVA` scenari di interoperabilità COM, il corpo del metodo non verrà fornito e deve essere impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="90847-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="90847-139">In queste situazioni, il metodo non deve essere contrassegnato come astratto, perché il runtime individuerà l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="90847-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="90847-140">Definizione di un metodo per PInvokeDefining a Method for PInvoke</span><span class="sxs-lookup"><span data-stu-id="90847-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="90847-141">Per ogni funzione non gestita da chiamare tramite PInvoke, è necessario definire un metodo gestito che rappresenta la funzione non gestita di destinazione.</span><span class="sxs-lookup"><span data-stu-id="90847-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="90847-142">Per definire il metodo `DefineMethod` gestito, utilizzare con alcuni dei parametri impostati su determinati valori, a seconda del modo in cui viene utilizzato PInvoke:</span><span class="sxs-lookup"><span data-stu-id="90847-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="90847-143">True PInvoke- comporta la chiamata di un metodo non gestito esterno che risiede in una DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="90847-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="90847-144">PInvoke locale: comporta la chiamata di un metodo non gestito nativo incorporato nel modulo gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="90847-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="90847-145">Le impostazioni dei parametri sono riportate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="90847-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="90847-146">Parametro</span><span class="sxs-lookup"><span data-stu-id="90847-146">Parameter</span></span>|<span data-ttu-id="90847-147">Valori per PInvoke true</span><span class="sxs-lookup"><span data-stu-id="90847-147">Values for true PInvoke</span></span>|<span data-ttu-id="90847-148">Valori per PInvoke locale</span><span class="sxs-lookup"><span data-stu-id="90847-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="90847-149">Imposta `mdStatic`; chiaro `mdSynchronized` `mdAbstract`e .</span><span class="sxs-lookup"><span data-stu-id="90847-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="90847-150">Firma del metodo CLR (Common Language Runtime) valida con parametri di tipi gestiti validi.</span><span class="sxs-lookup"><span data-stu-id="90847-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="90847-151">Firma del metodo CLR valida con parametri di tipi gestiti validi.</span><span class="sxs-lookup"><span data-stu-id="90847-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="90847-152">0</span><span class="sxs-lookup"><span data-stu-id="90847-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="90847-153">Impostare `miCil` e `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="90847-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="90847-154">Impostare `miNative` e `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="90847-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90847-155">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90847-155">Requirements</span></span>  
 <span data-ttu-id="90847-156">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90847-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90847-157">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90847-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90847-158">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90847-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90847-159">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90847-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90847-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90847-160">See also</span></span>

- [<span data-ttu-id="90847-161">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="90847-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="90847-162">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="90847-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

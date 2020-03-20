---
title: Metodo IMetaDataImport::EnumMembers
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175486"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="08ef2-102">Metodo IMetaDataImport::EnumMembers</span><span class="sxs-lookup"><span data-stu-id="08ef2-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="08ef2-103">Enumera i token MemberDef che rappresentano i membri del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="08ef2-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ef2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08ef2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08ef2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08ef2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="08ef2-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="08ef2-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="08ef2-107">[in] Token TypeDef che rappresenta il tipo i cui membri devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="08ef2-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="08ef2-108">[fuori] Matrice utilizzata per contenere i token MemberDef.</span><span class="sxs-lookup"><span data-stu-id="08ef2-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="08ef2-109">[in] Dimensione massima della matrice `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="08ef2-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="08ef2-110">[fuori] Numero effettivo di token MemberDef `rMembers`restituiti in .</span><span class="sxs-lookup"><span data-stu-id="08ef2-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08ef2-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08ef2-111">Return Value</span></span>  
  
|<span data-ttu-id="08ef2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08ef2-112">HRESULT</span></span>|<span data-ttu-id="08ef2-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08ef2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="08ef2-114">`EnumMembers`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="08ef2-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="08ef2-115">Non sono presenti token MemberDef da enumerare.</span><span class="sxs-lookup"><span data-stu-id="08ef2-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="08ef2-116">In tal `pcTokens` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="08ef2-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08ef2-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="08ef2-117">Remarks</span></span>  
 <span data-ttu-id="08ef2-118">Quando si enumerano raccolte di `EnumMembers` membri per una classe, restituisce solo i membri (campi e metodi, ma **non** le proprietà o gli eventi) definiti direttamente nella classe.</span><span class="sxs-lookup"><span data-stu-id="08ef2-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="08ef2-119">Non restituisce alcun membro ereditato dalla classe, anche se la classe fornisce un'implementazione per tali membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="08ef2-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="08ef2-120">Per enumerare i membri ereditati, il chiamante deve esaminare in modo esplicito la catena di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="08ef2-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="08ef2-121">Si noti che le regole per la catena di ereditarietà possono variare a seconda del linguaggio o del compilatore che ha generato i metadati originali.</span><span class="sxs-lookup"><span data-stu-id="08ef2-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="08ef2-122">Le proprietà e gli `EnumMembers`eventi non sono enumerati da .</span><span class="sxs-lookup"><span data-stu-id="08ef2-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="08ef2-123">Per enumerarli, utilizzare [EnumProperties](imetadataimport-enumproperties-method.md) o [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="08ef2-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="08ef2-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08ef2-124">Requirements</span></span>  
 <span data-ttu-id="08ef2-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08ef2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08ef2-126">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="08ef2-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08ef2-127">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08ef2-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08ef2-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08ef2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ef2-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08ef2-129">See also</span></span>

- [<span data-ttu-id="08ef2-130">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08ef2-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="08ef2-131">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08ef2-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

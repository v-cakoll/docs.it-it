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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e8d871f2ecbd96d5bda781b2ae11b94efd409442
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128401"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="ad378-102">Metodo IMetaDataImport::EnumMembers</span><span class="sxs-lookup"><span data-stu-id="ad378-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="ad378-103">Enumera i token MemberDef che rappresentano i membri del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="ad378-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad378-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad378-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad378-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad378-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ad378-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="ad378-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="ad378-107">[in] Token TypeDef che rappresenta il tipo i cui membri sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="ad378-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="ad378-108">[out] Matrice usata per contenere i token MemberDef.</span><span class="sxs-lookup"><span data-stu-id="ad378-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ad378-109">[in] Dimensione massima della matrice `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="ad378-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ad378-110">[out] Il numero effettivo di token MemberDef restituiti in `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="ad378-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad378-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ad378-111">Return Value</span></span>  
  
|<span data-ttu-id="ad378-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad378-112">HRESULT</span></span>|<span data-ttu-id="ad378-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad378-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ad378-114">`EnumMembers` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ad378-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ad378-115">Non sono presenti token MemberDef per enumerare.</span><span class="sxs-lookup"><span data-stu-id="ad378-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="ad378-116">In tal caso, `pcTokens` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="ad378-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad378-117">Note</span><span class="sxs-lookup"><span data-stu-id="ad378-117">Remarks</span></span>  
 <span data-ttu-id="ad378-118">Durante l'enumerazione delle raccolte di membri per una classe `EnumMembers` restituisce solo i membri (campi e metodi, ma **non** eventi o proprietà) definiti direttamente nella classe.</span><span class="sxs-lookup"><span data-stu-id="ad378-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="ad378-119">Non restituisce tutti i membri che eredita la classe, anche se la classe fornisce un'implementazione per i membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="ad378-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="ad378-120">Per enumerare i membri ereditati, il chiamante deve verificare in modo esplicito la catena di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="ad378-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="ad378-121">Si noti che le regole per la catena di ereditarietà possono variare a seconda del linguaggio o un compilatore che ha creato i metadati originali.</span><span class="sxs-lookup"><span data-stu-id="ad378-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>
 
 <span data-ttu-id="ad378-122">Proprietà ed eventi non sono enumerati dal `EnumMembers`.</span><span class="sxs-lookup"><span data-stu-id="ad378-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="ad378-123">Per enumerare quelli, usare [EnumProperties](imetadataimport-enumproperties-method.md) oppure [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="ad378-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ad378-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad378-124">Requirements</span></span>  
 <span data-ttu-id="ad378-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad378-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad378-126">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ad378-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad378-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ad378-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad378-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad378-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad378-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad378-129">See also</span></span>

- [<span data-ttu-id="ad378-130">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ad378-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ad378-131">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ad378-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

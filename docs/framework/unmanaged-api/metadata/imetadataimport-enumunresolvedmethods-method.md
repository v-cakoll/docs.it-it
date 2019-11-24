---
title: Metodo IMetaDataImport::EnumUnresolvedMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: ff9827174e43fd62f3a995e9f477c6fff66b227a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449963"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="d7281-102">Metodo IMetaDataImport::EnumUnresolvedMethods</span><span class="sxs-lookup"><span data-stu-id="d7281-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="d7281-103">Enumera i token MemberDef che rappresentano i metodi non risolti nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="d7281-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7281-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7281-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7281-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7281-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d7281-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="d7281-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d7281-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="d7281-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="d7281-108">[out] The array used to store the MemberDef tokens.</span><span class="sxs-lookup"><span data-stu-id="d7281-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d7281-109">[in] Dimensione massima della matrice `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="d7281-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d7281-110">[out] The number of MemberDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="d7281-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7281-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d7281-111">Return Value</span></span>  
  
|<span data-ttu-id="d7281-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7281-112">HRESULT</span></span>|<span data-ttu-id="d7281-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7281-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d7281-114">`EnumUnresolvedMethods` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="d7281-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d7281-115">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="d7281-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="d7281-116">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="d7281-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7281-117">Note</span><span class="sxs-lookup"><span data-stu-id="d7281-117">Remarks</span></span>  
 <span data-ttu-id="d7281-118">An unresolved method is one that has been declared but not implemented.</span><span class="sxs-lookup"><span data-stu-id="d7281-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="d7281-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span><span class="sxs-lookup"><span data-stu-id="d7281-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="d7281-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span><span class="sxs-lookup"><span data-stu-id="d7281-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="d7281-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span><span class="sxs-lookup"><span data-stu-id="d7281-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7281-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7281-122">Requirements</span></span>  
 <span data-ttu-id="d7281-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7281-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7281-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7281-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7281-125">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7281-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7281-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7281-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7281-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7281-127">See also</span></span>

- [<span data-ttu-id="d7281-128">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d7281-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d7281-129">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d7281-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

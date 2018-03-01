---
title: Metodo IMetaDataImport::EnumUnresolvedMethods
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d4e77453fc11b77b602d4a89f0d90540c06b0a08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="58c25-102">Metodo IMetaDataImport::EnumUnresolvedMethods</span><span class="sxs-lookup"><span data-stu-id="58c25-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="58c25-103">Enumera i token MemberDef che rappresentano i metodi non risolti nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="58c25-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c25-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58c25-104">Syntax</span></span>  
  
```  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58c25-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58c25-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="58c25-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="58c25-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="58c25-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="58c25-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="58c25-108">[out] Matrice utilizzata per archiviare i token MemberDef.</span><span class="sxs-lookup"><span data-stu-id="58c25-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="58c25-109">[in] Dimensione massima della matrice `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="58c25-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="58c25-110">[out] Il numero di token MemberDef restituiti in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="58c25-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58c25-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="58c25-111">Return Value</span></span>  
  
|<span data-ttu-id="58c25-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58c25-112">HRESULT</span></span>|<span data-ttu-id="58c25-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58c25-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="58c25-114">`EnumUnresolvedMethods`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="58c25-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="58c25-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="58c25-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="58c25-116">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="58c25-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58c25-117">Note</span><span class="sxs-lookup"><span data-stu-id="58c25-117">Remarks</span></span>  
 <span data-ttu-id="58c25-118">Un metodo non risolto è quello che è stato dichiarato ma non implementato.</span><span class="sxs-lookup"><span data-stu-id="58c25-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="58c25-119">Un metodo è incluso nell'enumerazione se il metodo è contrassegnato come `miForwardRef` e `mdPinvokeImpl` o `miRuntime` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="58c25-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="58c25-120">In altre parole, un metodo non risolto è un metodo della classe che è contrassegnato come `miForwardRef` ma non è implementato nel codice non gestito (raggiunto tramite PInvoke) né implementato internamente dal runtime stesso.</span><span class="sxs-lookup"><span data-stu-id="58c25-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="58c25-121">L'enumerazione esclude tutti i metodi definiti nell'ambito del modulo (globals) o interfacce o classi astratte.</span><span class="sxs-lookup"><span data-stu-id="58c25-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c25-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58c25-122">Requirements</span></span>  
 <span data-ttu-id="58c25-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58c25-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c25-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="58c25-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58c25-125">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58c25-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58c25-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c25-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c25-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58c25-127">See Also</span></span>  
 [<span data-ttu-id="58c25-128">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="58c25-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="58c25-129">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="58c25-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

---
title: Metodo IMetaDataImport::EnumSignatures
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumSignatures
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 25fb32b0780dc91157d39ece37f93d7abd582cf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="fa2d0-102">Metodo IMetaDataImport::EnumSignatures</span><span class="sxs-lookup"><span data-stu-id="fa2d0-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="fa2d0-103">Enumera i token Signature che rappresentano le firme autonome nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa2d0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa2d0-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa2d0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa2d0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fa2d0-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fa2d0-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="fa2d0-108">[out] Matrice utilizzata per archiviare i token di firma.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fa2d0-109">[in] Dimensione massima della matrice `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="fa2d0-110">[out] Il numero di token di firma restituiti in `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa2d0-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fa2d0-111">Return Value</span></span>  
  
|<span data-ttu-id="fa2d0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa2d0-112">HRESULT</span></span>|<span data-ttu-id="fa2d0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa2d0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fa2d0-114">`EnumSignatures`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fa2d0-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fa2d0-116">In tal caso, `pcSignatures` è zero.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa2d0-117">Note</span><span class="sxs-lookup"><span data-stu-id="fa2d0-117">Remarks</span></span>  
 <span data-ttu-id="fa2d0-118">Vengono creati i token di firma di [GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="fa2d0-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa2d0-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa2d0-119">Requirements</span></span>  
 <span data-ttu-id="fa2d0-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa2d0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa2d0-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fa2d0-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa2d0-122">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa2d0-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa2d0-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa2d0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa2d0-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa2d0-124">See Also</span></span>  
 [<span data-ttu-id="fa2d0-125">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fa2d0-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="fa2d0-126">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fa2d0-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

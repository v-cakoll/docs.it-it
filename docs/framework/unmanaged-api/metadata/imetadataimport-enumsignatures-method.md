---
title: Metodo IMetaDataImport::EnumSignatures
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 193abe173b259ff2679642e229fce96151e37872
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179680"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="08f76-102">Metodo IMetaDataImport::EnumSignatures</span><span class="sxs-lookup"><span data-stu-id="08f76-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="08f76-103">Enumera i token Signature che rappresentano le firme autonome nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="08f76-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f76-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08f76-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08f76-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08f76-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="08f76-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="08f76-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="08f76-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="08f76-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="08f76-108">[out] Matrice utilizzata per archiviare i token di firma.</span><span class="sxs-lookup"><span data-stu-id="08f76-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="08f76-109">[in] Dimensione massima della matrice `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="08f76-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="08f76-110">[out] Il numero di token di firma restituita `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="08f76-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08f76-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08f76-111">Return Value</span></span>  
  
|<span data-ttu-id="08f76-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08f76-112">HRESULT</span></span>|<span data-ttu-id="08f76-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08f76-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumSignatures` <span data-ttu-id="08f76-114">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="08f76-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="08f76-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="08f76-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="08f76-116">In tal caso, `pcSignatures` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="08f76-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08f76-117">Note</span><span class="sxs-lookup"><span data-stu-id="08f76-117">Remarks</span></span>  
 <span data-ttu-id="08f76-118">I token di firma creati tramite il [GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="08f76-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f76-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08f76-119">Requirements</span></span>  
 <span data-ttu-id="08f76-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08f76-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f76-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="08f76-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08f76-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="08f76-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="08f76-123">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="08f76-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08f76-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08f76-124">See also</span></span>

- [<span data-ttu-id="08f76-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08f76-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="08f76-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08f76-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

---
title: Metodo IMetaDataImport::EnumModuleRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 294156983507476b7ddfda3bc3cad16bb32f422b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445409"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="d3510-102">Metodo IMetaDataImport::EnumModuleRefs</span><span class="sxs-lookup"><span data-stu-id="d3510-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="d3510-103">Enumera i token ModuleRef che rappresentano i moduli importati.</span><span class="sxs-lookup"><span data-stu-id="d3510-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3510-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3510-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3510-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3510-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d3510-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="d3510-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d3510-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="d3510-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="d3510-108">[out] Matrice utilizzata per archiviare i token ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="d3510-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d3510-109">[in] Dimensione massima della matrice `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="d3510-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="d3510-110">[out] Il numero di token ModuleRef restituiti in `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="d3510-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3510-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d3510-111">Return Value</span></span>  
  
|<span data-ttu-id="d3510-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3510-112">HRESULT</span></span>|<span data-ttu-id="d3510-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3510-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d3510-114">`EnumModuleRefs` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d3510-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d3510-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="d3510-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="d3510-116">In tal caso, `pcModuleRefs` è zero.</span><span class="sxs-lookup"><span data-stu-id="d3510-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3510-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3510-117">Requirements</span></span>  
 <span data-ttu-id="d3510-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3510-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3510-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d3510-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3510-120">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d3510-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3510-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3510-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3510-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3510-122">See Also</span></span>  
 [<span data-ttu-id="d3510-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d3510-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d3510-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d3510-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

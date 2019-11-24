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
ms.openlocfilehash: 66186d25e8fee0d6b25c0a2069d46ff9a104c625
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450040"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="e53b5-102">Metodo IMetaDataImport::EnumModuleRefs</span><span class="sxs-lookup"><span data-stu-id="e53b5-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="e53b5-103">Enumera i token ModuleRef che rappresentano i moduli importati.</span><span class="sxs-lookup"><span data-stu-id="e53b5-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e53b5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e53b5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e53b5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e53b5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e53b5-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="e53b5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e53b5-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="e53b5-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="e53b5-108">[out] The array used to store the ModuleRef tokens.</span><span class="sxs-lookup"><span data-stu-id="e53b5-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e53b5-109">[in] Dimensione massima della matrice `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="e53b5-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="e53b5-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="e53b5-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e53b5-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e53b5-111">Return Value</span></span>  
  
|<span data-ttu-id="e53b5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e53b5-112">HRESULT</span></span>|<span data-ttu-id="e53b5-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e53b5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e53b5-114">`EnumModuleRefs` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="e53b5-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e53b5-115">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="e53b5-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e53b5-116">In that case, `pcModuleRefs` is zero.</span><span class="sxs-lookup"><span data-stu-id="e53b5-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e53b5-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e53b5-117">Requirements</span></span>  
 <span data-ttu-id="e53b5-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e53b5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e53b5-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e53b5-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e53b5-120">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e53b5-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e53b5-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e53b5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e53b5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e53b5-122">See also</span></span>

- [<span data-ttu-id="e53b5-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e53b5-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e53b5-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e53b5-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

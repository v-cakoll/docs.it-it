---
title: Metodo IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: a43c1883038e41cac1b58c78bc26f20d436ebbd1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440247"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="e714f-102">Metodo IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="e714f-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="e714f-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span><span class="sxs-lookup"><span data-stu-id="e714f-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e714f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e714f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e714f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e714f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e714f-106">[in, out] A pointer to the returned enumerator.</span><span class="sxs-lookup"><span data-stu-id="e714f-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="e714f-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span><span class="sxs-lookup"><span data-stu-id="e714f-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="e714f-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span><span class="sxs-lookup"><span data-stu-id="e714f-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="e714f-109">[out] An array of custom attribute tokens.</span><span class="sxs-lookup"><span data-stu-id="e714f-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e714f-110">[in] Dimensione massima della matrice `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="e714f-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="e714f-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="e714f-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e714f-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e714f-112">Return Value</span></span>  
  
|<span data-ttu-id="e714f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e714f-113">HRESULT</span></span>|<span data-ttu-id="e714f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e714f-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e714f-115">`EnumCustomAttributes` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="e714f-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e714f-116">There are no custom attributes to enumerate.</span><span class="sxs-lookup"><span data-stu-id="e714f-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="e714f-117">In that case, `pcCustomAttributes` is zero.</span><span class="sxs-lookup"><span data-stu-id="e714f-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e714f-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e714f-118">Requirements</span></span>  
 <span data-ttu-id="e714f-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e714f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e714f-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e714f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e714f-121">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e714f-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e714f-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e714f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e714f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e714f-123">See also</span></span>

- [<span data-ttu-id="e714f-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e714f-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e714f-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e714f-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

---
title: Metodo IMetaDataImport::EnumParams
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
ms.openlocfilehash: e5fa3647c86d97730e7ad6a2576dd34af75251d6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433949"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="6295d-102">Metodo IMetaDataImport::EnumParams</span><span class="sxs-lookup"><span data-stu-id="6295d-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="6295d-103">Enumera i token ParamDef che rappresentano i parametri del metodo a cui fa riferimento il token MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="6295d-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6295d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6295d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6295d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6295d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6295d-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="6295d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6295d-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="6295d-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="6295d-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span><span class="sxs-lookup"><span data-stu-id="6295d-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="6295d-109">[out] The array used to store the ParamDef tokens.</span><span class="sxs-lookup"><span data-stu-id="6295d-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6295d-110">[in] Dimensione massima della matrice `rParams`.</span><span class="sxs-lookup"><span data-stu-id="6295d-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6295d-111">[out] The number of ParamDef tokens returned in `rParams`.</span><span class="sxs-lookup"><span data-stu-id="6295d-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6295d-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6295d-112">Return Value</span></span>  
  
|<span data-ttu-id="6295d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6295d-113">HRESULT</span></span>|<span data-ttu-id="6295d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6295d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6295d-115">`EnumParams` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="6295d-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6295d-116">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="6295d-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="6295d-117">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="6295d-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6295d-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6295d-118">Requirements</span></span>  
 <span data-ttu-id="6295d-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6295d-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6295d-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6295d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6295d-121">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6295d-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6295d-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6295d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6295d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6295d-123">See also</span></span>

- [<span data-ttu-id="6295d-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6295d-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6295d-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6295d-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

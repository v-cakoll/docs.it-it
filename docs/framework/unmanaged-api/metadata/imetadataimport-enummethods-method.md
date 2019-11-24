---
title: Metodo IMetaDataImport::EnumMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 8e9e08ac903423b2e121f22cc9e43a660ccfac7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450092"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="5ca76-102">Metodo IMetaDataImport::EnumMethods</span><span class="sxs-lookup"><span data-stu-id="5ca76-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="5ca76-103">Enumera i token MethodDef che rappresentano i metodi del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="5ca76-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ca76-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ca76-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ca76-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5ca76-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5ca76-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="5ca76-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5ca76-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="5ca76-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="5ca76-108">[in] A TypeDef token representing the type with the methods to enumerate.</span><span class="sxs-lookup"><span data-stu-id="5ca76-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="5ca76-109">[out] The array to store the MethodDef tokens.</span><span class="sxs-lookup"><span data-stu-id="5ca76-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5ca76-110">[in] The maximum size of the MethodDef `rMethods` array.</span><span class="sxs-lookup"><span data-stu-id="5ca76-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5ca76-111">[out] The number of MethodDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="5ca76-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ca76-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5ca76-112">Return Value</span></span>  
  
|<span data-ttu-id="5ca76-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ca76-113">HRESULT</span></span>|<span data-ttu-id="5ca76-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ca76-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5ca76-115">`EnumMethods` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="5ca76-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5ca76-116">There are no MethodDef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="5ca76-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="5ca76-117">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="5ca76-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ca76-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ca76-118">Requirements</span></span>  
 <span data-ttu-id="5ca76-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ca76-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ca76-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ca76-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ca76-121">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ca76-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ca76-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ca76-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca76-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ca76-123">See also</span></span>

- [<span data-ttu-id="5ca76-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5ca76-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5ca76-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5ca76-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

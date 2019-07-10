---
title: Metodo IMetaDataImport::EnumMethodsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5de55d74741e9deb33be2f9adf15a970561664b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779728"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="ca78d-102">Metodo IMetaDataImport::EnumMethodsWithName</span><span class="sxs-lookup"><span data-stu-id="ca78d-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="ca78d-103">Enumera i metodi che hanno il nome specificato e che sono definiti dal tipo a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="ca78d-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca78d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca78d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca78d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca78d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ca78d-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="ca78d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ca78d-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="ca78d-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="ca78d-108">[in] Token TypeDef che rappresenta il tipo i cui metodi per enumerare.</span><span class="sxs-lookup"><span data-stu-id="ca78d-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="ca78d-109">[in] Il nome che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ca78d-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="ca78d-110">[out] Matrice utilizzata per archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="ca78d-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ca78d-111">[in] Dimensione massima della matrice `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="ca78d-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ca78d-112">[out] Il numero di token MethodDef restituiti in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="ca78d-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca78d-113">Note</span><span class="sxs-lookup"><span data-stu-id="ca78d-113">Remarks</span></span>  
 <span data-ttu-id="ca78d-114">Questo metodo enumera i campi e metodi, ma non le proprietà o eventi.</span><span class="sxs-lookup"><span data-stu-id="ca78d-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="ca78d-115">A differenza [EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` Elimina tutti i token che non è il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="ca78d-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca78d-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ca78d-116">Return Value</span></span>  
  
|<span data-ttu-id="ca78d-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca78d-117">HRESULT</span></span>|<span data-ttu-id="ca78d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca78d-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ca78d-119">`EnumMethodsWithName` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ca78d-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ca78d-120">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="ca78d-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="ca78d-121">In tal caso, `pcTokens` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="ca78d-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca78d-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca78d-122">Requirements</span></span>  
 <span data-ttu-id="ca78d-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca78d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca78d-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ca78d-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca78d-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ca78d-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca78d-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca78d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca78d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca78d-127">See also</span></span>

- [<span data-ttu-id="ca78d-128">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ca78d-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ca78d-129">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ca78d-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

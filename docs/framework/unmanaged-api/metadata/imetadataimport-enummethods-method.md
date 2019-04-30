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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bab625b8415183b9cf90c35cba140c4d28095805
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992446"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="b0914-102">Metodo IMetaDataImport::EnumMethods</span><span class="sxs-lookup"><span data-stu-id="b0914-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="b0914-103">Enumera i token MethodDef che rappresentano i metodi del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="b0914-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0914-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0914-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0914-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0914-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b0914-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="b0914-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b0914-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="b0914-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="b0914-108">[in] Token TypeDef che rappresenta il tipo con i metodi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="b0914-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="b0914-109">[out] Matrice in cui archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="b0914-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b0914-110">[in] Le dimensioni massime di MethodDef `rMethods` matrice.</span><span class="sxs-lookup"><span data-stu-id="b0914-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b0914-111">[out] Il numero di token MethodDef restituiti in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="b0914-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0914-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b0914-112">Return Value</span></span>  
  
|<span data-ttu-id="b0914-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0914-113">HRESULT</span></span>|<span data-ttu-id="b0914-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0914-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b0914-115">`EnumMethods` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b0914-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b0914-116">Non sono presenti token MethodDef per enumerare.</span><span class="sxs-lookup"><span data-stu-id="b0914-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="b0914-117">In tal caso, `pcTokens` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="b0914-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0914-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0914-118">Requirements</span></span>  
 <span data-ttu-id="b0914-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0914-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0914-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b0914-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0914-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b0914-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0914-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0914-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0914-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0914-123">See also</span></span>

- [<span data-ttu-id="b0914-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b0914-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b0914-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b0914-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

---
title: Metodo IMetaDataImport::EnumEvents
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 608b4a7d147124ede60e9d81f91600dfdaad0a65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446496"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="f0a86-102">Metodo IMetaDataImport::EnumEvents</span><span class="sxs-lookup"><span data-stu-id="f0a86-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="f0a86-103">Enumera i token di definizione di evento per il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="f0a86-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0a86-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0a86-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0a86-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f0a86-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="f0a86-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="f0a86-107">[in] Il token TypeDef sono le cui definizioni di evento da enumerare.</span><span class="sxs-lookup"><span data-stu-id="f0a86-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="f0a86-108">[out] Matrice di eventi restituiti.</span><span class="sxs-lookup"><span data-stu-id="f0a86-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f0a86-109">[in] Dimensione massima della matrice `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="f0a86-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="f0a86-110">[out] Il numero effettivo di eventi restituiti in `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="f0a86-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0a86-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f0a86-111">Return Value</span></span>  
  
|<span data-ttu-id="f0a86-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0a86-112">HRESULT</span></span>|<span data-ttu-id="f0a86-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0a86-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f0a86-114">`EnumEvents` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f0a86-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f0a86-115">Non sono presenti eventi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="f0a86-115">There are no events to enumerate.</span></span> <span data-ttu-id="f0a86-116">In tal caso, `pcEvents` è zero.</span><span class="sxs-lookup"><span data-stu-id="f0a86-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0a86-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0a86-117">Requirements</span></span>  
 <span data-ttu-id="f0a86-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0a86-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a86-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f0a86-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0a86-120">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f0a86-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f0a86-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0a86-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a86-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0a86-122">See Also</span></span>  
 [<span data-ttu-id="f0a86-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f0a86-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f0a86-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f0a86-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

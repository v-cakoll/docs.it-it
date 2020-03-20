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
ms.openlocfilehash: bd50d63b1f7080f510c29f90979b7b36242af1c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177376"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="35d97-102">Metodo IMetaDataImport::EnumEvents</span><span class="sxs-lookup"><span data-stu-id="35d97-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="35d97-103">Enumera i token di definizione di evento per il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="35d97-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35d97-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35d97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35d97-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="35d97-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="35d97-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="35d97-107">[in] Token TypeDef le cui definizioni di evento devono essere enumerate.</span><span class="sxs-lookup"><span data-stu-id="35d97-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="35d97-108">[fuori] Matrice di eventi restituiti.</span><span class="sxs-lookup"><span data-stu-id="35d97-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="35d97-109">[in] Dimensione massima della matrice `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="35d97-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="35d97-110">[fuori] Numero effettivo di eventi `rEvents`restituiti in .</span><span class="sxs-lookup"><span data-stu-id="35d97-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35d97-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="35d97-111">Return Value</span></span>  
  
|<span data-ttu-id="35d97-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35d97-112">HRESULT</span></span>|<span data-ttu-id="35d97-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35d97-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="35d97-114">`EnumEvents`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="35d97-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="35d97-115">Non sono presenti eventi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="35d97-115">There are no events to enumerate.</span></span> <span data-ttu-id="35d97-116">In tal `pcEvents` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="35d97-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35d97-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35d97-117">Requirements</span></span>  
 <span data-ttu-id="35d97-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35d97-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35d97-119">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35d97-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35d97-120">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35d97-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35d97-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d97-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d97-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35d97-122">See also</span></span>

- [<span data-ttu-id="35d97-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="35d97-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="35d97-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="35d97-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

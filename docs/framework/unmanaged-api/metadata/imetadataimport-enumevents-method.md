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
ms.openlocfilehash: 4faf8646b81f92ddf65eff15fdc610d275b37864
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440017"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="da2ad-102">Metodo IMetaDataImport::EnumEvents</span><span class="sxs-lookup"><span data-stu-id="da2ad-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="da2ad-103">Enumera i token di definizione di evento per il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="da2ad-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da2ad-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da2ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da2ad-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="da2ad-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="da2ad-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="da2ad-107">in Token TypeDef le cui definizioni di evento devono essere enumerate.</span><span class="sxs-lookup"><span data-stu-id="da2ad-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="da2ad-108">out Matrice degli eventi restituiti.</span><span class="sxs-lookup"><span data-stu-id="da2ad-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="da2ad-109">[in] Dimensione massima della matrice `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="da2ad-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="da2ad-110">out Numero effettivo di eventi restituiti in `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="da2ad-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da2ad-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="da2ad-111">Return Value</span></span>  
  
|<span data-ttu-id="da2ad-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da2ad-112">HRESULT</span></span>|<span data-ttu-id="da2ad-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da2ad-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="da2ad-114">`EnumEvents` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="da2ad-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="da2ad-115">Nessun evento da enumerare.</span><span class="sxs-lookup"><span data-stu-id="da2ad-115">There are no events to enumerate.</span></span> <span data-ttu-id="da2ad-116">In tal caso, `pcEvents` è zero.</span><span class="sxs-lookup"><span data-stu-id="da2ad-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da2ad-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da2ad-117">Requirements</span></span>  
 <span data-ttu-id="da2ad-118">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da2ad-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da2ad-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="da2ad-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da2ad-120">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="da2ad-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da2ad-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da2ad-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2ad-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da2ad-122">See also</span></span>

- [<span data-ttu-id="da2ad-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="da2ad-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="da2ad-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="da2ad-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

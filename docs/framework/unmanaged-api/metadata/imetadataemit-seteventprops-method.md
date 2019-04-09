---
title: Metodo IMetaDataEmit::SetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abfa8a3f58d3e9f7c80762c1faf2bc51514d71b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113815"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="2480d-102">Metodo IMetaDataEmit::SetEventProps</span><span class="sxs-lookup"><span data-stu-id="2480d-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="2480d-103">Imposta o aggiorna la funzionalità specificata di un evento definito da una chiamata precedente a [DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="2480d-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2480d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2480d-104">Syntax</span></span>  
  
```  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,   
    [in]  DWORD       dwEventFlags,   
    [in]  mdToken     tkEventType,   
    [in]  mdMethodDef mdAddOn,   
    [in]  mdMethodDef mdRemoveOn,   
    [in]  mdMethodDef mdFire,   
    [in]  mdMethodDef rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2480d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2480d-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="2480d-106">[in] Il token di evento.</span><span class="sxs-lookup"><span data-stu-id="2480d-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="2480d-107">[in] Flag dell'evento.</span><span class="sxs-lookup"><span data-stu-id="2480d-107">[in] Event flags.</span></span> <span data-ttu-id="2480d-108">Si tratta di una maschera di bit delle `CorEventAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="2480d-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="2480d-109">[in] Il token per la classe di evento.</span><span class="sxs-lookup"><span data-stu-id="2480d-109">[in] The token for the event class.</span></span> <span data-ttu-id="2480d-110">Questo è un `mdTypeDef` o un `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="2480d-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="2480d-111">[in] Il metodo utilizzato per sottoscrivere l'evento, o null.</span><span class="sxs-lookup"><span data-stu-id="2480d-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="2480d-112">[in] Il metodo utilizzato per annullare la sottoscrizione per l'evento, o null.</span><span class="sxs-lookup"><span data-stu-id="2480d-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="2480d-113">[in] Il metodo utilizzato (da una classe derivata) per generare l'evento.</span><span class="sxs-lookup"><span data-stu-id="2480d-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="2480d-114">[in] Matrice dei token per gli altri metodi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="2480d-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="2480d-115">L'ultimo elemento della matrice deve essere `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="2480d-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2480d-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2480d-116">Requirements</span></span>  
 <span data-ttu-id="2480d-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2480d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2480d-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2480d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2480d-119">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2480d-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2480d-120">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2480d-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2480d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2480d-121">See also</span></span>

- [<span data-ttu-id="2480d-122">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2480d-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2480d-123">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2480d-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

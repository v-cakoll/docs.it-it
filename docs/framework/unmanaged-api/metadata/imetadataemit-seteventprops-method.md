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
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177523"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="76907-102">Metodo IMetaDataEmit::SetEventProps</span><span class="sxs-lookup"><span data-stu-id="76907-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="76907-103">Imposta o aggiorna la funzionalità specificata di un evento definito da una precedente chiamata a [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="76907-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76907-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76907-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="76907-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="76907-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="76907-106">[in] Token dell'evento.</span><span class="sxs-lookup"><span data-stu-id="76907-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="76907-107">[in] Flag di evento.</span><span class="sxs-lookup"><span data-stu-id="76907-107">[in] Event flags.</span></span> <span data-ttu-id="76907-108">Si tratta di `CorEventAttr` una maschera di bit di valori.</span><span class="sxs-lookup"><span data-stu-id="76907-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="76907-109">[in] Token per la classe di evento.</span><span class="sxs-lookup"><span data-stu-id="76907-109">[in] The token for the event class.</span></span> <span data-ttu-id="76907-110">Si tratta `mdTypeDef` di `mdTypeRef` un o un token.</span><span class="sxs-lookup"><span data-stu-id="76907-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="76907-111">[in] Metodo utilizzato per sottoscrivere l'evento o null.</span><span class="sxs-lookup"><span data-stu-id="76907-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="76907-112">[in] Metodo utilizzato per annullare la sottoscrizione all'evento o null.</span><span class="sxs-lookup"><span data-stu-id="76907-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="76907-113">[in] Metodo utilizzato (da una classe derivata) per generare l'evento.</span><span class="sxs-lookup"><span data-stu-id="76907-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="76907-114">[in] Matrice di token per altri metodi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="76907-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="76907-115">L'ultimo elemento della `mdMethodDefNil`matrice deve essere .</span><span class="sxs-lookup"><span data-stu-id="76907-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76907-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76907-116">Requirements</span></span>  
 <span data-ttu-id="76907-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76907-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76907-118">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="76907-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76907-119">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76907-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76907-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76907-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76907-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76907-121">See also</span></span>

- [<span data-ttu-id="76907-122">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="76907-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="76907-123">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="76907-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

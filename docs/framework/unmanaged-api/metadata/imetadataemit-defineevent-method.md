---
title: Metodo IMetaDataEmit::DefineEvent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175850"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="92c6b-102">Metodo IMetaDataEmit::DefineEvent</span><span class="sxs-lookup"><span data-stu-id="92c6b-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="92c6b-103">Crea una definizione per un evento con la firma dei metadati specificata e ottiene un token per tale definizione di evento.</span><span class="sxs-lookup"><span data-stu-id="92c6b-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92c6b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92c6b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="92c6b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="92c6b-106">[in] Token per la classe o l'interfaccia di destinazione.</span><span class="sxs-lookup"><span data-stu-id="92c6b-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="92c6b-107">Si tratta `mdTypeDef` di `mdTypeDefNil` un o token.</span><span class="sxs-lookup"><span data-stu-id="92c6b-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="92c6b-108">[in] Nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="92c6b-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="92c6b-109">[in] Flag di evento.</span><span class="sxs-lookup"><span data-stu-id="92c6b-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="92c6b-110">[in] Token per la classe di evento.</span><span class="sxs-lookup"><span data-stu-id="92c6b-110">[in] The token for the event class.</span></span> <span data-ttu-id="92c6b-111">Si tratta `mdTypeDef`di `mdTypeRef`un, `mdTokenNil` un oggetto o un token.</span><span class="sxs-lookup"><span data-stu-id="92c6b-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="92c6b-112">[in] Metodo utilizzato per sottoscrivere l'evento o null.</span><span class="sxs-lookup"><span data-stu-id="92c6b-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="92c6b-113">[in] Metodo utilizzato per annullare la sottoscrizione all'evento o null.</span><span class="sxs-lookup"><span data-stu-id="92c6b-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="92c6b-114">[in] Metodo utilizzato (da una classe derivata) per generare l'evento.</span><span class="sxs-lookup"><span data-stu-id="92c6b-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="92c6b-115">[in] Matrice di token per altri metodi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="92c6b-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="92c6b-116">La matrice viene terminata con un `mdMethodDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="92c6b-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="92c6b-117">[fuori] Token di metadati assegnato all'evento.</span><span class="sxs-lookup"><span data-stu-id="92c6b-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c6b-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92c6b-118">Requirements</span></span>  
 <span data-ttu-id="92c6b-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92c6b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92c6b-120">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92c6b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92c6b-121">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92c6b-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92c6b-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92c6b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c6b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92c6b-123">See also</span></span>

- [<span data-ttu-id="92c6b-124">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="92c6b-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="92c6b-125">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="92c6b-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

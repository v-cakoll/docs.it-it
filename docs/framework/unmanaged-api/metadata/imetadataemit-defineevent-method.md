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
ms.openlocfilehash: 6966d0ad2fefd8401b19d8e8dcf7776799a066b2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432559"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="e779f-102">Metodo IMetaDataEmit::DefineEvent</span><span class="sxs-lookup"><span data-stu-id="e779f-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="e779f-103">Crea una definizione per un evento con la firma dei metadati specificata e ottiene un token per la definizione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e779f-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e779f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e779f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e779f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e779f-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e779f-106">in Token per la classe o l'interfaccia di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e779f-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="e779f-107">Si tratta di un token `mdTypeDef` o `mdTypeDefNil`.</span><span class="sxs-lookup"><span data-stu-id="e779f-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="e779f-108">in Nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e779f-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="e779f-109">in Flag evento.</span><span class="sxs-lookup"><span data-stu-id="e779f-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="e779f-110">in Token per la classe di evento.</span><span class="sxs-lookup"><span data-stu-id="e779f-110">[in] The token for the event class.</span></span> <span data-ttu-id="e779f-111">Si tratta di un `mdTypeDef`, un `mdTypeRef`o un token di `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="e779f-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="e779f-112">in Metodo utilizzato per sottoscrivere l'evento o null.</span><span class="sxs-lookup"><span data-stu-id="e779f-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="e779f-113">in Metodo utilizzato per annullare la sottoscrizione dell'evento o null.</span><span class="sxs-lookup"><span data-stu-id="e779f-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="e779f-114">in Metodo usato (da una classe derivata) per generare l'evento.</span><span class="sxs-lookup"><span data-stu-id="e779f-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="e779f-115">in Matrice di token per altri metodi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="e779f-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="e779f-116">La matrice viene terminata con un token di `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="e779f-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="e779f-117">out Token di metadati assegnato all'evento.</span><span class="sxs-lookup"><span data-stu-id="e779f-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e779f-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e779f-118">Requirements</span></span>  
 <span data-ttu-id="e779f-119">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e779f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e779f-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e779f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e779f-121">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e779f-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e779f-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e779f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e779f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e779f-123">See also</span></span>

- [<span data-ttu-id="e779f-124">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e779f-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e779f-125">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e779f-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

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
ms.openlocfilehash: 720133e64c02aa09c9ff7e43a20630b0d55c1acf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008755"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="8296d-102">Metodo IMetaDataEmit::SetEventProps</span><span class="sxs-lookup"><span data-stu-id="8296d-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="8296d-103">Imposta o aggiorna la funzionalità specificata di un evento definito da una chiamata precedente a [IMetaDataEmit::D efineevent](imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="8296d-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8296d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8296d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8296d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8296d-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="8296d-106">in Token dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8296d-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="8296d-107">in Flag evento.</span><span class="sxs-lookup"><span data-stu-id="8296d-107">[in] Event flags.</span></span> <span data-ttu-id="8296d-108">Si tratta di una maschera di maschera di `CorEventAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="8296d-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="8296d-109">in Token per la classe di evento.</span><span class="sxs-lookup"><span data-stu-id="8296d-109">[in] The token for the event class.</span></span> <span data-ttu-id="8296d-110">Si tratta di un `mdTypeDef` token o `mdTypeRef` .</span><span class="sxs-lookup"><span data-stu-id="8296d-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="8296d-111">in Metodo utilizzato per sottoscrivere l'evento o null.</span><span class="sxs-lookup"><span data-stu-id="8296d-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="8296d-112">in Metodo utilizzato per annullare la sottoscrizione dell'evento o null.</span><span class="sxs-lookup"><span data-stu-id="8296d-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="8296d-113">in Metodo usato (da una classe derivata) per generare l'evento.</span><span class="sxs-lookup"><span data-stu-id="8296d-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="8296d-114">in Matrice di token per altri metodi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="8296d-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="8296d-115">L'ultimo elemento della matrice deve essere `mdMethodDefNil` .</span><span class="sxs-lookup"><span data-stu-id="8296d-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8296d-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8296d-116">Requirements</span></span>  
 <span data-ttu-id="8296d-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8296d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8296d-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8296d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8296d-119">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8296d-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8296d-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8296d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8296d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8296d-121">See also</span></span>

- [<span data-ttu-id="8296d-122">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8296d-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8296d-123">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8296d-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

---
title: Metodo IMetaDataEmit::SetCustomAttributeValue
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: 6e24db7da7abbdb597b8ff64515e8053667af3ff
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008768"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="beab0-102">Metodo IMetaDataEmit::SetCustomAttributeValue</span><span class="sxs-lookup"><span data-stu-id="beab0-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="beab0-103">Imposta o aggiorna il valore di un attributo personalizzato definito da una chiamata precedente a [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="beab0-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beab0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="beab0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="beab0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="beab0-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="beab0-106">in Token dell'attributo personalizzato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="beab0-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="beab0-107">in Puntatore alla matrice che contiene l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="beab0-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="beab0-108">in Dimensione, in byte, dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="beab0-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beab0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="beab0-109">Requirements</span></span>  
 <span data-ttu-id="beab0-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beab0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beab0-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="beab0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="beab0-112">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="beab0-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="beab0-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beab0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beab0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="beab0-114">See also</span></span>

- [<span data-ttu-id="beab0-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="beab0-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="beab0-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="beab0-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

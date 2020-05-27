---
title: Metodo IMetaDataEmit::SetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: 3059d30f3969b4e19cee5a8d7a34c606f3849c05
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008742"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="8bbc8-102">Metodo IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="8bbc8-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="8bbc8-103">Imposta l'indirizzo virtuale relativo del metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="8bbc8-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bbc8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8bbc8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bbc8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8bbc8-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="8bbc8-106">in Token per l'implementazione del metodo o del metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8bbc8-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="8bbc8-107">in Indirizzo del codice o dell'area dati.</span><span class="sxs-lookup"><span data-stu-id="8bbc8-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bbc8-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8bbc8-108">Requirements</span></span>  
 <span data-ttu-id="8bbc8-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bbc8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bbc8-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8bbc8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bbc8-111">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8bbc8-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bbc8-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bbc8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bbc8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bbc8-113">See also</span></span>

- [<span data-ttu-id="8bbc8-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8bbc8-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8bbc8-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8bbc8-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

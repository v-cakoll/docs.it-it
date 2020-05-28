---
title: Metodo IMetaDataEmit::SaveToMemory
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
ms.openlocfilehash: ccf82531eb1f78bcfc6762d10d53ffee59f30ad8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003949"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="e7702-102">Metodo IMetaDataEmit::SaveToMemory</span><span class="sxs-lookup"><span data-stu-id="e7702-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="e7702-103">Salva tutti i metadati nell'ambito corrente nell'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="e7702-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7702-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7702-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7702-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7702-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="e7702-106">out Indirizzo da cui iniziare la scrittura dei metadati.</span><span class="sxs-lookup"><span data-stu-id="e7702-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="e7702-107">in Dimensione, in byte, della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="e7702-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7702-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7702-108">Requirements</span></span>  
 <span data-ttu-id="e7702-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7702-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7702-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e7702-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7702-111">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e7702-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7702-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7702-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7702-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7702-113">See also</span></span>

- [<span data-ttu-id="e7702-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e7702-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e7702-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e7702-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

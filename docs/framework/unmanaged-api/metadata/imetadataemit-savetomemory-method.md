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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e32c0ace5f999a75220d0d093b85e0cbbfc73889
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757577"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="45c7a-102">Metodo IMetaDataEmit::SaveToMemory</span><span class="sxs-lookup"><span data-stu-id="45c7a-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="45c7a-103">Salva tutti i metadati nell'ambito corrente per l'area specificata di memoria.</span><span class="sxs-lookup"><span data-stu-id="45c7a-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45c7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45c7a-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45c7a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="45c7a-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="45c7a-106">[out] L'indirizzo in corrispondenza del quale iniziare la scrittura dei metadati.</span><span class="sxs-lookup"><span data-stu-id="45c7a-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="45c7a-107">[in] Le dimensioni, in byte, della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="45c7a-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45c7a-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45c7a-108">Requirements</span></span>  
 <span data-ttu-id="45c7a-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45c7a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45c7a-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="45c7a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45c7a-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="45c7a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45c7a-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45c7a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c7a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45c7a-113">See also</span></span>

- [<span data-ttu-id="45c7a-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="45c7a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="45c7a-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="45c7a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

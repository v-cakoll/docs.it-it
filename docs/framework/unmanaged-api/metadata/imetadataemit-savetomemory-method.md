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
ms.openlocfilehash: d8843b2b5f69696dc206e9b530e3062ff225e89e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177573"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="6b3ff-102">Metodo IMetaDataEmit::SaveToMemory</span><span class="sxs-lookup"><span data-stu-id="6b3ff-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="6b3ff-103">Salva tutti i metadati nell'ambito corrente nell'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b3ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b3ff-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b3ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b3ff-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="6b3ff-106">[fuori] Indirizzo in corrispondenza del quale iniziare a scrivere i metadati.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="6b3ff-107">[in] Dimensione, in byte, della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b3ff-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b3ff-108">Requirements</span></span>  
 <span data-ttu-id="6b3ff-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b3ff-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b3ff-110">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6b3ff-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b3ff-111">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b3ff-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b3ff-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b3ff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b3ff-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b3ff-113">See also</span></span>

- [<span data-ttu-id="6b3ff-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6b3ff-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6b3ff-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6b3ff-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

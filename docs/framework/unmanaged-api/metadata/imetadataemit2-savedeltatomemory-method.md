---
title: Metodo IMetaDataEmit2::SaveDeltaToMemory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8f4243840ac64a14b4f4e6c86787fdf238507635
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="85cbb-102">Metodo IMetaDataEmit2::SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="85cbb-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="85cbb-103">Salva le modifiche dalla sessione corrente di modifica e continuazione in memoria.</span><span class="sxs-lookup"><span data-stu-id="85cbb-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85cbb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85cbb-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85cbb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="85cbb-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="85cbb-106">[out] L'indirizzo in corrispondenza del quale iniziare a scrivere il delta dei metadati.</span><span class="sxs-lookup"><span data-stu-id="85cbb-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="85cbb-107">[in] Le dimensioni delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="85cbb-107">[in] The size of the changes.</span></span> <span data-ttu-id="85cbb-108">Utilizzare [IMetaDataEmit2:: GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) per determinare le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="85cbb-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85cbb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85cbb-109">Requirements</span></span>  
 <span data-ttu-id="85cbb-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85cbb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85cbb-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="85cbb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85cbb-112">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85cbb-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85cbb-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85cbb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85cbb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85cbb-114">See Also</span></span>  
 [<span data-ttu-id="85cbb-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="85cbb-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="85cbb-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="85cbb-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

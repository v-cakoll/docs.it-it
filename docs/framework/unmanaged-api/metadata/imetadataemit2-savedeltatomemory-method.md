---
title: Metodo IMetaDataEmit2::SaveDeltaToMemory
ms.date: 03/30/2017
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
ms.openlocfilehash: 5ec4fe2a8e949cf6e9aa0ce68f4d4e49b72170b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177441"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="86fdb-102">Metodo IMetaDataEmit2::SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="86fdb-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="86fdb-103">Salva in memoria le modifiche della sessione di modifica e continuazione corrente.</span><span class="sxs-lookup"><span data-stu-id="86fdb-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86fdb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86fdb-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86fdb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86fdb-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="86fdb-106">[fuori] Indirizzo in corrispondenza del quale iniziare a scrivere il delta dei metadati.</span><span class="sxs-lookup"><span data-stu-id="86fdb-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="86fdb-107">[in] La dimensione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="86fdb-107">[in] The size of the changes.</span></span> <span data-ttu-id="86fdb-108">Utilizzare [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) per determinare le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="86fdb-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86fdb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86fdb-109">Requirements</span></span>  
 <span data-ttu-id="86fdb-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86fdb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86fdb-111">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86fdb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86fdb-112">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86fdb-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86fdb-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86fdb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86fdb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86fdb-114">See also</span></span>

- [<span data-ttu-id="86fdb-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="86fdb-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="86fdb-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="86fdb-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

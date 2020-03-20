---
title: Metodo IMetaDataEmit2::SaveDeltaToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: 7e8376f3a029b0e3ec51a1e7587dd14b3e7530ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177417"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="bcbe6-102">Metodo IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="bcbe6-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="bcbe6-103">Salva le modifiche dalla sessione di modifica e continuazione corrente nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="bcbe6-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcbe6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcbe6-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcbe6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bcbe6-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="bcbe6-106">[in] Puntatore a interfaccia al flusso scrivibile in cui salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="bcbe6-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="bcbe6-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="bcbe6-107">[in] Reserved.</span></span> <span data-ttu-id="bcbe6-108">Il valore deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="bcbe6-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcbe6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bcbe6-109">Requirements</span></span>  
 <span data-ttu-id="bcbe6-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcbe6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcbe6-111">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bcbe6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bcbe6-112">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bcbe6-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bcbe6-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcbe6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbe6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcbe6-114">See also</span></span>

- [<span data-ttu-id="bcbe6-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bcbe6-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="bcbe6-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bcbe6-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

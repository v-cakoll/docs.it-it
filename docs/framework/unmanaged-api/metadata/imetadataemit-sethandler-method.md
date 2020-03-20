---
title: Metodo IMetaDataEmit::SetHandler
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 375c4b2cece0bdfd763ae383c5412c9e25614baf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177537"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="e2b4a-102">Metodo IMetaDataEmit::SetHandler</span><span class="sxs-lookup"><span data-stu-id="e2b4a-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="e2b4a-103">Imposta il metodo a `IUnknown` cui fa riferimento il puntatore specificato come callback di notifica per i rimappato del token.</span><span class="sxs-lookup"><span data-stu-id="e2b4a-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b4a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2b4a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2b4a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2b4a-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="e2b4a-106">[in] Gestore da registrare.</span><span class="sxs-lookup"><span data-stu-id="e2b4a-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2b4a-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e2b4a-107">Remarks</span></span>  
 <span data-ttu-id="e2b4a-108">Il motore dei metadati invia una `SetHandler`notifica utilizzando il metodo fornito da , ai compilatori che non generano record in modo ottimizzato e che desiderano ottimizzare i record salvati.</span><span class="sxs-lookup"><span data-stu-id="e2b4a-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="e2b4a-109">Se il metodo di `SetHandler`callback non viene fornito tramite , non verrà eseguita alcuna ottimizzazione al salvataggio, tranne quando sono stati uniti diversi ambiti di importazione utilizzando `IMapToken` in un'unione per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="e2b4a-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2b4a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2b4a-110">Requirements</span></span>  
 <span data-ttu-id="e2b4a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2b4a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2b4a-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e2b4a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2b4a-113">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2b4a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2b4a-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2b4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b4a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2b4a-115">See also</span></span>

- [<span data-ttu-id="e2b4a-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e2b4a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e2b4a-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e2b4a-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

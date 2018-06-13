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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60c9266806ef6b5d7e2e1c3a219a4485bc22d7f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445520"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="77d02-102">Metodo IMetaDataEmit::SetHandler</span><span class="sxs-lookup"><span data-stu-id="77d02-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="77d02-103">Imposta il metodo a cui fa riferimento specificato `IUnknown` puntatore come un callback di notifica per i nuovi mapping token.</span><span class="sxs-lookup"><span data-stu-id="77d02-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77d02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77d02-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77d02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="77d02-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="77d02-106">[in] Gestore da registrare.</span><span class="sxs-lookup"><span data-stu-id="77d02-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77d02-107">Note</span><span class="sxs-lookup"><span data-stu-id="77d02-107">Remarks</span></span>  
 <span data-ttu-id="77d02-108">Il motore dei metadati invia notifica tramite il metodo che viene fornito da `SetHandler`, per i compilatori che non generano record in modo ottimizzato e che si desidera ottimizzare i record salvati.</span><span class="sxs-lookup"><span data-stu-id="77d02-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="77d02-109">Se il metodo di callback non viene fornito tramite `SetHandler`, verrà eseguita alcuna ottimizzazione su Salva tranne diversi in cui importare gli ambiti vengono uniti utilizzando `IMapToken` merge per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="77d02-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77d02-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77d02-110">Requirements</span></span>  
 <span data-ttu-id="77d02-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77d02-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77d02-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="77d02-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77d02-113">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="77d02-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77d02-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77d02-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77d02-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77d02-115">See Also</span></span>  
 [<span data-ttu-id="77d02-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="77d02-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="77d02-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="77d02-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

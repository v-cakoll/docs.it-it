---
title: Metodo ICorPublishProcess::EnumAppDomains
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5492d4e1245c6c0ce5c1eb98d25168c5d69d123b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423702"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="1de67-102">Metodo ICorPublishProcess::EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="1de67-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="1de67-103">Ottiene un enumeratore per i domini applicazione nel processo di cui fa riferimento questo [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1de67-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1de67-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1de67-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1de67-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="1de67-106">[out] Un puntatore all'indirizzo di un [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) istanza che consente l'iterazione attraverso la raccolta di domini applicazione nel processo.</span><span class="sxs-lookup"><span data-stu-id="1de67-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1de67-107">Note</span><span class="sxs-lookup"><span data-stu-id="1de67-107">Remarks</span></span>  
 <span data-ttu-id="1de67-108">L'elenco dei domini applicazione si basa su uno snapshot dei domini dell'applicazione che esiste quando il `EnumAppDomains` metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="1de67-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="1de67-109">Questo metodo può essere chiamato più volte per creare un nuovo elenco aggiornato.</span><span class="sxs-lookup"><span data-stu-id="1de67-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="1de67-110">Elenchi esistenti non influiranno le chiamate successive di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="1de67-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="1de67-111">Se il processo è stato terminato, `EnumAppDomains` avrà esito negativo con un valore HRESULT di CORDBG_E_PROCESS_TERMINATED.</span><span class="sxs-lookup"><span data-stu-id="1de67-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de67-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1de67-112">Requirements</span></span>  
 <span data-ttu-id="1de67-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1de67-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de67-114">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1de67-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1de67-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1de67-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1de67-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de67-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de67-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1de67-117">See Also</span></span>  
 [<span data-ttu-id="1de67-118">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="1de67-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)

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
ms.openlocfilehash: 4799c1d04e8172c604eeec50f2b841a6db063949
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790576"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="3d958-102">Metodo ICorPublishProcess::EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="3d958-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="3d958-103">Ottiene un enumeratore per i domini applicazione nel processo a cui fa riferimento questo [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3d958-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d958-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d958-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d958-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d958-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3d958-106">out Puntatore all'indirizzo di un'istanza di [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) che consente l'iterazione nella raccolta di domini applicazione in questo processo.</span><span class="sxs-lookup"><span data-stu-id="3d958-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d958-107">Note</span><span class="sxs-lookup"><span data-stu-id="3d958-107">Remarks</span></span>  
 <span data-ttu-id="3d958-108">L'elenco dei domini applicazione si basa su uno snapshot dei domini applicazione esistenti quando viene chiamato il metodo `EnumAppDomains`.</span><span class="sxs-lookup"><span data-stu-id="3d958-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="3d958-109">Questo metodo può essere chiamato più volte per creare un nuovo elenco aggiornato.</span><span class="sxs-lookup"><span data-stu-id="3d958-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="3d958-110">Gli elenchi esistenti non saranno interessati dalle chiamate successive di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="3d958-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="3d958-111">Se il processo è stato terminato, `EnumAppDomains` avrà esito negativo con un valore HRESULT di CORDBG_E_PROCESS_TERMINATED.</span><span class="sxs-lookup"><span data-stu-id="3d958-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d958-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3d958-112">Requirements</span></span>  
 <span data-ttu-id="3d958-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d958-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d958-114">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="3d958-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3d958-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d958-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d958-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d958-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d958-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d958-117">See also</span></span>

- [<span data-ttu-id="3d958-118">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="3d958-118">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)

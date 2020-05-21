---
title: Metodo ICorConfiguration::SetGCHostControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: e648b36a2b276d9335eefaf71b57ad76f9fe0def
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762383"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="166d5-102">Metodo ICorConfiguration::SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="166d5-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="166d5-103">Imposta l'interfaccia di callback che deve essere utilizzata dal Garbage Collector per richiedere all'host di modificare i limiti della memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="166d5-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="166d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="166d5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="166d5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="166d5-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="166d5-106">in Puntatore a un oggetto [IGCHostControl](igchostcontrol-interface.md) che consente all'Garbage Collector di richiedere all'host di modificare i limiti della memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="166d5-106">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="166d5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="166d5-107">Requirements</span></span>  
 <span data-ttu-id="166d5-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="166d5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="166d5-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="166d5-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="166d5-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="166d5-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="166d5-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="166d5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="166d5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="166d5-112">See also</span></span>

- [<span data-ttu-id="166d5-113">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="166d5-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)

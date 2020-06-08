---
title: Interfaccia IActionOnCLREvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: f577e9252d97ec188ff1076fd8340336b16c8257
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504329"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="cdd2a-102">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="cdd2a-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="cdd2a-103">Fornisce il metodo [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) , che esegue i callback sugli eventi che sono stati registrati tramite una chiamata al metodo [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cdd2a-103">Provides the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cdd2a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cdd2a-104">Methods</span></span>  
  
|<span data-ttu-id="cdd2a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cdd2a-105">Method</span></span>|<span data-ttu-id="cdd2a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cdd2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cdd2a-107">Metodo OnEvent</span><span class="sxs-lookup"><span data-stu-id="cdd2a-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="cdd2a-108">Esegue un callback per un evento registrato.</span><span class="sxs-lookup"><span data-stu-id="cdd2a-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cdd2a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cdd2a-109">Requirements</span></span>  
 <span data-ttu-id="cdd2a-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdd2a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdd2a-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cdd2a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cdd2a-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cdd2a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdd2a-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdd2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd2a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdd2a-114">See also</span></span>

- [<span data-ttu-id="cdd2a-115">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="cdd2a-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="cdd2a-116">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="cdd2a-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="cdd2a-117">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="cdd2a-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="cdd2a-118">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="cdd2a-118">Hosting Interfaces</span></span>](hosting-interfaces.md)

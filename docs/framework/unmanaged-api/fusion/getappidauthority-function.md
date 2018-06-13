---
title: Funzione GetAppIdAuthority
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 419884cfd4cbcbcdaa999c221b56ee9873a90241
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429108"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="f587d-102">Funzione GetAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="f587d-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="f587d-103">Ottiene un puntatore a un [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) che gestisce le chiavi per le identità delle applicazioni e i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="f587d-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f587d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f587d-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f587d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f587d-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="f587d-106">[out] L'oggetto restituito `IAppIdAuthority` puntatore.</span><span class="sxs-lookup"><span data-stu-id="f587d-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f587d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f587d-107">Requirements</span></span>  
 <span data-ttu-id="f587d-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f587d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f587d-109">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="f587d-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f587d-110">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f587d-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f587d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f587d-111">See Also</span></span>  
 [<span data-ttu-id="f587d-112">Interfaccia IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="f587d-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 [<span data-ttu-id="f587d-113">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="f587d-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

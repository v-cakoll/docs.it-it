---
title: Funzione GetIdentityAuthority
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eae17c2dbccb4296d7542c60a30b341f1ad67f88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429566"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="4b3a1-102">Funzione GetIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="4b3a1-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="4b3a1-103">Ottiene un puntatore a un [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) che gestisce le chiavi per gli oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b3a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b3a1-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b3a1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b3a1-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="4b3a1-106">[out] L'oggetto restituito `IIdentityAuthority` puntatore.</span><span class="sxs-lookup"><span data-stu-id="4b3a1-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b3a1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b3a1-107">Requirements</span></span>  
 <span data-ttu-id="4b3a1-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b3a1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b3a1-109">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="4b3a1-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="4b3a1-110">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b3a1-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3a1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b3a1-111">See Also</span></span>  
 [<span data-ttu-id="4b3a1-112">Interfaccia IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="4b3a1-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 [<span data-ttu-id="4b3a1-113">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="4b3a1-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

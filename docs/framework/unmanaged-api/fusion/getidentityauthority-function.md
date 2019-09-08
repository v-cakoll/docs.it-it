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
ms.openlocfilehash: f29246bdb929c8eaf1ebce726164d5cd2269b9f1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796864"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="deb17-102">Funzione GetIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="deb17-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="deb17-103">Ottiene un puntatore a un'istanza di [IIdentityAuthority](iidentityauthority-interface.md) che gestisce le chiavi per gli oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="deb17-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb17-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="deb17-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="deb17-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="deb17-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="deb17-106">out Puntatore restituito `IIdentityAuthority` .</span><span class="sxs-lookup"><span data-stu-id="deb17-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deb17-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="deb17-107">Requirements</span></span>  
 <span data-ttu-id="deb17-108">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deb17-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb17-109">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="deb17-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="deb17-110">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deb17-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb17-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="deb17-111">See also</span></span>

- [<span data-ttu-id="deb17-112">Interfaccia IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="deb17-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="deb17-113">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="deb17-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

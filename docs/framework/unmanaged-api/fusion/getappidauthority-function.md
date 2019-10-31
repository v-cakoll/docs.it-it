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
ms.openlocfilehash: 22a6af61251942f068676daaee2bdfa868e32a97
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134548"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="116eb-102">Funzione GetAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="116eb-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="116eb-103">Ottiene un puntatore a un'istanza di [IAppIdAuthority](iappidauthority-interface.md) che gestisce le chiavi per le identità dell'applicazione e i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="116eb-103">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="116eb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="116eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="116eb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="116eb-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="116eb-106">out Puntatore `IAppIdAuthority` restituito.</span><span class="sxs-lookup"><span data-stu-id="116eb-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="116eb-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="116eb-107">Requirements</span></span>  
 <span data-ttu-id="116eb-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="116eb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="116eb-109">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="116eb-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="116eb-110">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="116eb-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="116eb-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="116eb-111">See also</span></span>

- [<span data-ttu-id="116eb-112">Interfaccia IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="116eb-112">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="116eb-113">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="116eb-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

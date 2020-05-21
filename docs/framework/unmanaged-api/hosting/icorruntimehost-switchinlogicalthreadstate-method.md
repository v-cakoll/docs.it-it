---
title: Metodo ICorRuntimeHost::SwitchInLogicalThreadState
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: d830635b911fa5d80382e432f283c455c41af7a8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762682"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="81f34-102">Metodo ICorRuntimeHost::SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="81f34-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="81f34-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="81f34-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81f34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81f34-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81f34-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="81f34-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="81f34-106">in Cookie che indica il fiber da usare.</span><span class="sxs-lookup"><span data-stu-id="81f34-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81f34-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81f34-107">Requirements</span></span>  
 <span data-ttu-id="81f34-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81f34-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81f34-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="81f34-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81f34-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81f34-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81f34-111">**Versione .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="81f34-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f34-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81f34-112">See also</span></span>

- [<span data-ttu-id="81f34-113">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="81f34-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)

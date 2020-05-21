---
title: Metodo ICorRuntimeHost::SwitchOutLogicalThreadState
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
ms.openlocfilehash: f32381dc40a744157e46780e59b83efd63e58dcb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762643"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="f4d14-102">Metodo ICorRuntimeHost::SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="f4d14-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="f4d14-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="f4d14-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4d14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4d14-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4d14-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4d14-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="f4d14-106">out Cookie che indica che la fibra è stata disattivata.</span><span class="sxs-lookup"><span data-stu-id="f4d14-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4d14-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4d14-107">Requirements</span></span>  
 <span data-ttu-id="f4d14-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4d14-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4d14-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f4d14-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4d14-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f4d14-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4d14-111">**Versione .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="f4d14-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d14-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4d14-112">See also</span></span>

- [<span data-ttu-id="f4d14-113">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f4d14-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)

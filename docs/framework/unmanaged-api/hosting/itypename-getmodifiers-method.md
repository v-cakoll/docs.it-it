---
title: Metodo ITypeName::GetModifiers
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
ms.openlocfilehash: c96764749a766f3b4bbff4cf6512677a47197f4c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095837"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="c6b97-102">Metodo ITypeName::GetModifiers</span><span class="sxs-lookup"><span data-stu-id="c6b97-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="c6b97-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="c6b97-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6b97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6b97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c6b97-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6b97-105">Requirements</span></span>  
 <span data-ttu-id="c6b97-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6b97-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6b97-107">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c6b97-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6b97-108">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c6b97-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6b97-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6b97-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6b97-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6b97-110">See also</span></span>

- [<span data-ttu-id="c6b97-111">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c6b97-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

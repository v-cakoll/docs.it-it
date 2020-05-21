---
title: Metodo ICorThreadpool::CorDeleteTimer
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorDeleteTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeleteTimer
helpviewer_keywords:
- ICorThreadpool::CorDeleteTimer method [.NET Framework hosting]
- CorDeleteTimer method [.NET Framework hosting]
ms.assetid: 74847c35-7ca1-466a-b750-b25e7b03d100
topic_type:
- apiref
ms.openlocfilehash: c4ea53502c58106190a8ca5d194039dc3600af75
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760433"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="62607-102">Metodo ICorThreadpool::CorDeleteTimer</span><span class="sxs-lookup"><span data-stu-id="62607-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="62607-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="62607-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62607-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62607-104">Syntax</span></span>  
  
```cpp  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="62607-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62607-105">Requirements</span></span>  
 <span data-ttu-id="62607-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62607-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62607-107">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="62607-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62607-108">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62607-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62607-109">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62607-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62607-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62607-110">See also</span></span>

- [<span data-ttu-id="62607-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="62607-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)

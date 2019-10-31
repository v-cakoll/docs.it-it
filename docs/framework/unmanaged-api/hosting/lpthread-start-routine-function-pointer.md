---
title: Puntatore alla funzione LPTHREAD_START_ROUTINE
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
ms.openlocfilehash: c6e0c02af93b9df726202f397bbb2afc306f3b3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090872"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="91ab2-102">Puntatore alla funzione LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="91ab2-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="91ab2-103">Punta a una funzione che notifica all'host che un thread è stato avviato per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91ab2-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="91ab2-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="91ab2-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91ab2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91ab2-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91ab2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="91ab2-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="91ab2-107">in Puntatore al codice che ha avviato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91ab2-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91ab2-108">Note</span><span class="sxs-lookup"><span data-stu-id="91ab2-108">Remarks</span></span>  
 <span data-ttu-id="91ab2-109">Funzione a cui `LPTHREAD_START_ROUTINE` punti è una funzione di callback e deve essere implementata dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="91ab2-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91ab2-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91ab2-110">Requirements</span></span>  
 <span data-ttu-id="91ab2-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91ab2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91ab2-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="91ab2-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91ab2-113">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="91ab2-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="91ab2-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91ab2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ab2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91ab2-115">See also</span></span>

- [<span data-ttu-id="91ab2-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="91ab2-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

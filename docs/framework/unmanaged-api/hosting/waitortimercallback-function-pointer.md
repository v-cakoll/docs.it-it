---
title: Puntatore alla funzione WAITORTIMERCALLBACK
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
ms.openlocfilehash: ee5dd611888ec52e360ef45fab4c01e9c5b2d6bb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009450"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="5cbc9-102">Puntatore alla funzione WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="5cbc9-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="5cbc9-103">Punta a una funzione che notifica all'host che un handle di attesa ( <xref:System.Threading.WaitHandle> ) è stato segnalato o si è verificato un timeout.</span><span class="sxs-lookup"><span data-stu-id="5cbc9-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="5cbc9-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5cbc9-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cbc9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cbc9-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cbc9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5cbc9-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="5cbc9-107">in Puntatore a un oggetto che contiene le informazioni definite dall'host.</span><span class="sxs-lookup"><span data-stu-id="5cbc9-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="5cbc9-108">[in] `true` Se l'handle di attesa è scaduto o è `false` stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="5cbc9-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cbc9-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="5cbc9-109">Remarks</span></span>  
 <span data-ttu-id="5cbc9-110">Funzione a cui `WAITORTIMERCALLBACK` punta è una funzione di callback e deve essere implementata dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="5cbc9-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cbc9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cbc9-111">Requirements</span></span>  
 <span data-ttu-id="5cbc9-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cbc9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cbc9-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5cbc9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5cbc9-114">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="5cbc9-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="5cbc9-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cbc9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbc9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cbc9-116">See also</span></span>

- [<span data-ttu-id="5cbc9-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="5cbc9-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

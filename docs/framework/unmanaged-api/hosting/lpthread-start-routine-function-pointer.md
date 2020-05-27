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
ms.openlocfilehash: 84cdb42b11ad70f54f21ae36ca2734dc794d06d7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008469"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="4c1d7-102">Puntatore alla funzione LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="4c1d7-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="4c1d7-103">Punta a una funzione che notifica all'host che un thread è stato avviato per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4c1d7-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="4c1d7-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4c1d7-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c1d7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c1d7-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c1d7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4c1d7-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="4c1d7-107">in Puntatore al codice che ha avviato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4c1d7-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c1d7-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="4c1d7-108">Remarks</span></span>  
 <span data-ttu-id="4c1d7-109">Funzione a cui `LPTHREAD_START_ROUTINE` punta è una funzione di callback e deve essere implementata dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="4c1d7-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c1d7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c1d7-110">Requirements</span></span>  
 <span data-ttu-id="4c1d7-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c1d7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c1d7-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4c1d7-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c1d7-113">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="4c1d7-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="4c1d7-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c1d7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c1d7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c1d7-115">See also</span></span>

- [<span data-ttu-id="4c1d7-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="4c1d7-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

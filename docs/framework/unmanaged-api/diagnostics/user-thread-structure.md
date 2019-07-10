---
title: Struttura USER_THREAD
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0191f1fa17d436944fcb590d88dd4004adfa1aba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744292"
---
# <a name="userthread-structure"></a><span data-ttu-id="cdd1d-102">Struttura USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="cdd1d-102">USER_THREAD Structure</span></span>
<span data-ttu-id="cdd1d-103">Vengono fornite informazioni a un debugger su un thread.</span><span class="sxs-lookup"><span data-stu-id="cdd1d-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="cdd1d-104">Per altre informazioni, vedere la [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="cdd1d-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdd1d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cdd1d-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="cdd1d-106">Membri</span><span class="sxs-lookup"><span data-stu-id="cdd1d-106">Members</span></span>  
  
|<span data-ttu-id="cdd1d-107">Member</span><span class="sxs-lookup"><span data-stu-id="cdd1d-107">Member</span></span>|<span data-ttu-id="cdd1d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cdd1d-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="cdd1d-109">Indirizzo del buffer dei thread.</span><span class="sxs-lookup"><span data-stu-id="cdd1d-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="cdd1d-110">Lunghezza del buffer di thread, in byte.</span><span class="sxs-lookup"><span data-stu-id="cdd1d-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="cdd1d-111">ID del thread.</span><span class="sxs-lookup"><span data-stu-id="cdd1d-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cdd1d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cdd1d-112">Requirements</span></span>  
 <span data-ttu-id="cdd1d-113">**Intestazione:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="cdd1d-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd1d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdd1d-114">See also</span></span>

- [<span data-ttu-id="cdd1d-115">Metodo SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="cdd1d-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="cdd1d-116">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="cdd1d-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)

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
ms.openlocfilehash: 5144feab742bc5dac36563d701d81a699d0bb2f3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609443"
---
# <a name="user_thread-structure"></a><span data-ttu-id="9d354-102">Struttura USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="9d354-102">USER_THREAD Structure</span></span>
<span data-ttu-id="9d354-103">Fornisce informazioni a un debugger relativo a un thread.</span><span class="sxs-lookup"><span data-stu-id="9d354-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="9d354-104">Per ulteriori informazioni, vedere il metodo [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9d354-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d354-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d354-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="9d354-106">Membri</span><span class="sxs-lookup"><span data-stu-id="9d354-106">Members</span></span>  
  
|<span data-ttu-id="9d354-107">Membro</span><span class="sxs-lookup"><span data-stu-id="9d354-107">Member</span></span>|<span data-ttu-id="9d354-108">Description</span><span class="sxs-lookup"><span data-stu-id="9d354-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="9d354-109">Indirizzo del buffer del thread.</span><span class="sxs-lookup"><span data-stu-id="9d354-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="9d354-110">Lunghezza del buffer del thread, in byte.</span><span class="sxs-lookup"><span data-stu-id="9d354-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="9d354-111">ID thread.</span><span class="sxs-lookup"><span data-stu-id="9d354-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d354-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d354-112">Requirements</span></span>  
 <span data-ttu-id="9d354-113">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="9d354-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d354-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d354-114">See also</span></span>

- [<span data-ttu-id="9d354-115">Metodo SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="9d354-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="9d354-116">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="9d354-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)

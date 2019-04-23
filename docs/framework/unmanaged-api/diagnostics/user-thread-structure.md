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
ms.openlocfilehash: 11551221732e454e48111d48d60ca9b72f7f9b66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127165"
---
# <a name="userthread-structure"></a><span data-ttu-id="ce0a7-102">Struttura USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="ce0a7-102">USER_THREAD Structure</span></span>
<span data-ttu-id="ce0a7-103">Vengono fornite informazioni a un debugger su un thread.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="ce0a7-104">Per altre informazioni, vedere la [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ce0a7-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce0a7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce0a7-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="ce0a7-106">Membri</span><span class="sxs-lookup"><span data-stu-id="ce0a7-106">Members</span></span>  
  
|<span data-ttu-id="ce0a7-107">Member</span><span class="sxs-lookup"><span data-stu-id="ce0a7-107">Member</span></span>|<span data-ttu-id="ce0a7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce0a7-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="ce0a7-109">Indirizzo del buffer dei thread.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="ce0a7-110">Lunghezza del buffer di thread, in byte.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="ce0a7-111">ID del thread.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce0a7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce0a7-112">Requirements</span></span>  
 <span data-ttu-id="ce0a7-113">**Intestazione:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="ce0a7-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce0a7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce0a7-114">See also</span></span>

- [<span data-ttu-id="ce0a7-115">Metodo SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="ce0a7-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="ce0a7-116">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="ce0a7-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)

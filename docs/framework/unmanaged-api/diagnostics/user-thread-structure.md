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
ms.openlocfilehash: 93e96d6f8570e6aef7bfc18ef2859dc1e86ec8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429031"
---
# <a name="userthread-structure"></a><span data-ttu-id="5f0d2-102">Struttura USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="5f0d2-102">USER_THREAD Structure</span></span>
<span data-ttu-id="5f0d2-103">Vengono fornite informazioni a un debugger su un thread.</span><span class="sxs-lookup"><span data-stu-id="5f0d2-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="5f0d2-104">Per ulteriori informazioni, vedere il [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="5f0d2-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f0d2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f0d2-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="5f0d2-106">Membri</span><span class="sxs-lookup"><span data-stu-id="5f0d2-106">Members</span></span>  
  
|<span data-ttu-id="5f0d2-107">Membro</span><span class="sxs-lookup"><span data-stu-id="5f0d2-107">Member</span></span>|<span data-ttu-id="5f0d2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f0d2-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="5f0d2-109">Indirizzo del buffer dei thread.</span><span class="sxs-lookup"><span data-stu-id="5f0d2-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="5f0d2-110">Lunghezza del buffer dei thread, in byte.</span><span class="sxs-lookup"><span data-stu-id="5f0d2-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="5f0d2-111">ID del thread.</span><span class="sxs-lookup"><span data-stu-id="5f0d2-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f0d2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f0d2-112">Requirements</span></span>  
 <span data-ttu-id="5f0d2-113">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="5f0d2-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f0d2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f0d2-114">See Also</span></span>  
 [<span data-ttu-id="5f0d2-115">Metodo SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="5f0d2-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)  
 [<span data-ttu-id="5f0d2-116">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="5f0d2-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)

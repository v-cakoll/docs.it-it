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
ms.openlocfilehash: 51db7a2b6464b562e09ce061991898a8d604ead1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437976"
---
# <a name="user_thread-structure"></a><span data-ttu-id="669e1-102">Struttura USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="669e1-102">USER_THREAD Structure</span></span>
<span data-ttu-id="669e1-103">Fornisce informazioni a un debugger relativo a un thread.</span><span class="sxs-lookup"><span data-stu-id="669e1-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="669e1-104">Per ulteriori informazioni, vedere il metodo [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="669e1-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="669e1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="669e1-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="669e1-106">Members</span><span class="sxs-lookup"><span data-stu-id="669e1-106">Members</span></span>  
  
|<span data-ttu-id="669e1-107">Membro</span><span class="sxs-lookup"><span data-stu-id="669e1-107">Member</span></span>|<span data-ttu-id="669e1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="669e1-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="669e1-109">Indirizzo del buffer del thread.</span><span class="sxs-lookup"><span data-stu-id="669e1-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="669e1-110">Lunghezza del buffer del thread, in byte.</span><span class="sxs-lookup"><span data-stu-id="669e1-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="669e1-111">ID thread.</span><span class="sxs-lookup"><span data-stu-id="669e1-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="669e1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="669e1-112">Requirements</span></span>  
 <span data-ttu-id="669e1-113">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="669e1-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="669e1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="669e1-114">See also</span></span>

- [<span data-ttu-id="669e1-115">Metodo SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="669e1-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="669e1-116">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="669e1-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)

---
title: Struttura CoreClrDebugProcInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: e12882e53d1aa2120ab5c4b6793d7f2e34be76eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132156"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="14249-102">Struttura CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="14249-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="14249-103">Rappresenta un processo in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="14249-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14249-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14249-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="14249-105">Members</span><span class="sxs-lookup"><span data-stu-id="14249-105">Members</span></span>  
  
|<span data-ttu-id="14249-106">Member</span><span class="sxs-lookup"><span data-stu-id="14249-106">Member</span></span>|<span data-ttu-id="14249-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14249-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="14249-108">Identificatore di processo assegnato dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="14249-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="14249-109">Identificatore di processo assegnato dal proxy di debug remoto in esecuzione sul computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="14249-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="14249-110">Questo identificatore esegue il riciclo meno frequentemente rispetto all'identificatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="14249-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="14249-111">Riga di comando del processo.</span><span class="sxs-lookup"><span data-stu-id="14249-111">Command-line of the process.</span></span> <span data-ttu-id="14249-112">Questo membro può essere troncato.</span><span class="sxs-lookup"><span data-stu-id="14249-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14249-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14249-113">Requirements</span></span>  
 <span data-ttu-id="14249-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14249-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14249-115">**Intestazione:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="14249-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="14249-116">**Libreria:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="14249-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="14249-117">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="14249-117">**.NET Framework Versions:** 3.5 SP1</span></span>

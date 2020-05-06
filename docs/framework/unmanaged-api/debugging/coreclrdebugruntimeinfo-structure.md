---
title: Struttura CoreClrDebugRuntimeInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
ms.openlocfilehash: 2c41e7db32ee8557a6c03217b95fd5b040655c70
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860937"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="e6497-102">Struttura CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="e6497-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="e6497-103">Rappresenta un'istanza di Common Language Runtime (CLR) che viene caricata in un processo in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="e6497-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6497-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6497-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="e6497-105">Members</span><span class="sxs-lookup"><span data-stu-id="e6497-105">Members</span></span>  
  
|<span data-ttu-id="e6497-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e6497-106">Member</span></span>|<span data-ttu-id="e6497-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6497-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="e6497-108">Identificatore di runtime assegnato dal proxy di debug remoto in esecuzione sul computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e6497-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6497-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6497-109">Requirements</span></span>  
 <span data-ttu-id="e6497-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6497-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6497-111">**Intestazione:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="e6497-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="e6497-112">**Libreria:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="e6497-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="e6497-113">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="e6497-113">**.NET Framework Versions:** 3.5 SP1</span></span>

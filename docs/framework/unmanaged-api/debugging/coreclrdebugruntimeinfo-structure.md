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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88fcc5959054f1cdf7c9543674584a4bde26d896
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402070"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="79b0c-102">Struttura CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="79b0c-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="79b0c-103">Rappresenta un'istanza di Common Language Runtime (CLR) che viene caricata in un processo in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="79b0c-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79b0c-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="79b0c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="79b0c-105">Members</span></span>  
  
|<span data-ttu-id="79b0c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="79b0c-106">Member</span></span>|<span data-ttu-id="79b0c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79b0c-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="79b0c-108">Identificatore di runtime assegnato dal proxy di debug remoto in esecuzione sul computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="79b0c-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79b0c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79b0c-109">Requirements</span></span>  
 <span data-ttu-id="79b0c-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79b0c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79b0c-111">**Intestazione:** coreclrremotedebugginginterfaces. H</span><span class="sxs-lookup"><span data-stu-id="79b0c-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="79b0c-112">**Libreria:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="79b0c-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="79b0c-113">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="79b0c-113">**.NET Framework Versions:** 3.5 SP1</span></span>

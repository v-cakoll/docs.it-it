---
title: Struttura CoreClrDebugProcInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugProcInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 53616fb8e947d2a301dcfcb4e3870a9a9dc36ec1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="699dd-102">Struttura CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="699dd-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="699dd-103">Rappresenta un processo in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="699dd-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="699dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="699dd-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="699dd-105">Membri</span><span class="sxs-lookup"><span data-stu-id="699dd-105">Members</span></span>  
  
|<span data-ttu-id="699dd-106">Membro</span><span class="sxs-lookup"><span data-stu-id="699dd-106">Member</span></span>|<span data-ttu-id="699dd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="699dd-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="699dd-108">Identificatore di processo assegnato dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="699dd-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="699dd-109">Identificatore di processo assegnato dal proxy di debug remoto in esecuzione sul computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="699dd-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="699dd-110">Questo identificatore esegue il riciclo meno frequentemente rispetto all'identificatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="699dd-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="699dd-111">Riga di comando del processo.</span><span class="sxs-lookup"><span data-stu-id="699dd-111">Command-line of the process.</span></span> <span data-ttu-id="699dd-112">Questo membro può essere troncato.</span><span class="sxs-lookup"><span data-stu-id="699dd-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="699dd-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="699dd-113">Requirements</span></span>  
 <span data-ttu-id="699dd-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="699dd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="699dd-115">**Intestazione:** coreclrremotedebugginginterfaces. H</span><span class="sxs-lookup"><span data-stu-id="699dd-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="699dd-116">**Libreria:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="699dd-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="699dd-117">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="699dd-117">**.NET Framework Versions:** 3.5 SP1</span></span>

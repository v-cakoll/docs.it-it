---
title: Enumerazione ESymbolReadingPolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fdb18a343f91e85619f6d62e466fdd558044727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="95920-102">Enumerazione ESymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="95920-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="95920-103">Contiene valori che impostano i criteri per la lettura dei file di programma (PDB) di database.</span><span class="sxs-lookup"><span data-stu-id="95920-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95920-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95920-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="95920-105">Membri</span><span class="sxs-lookup"><span data-stu-id="95920-105">Members</span></span>  
  
|<span data-ttu-id="95920-106">Membro</span><span class="sxs-lookup"><span data-stu-id="95920-106">Member</span></span>|<span data-ttu-id="95920-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95920-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="95920-108">Specifica che il debugger deve sempre leggere i file PDB.</span><span class="sxs-lookup"><span data-stu-id="95920-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="95920-109">Specifica che il debugger deve leggere solo i file PDB sono associati gli assembly con attendibilità.</span><span class="sxs-lookup"><span data-stu-id="95920-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="95920-110">Specifica che il debugger non deve leggere i file PDB.</span><span class="sxs-lookup"><span data-stu-id="95920-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95920-111">Note</span><span class="sxs-lookup"><span data-stu-id="95920-111">Remarks</span></span>  
 <span data-ttu-id="95920-112">Il `ESymbolReadingPolicy` enumerazione viene utilizzata con la [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="95920-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95920-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95920-113">Requirements</span></span>  
 <span data-ttu-id="95920-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95920-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95920-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="95920-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95920-116">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95920-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95920-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95920-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95920-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95920-118">See Also</span></span>  
 [<span data-ttu-id="95920-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="95920-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

---
title: Enumerazione ESymbolReadingPolicy
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28f6bdbc3e382f82b7fdd632b9fc8c4d422629c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429735"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="71bb8-102">Enumerazione ESymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="71bb8-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="71bb8-103">Contiene valori che impostano i criteri per la lettura dei file di programma (PDB) di database.</span><span class="sxs-lookup"><span data-stu-id="71bb8-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71bb8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71bb8-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="71bb8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="71bb8-105">Members</span></span>  
  
|<span data-ttu-id="71bb8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="71bb8-106">Member</span></span>|<span data-ttu-id="71bb8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71bb8-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="71bb8-108">Specifica che il debugger deve sempre leggere i file PDB.</span><span class="sxs-lookup"><span data-stu-id="71bb8-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="71bb8-109">Specifica che il debugger deve leggere solo i file PDB sono associati gli assembly con attendibilità.</span><span class="sxs-lookup"><span data-stu-id="71bb8-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="71bb8-110">Specifica che il debugger non deve leggere i file PDB.</span><span class="sxs-lookup"><span data-stu-id="71bb8-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71bb8-111">Note</span><span class="sxs-lookup"><span data-stu-id="71bb8-111">Remarks</span></span>  
 <span data-ttu-id="71bb8-112">Il `ESymbolReadingPolicy` enumerazione viene utilizzata con la [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="71bb8-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71bb8-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71bb8-113">Requirements</span></span>  
 <span data-ttu-id="71bb8-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71bb8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71bb8-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="71bb8-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71bb8-116">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="71bb8-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71bb8-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71bb8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71bb8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71bb8-118">See Also</span></span>  
 [<span data-ttu-id="71bb8-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="71bb8-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

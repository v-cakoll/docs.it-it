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
ms.openlocfilehash: 9ba29952fe4a6edfc6e9e80ec02f82de65ef0064
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208423"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="a1894-102">Enumerazione ESymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="a1894-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="a1894-103">Contiene valori che impostano i criteri per la lettura dei file di programma (PDB) del database.</span><span class="sxs-lookup"><span data-stu-id="a1894-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1894-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1894-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="a1894-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a1894-105">Members</span></span>  
  
|<span data-ttu-id="a1894-106">Member</span><span class="sxs-lookup"><span data-stu-id="a1894-106">Member</span></span>|<span data-ttu-id="a1894-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1894-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="a1894-108">Specifica che il debugger deve sempre leggere i file PDB.</span><span class="sxs-lookup"><span data-stu-id="a1894-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="a1894-109">Specifica che il debugger deve leggere solo i file PDB associati ad assembly completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="a1894-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="a1894-110">Specifica che il debugger mai deve leggere i file PDB.</span><span class="sxs-lookup"><span data-stu-id="a1894-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1894-111">Note</span><span class="sxs-lookup"><span data-stu-id="a1894-111">Remarks</span></span>  
 <span data-ttu-id="a1894-112">Il `ESymbolReadingPolicy` enumerazione viene utilizzata con il [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="a1894-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1894-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1894-113">Requirements</span></span>  
 <span data-ttu-id="a1894-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1894-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1894-115">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a1894-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1894-116">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1894-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1894-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1894-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1894-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1894-118">See also</span></span>

- [<span data-ttu-id="a1894-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="a1894-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

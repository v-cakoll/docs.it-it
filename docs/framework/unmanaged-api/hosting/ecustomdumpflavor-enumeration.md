---
title: Enumerazione ECustomDumpFlavor
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1e69d9cbf39049e82803d2f7bc795cc9fd0b368
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154440"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="b6a55-102">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="b6a55-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="b6a55-103">Contiene valori che indicano gli elementi da includere in un subset di un heap personalizzato di dump quando si segnalano errori.</span><span class="sxs-lookup"><span data-stu-id="b6a55-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6a55-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6a55-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="b6a55-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b6a55-105">Members</span></span>  
  
|<span data-ttu-id="b6a55-106">Member</span><span class="sxs-lookup"><span data-stu-id="b6a55-106">Member</span></span>|<span data-ttu-id="b6a55-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6a55-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="b6a55-108">Specifica che il dump dell'heap personalizzato deve avviare come un minidump e include dati extra specificati da qualsiasi [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) istanze passato al metodo di stesso.</span><span class="sxs-lookup"><span data-stu-id="b6a55-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="b6a55-109">Specifica che il dump dell'heap personalizzato deve raccogliere tutti i dati di stato di runtime che non è stati allocati in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="b6a55-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6a55-110">Note</span><span class="sxs-lookup"><span data-stu-id="b6a55-110">Remarks</span></span>  
 <span data-ttu-id="b6a55-111">Un parametro di tipo `ECustomDumpFlavor` viene passato per il [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b6a55-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6a55-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6a55-112">Requirements</span></span>  
 <span data-ttu-id="b6a55-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6a55-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6a55-114">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b6a55-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6a55-115">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6a55-115">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b6a55-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b6a55-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b6a55-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6a55-117">See also</span></span>

- [<span data-ttu-id="b6a55-118">Enumerazione ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="b6a55-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="b6a55-119">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="b6a55-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="b6a55-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="b6a55-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

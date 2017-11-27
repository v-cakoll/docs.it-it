---
title: Enumerazione ECustomDumpFlavor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ECustomDumpFlavor
api_location: mscoree.dll
api_type: COM
f1_keywords: ECustomDumpFlavor
helpviewer_keywords: ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a7317a3a12acef2a16deebab9a1e1b10205ebf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="e73e0-102">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="e73e0-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="e73e0-103">Contiene valori che indicano gli elementi da includere in un sottoinsieme di un heap personalizzato dump per la segnalazione di errori.</span><span class="sxs-lookup"><span data-stu-id="e73e0-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e73e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e73e0-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="e73e0-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e73e0-105">Members</span></span>  
  
|<span data-ttu-id="e73e0-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e73e0-106">Member</span></span>|<span data-ttu-id="e73e0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e73e0-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="e73e0-108">Specifica che il dump dell'heap personalizzato deve avviare come un minidump e includere dati aggiuntivi specificati da qualsiasi [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) istanze passato al metodo stesso.</span><span class="sxs-lookup"><span data-stu-id="e73e0-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="e73e0-109">Specifica che il dump dell'heap personalizzato deve raccogliere tutti i dati di stato di runtime che non è stati allocati in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="e73e0-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e73e0-110">Note</span><span class="sxs-lookup"><span data-stu-id="e73e0-110">Remarks</span></span>  
 <span data-ttu-id="e73e0-111">Un parametro di tipo `ECustomDumpFlavor` viene passato per il [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="e73e0-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e73e0-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e73e0-112">Requirements</span></span>  
 <span data-ttu-id="e73e0-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e73e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e73e0-114">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e73e0-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e73e0-115">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e73e0-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e73e0-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e73e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e73e0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e73e0-117">See Also</span></span>  
 [<span data-ttu-id="e73e0-118">ECustomDumpItemKind (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="e73e0-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="e73e0-119">ICLRErrorReportingManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e73e0-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="e73e0-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="e73e0-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

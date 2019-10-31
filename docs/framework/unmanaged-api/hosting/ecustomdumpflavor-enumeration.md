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
ms.openlocfilehash: 057794fe524a0ee01f6f090ca7e11a4a4b523047
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124923"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="54446-102">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="54446-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="54446-103">Contiene valori che indicano quali elementi includere in un subset personalizzato di un dump dell'heap quando si segnalano errori.</span><span class="sxs-lookup"><span data-stu-id="54446-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54446-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54446-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="54446-105">Members</span><span class="sxs-lookup"><span data-stu-id="54446-105">Members</span></span>  
  
|<span data-ttu-id="54446-106">Member</span><span class="sxs-lookup"><span data-stu-id="54446-106">Member</span></span>|<span data-ttu-id="54446-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54446-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="54446-108">Specifica che il dump dell'heap personalizzato deve iniziare come minidump e includere dati aggiuntivi specificati da qualsiasi istanza di [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) passata allo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="54446-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="54446-109">Specifica che il dump dell'heap personalizzato deve raccogliere tutti i dati sullo stato della fase di esecuzione che non sono stati allocati in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="54446-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54446-110">Note</span><span class="sxs-lookup"><span data-stu-id="54446-110">Remarks</span></span>  
 <span data-ttu-id="54446-111">Un parametro di tipo `ECustomDumpFlavor` viene passato al metodo [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="54446-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54446-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54446-112">Requirements</span></span>  
 <span data-ttu-id="54446-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54446-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54446-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="54446-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54446-115">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="54446-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54446-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54446-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54446-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54446-117">See also</span></span>

- [<span data-ttu-id="54446-118">Enumerazione ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="54446-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="54446-119">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="54446-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="54446-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="54446-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

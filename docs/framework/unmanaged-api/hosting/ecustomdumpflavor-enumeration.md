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
ms.openlocfilehash: 9b4c1187945b4c243375a3096c3a8a3b22599aef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616281"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="d012c-102">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="d012c-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="d012c-103">Contiene valori che indicano quali elementi includere in un subset personalizzato di un dump dell'heap quando si segnalano errori.</span><span class="sxs-lookup"><span data-stu-id="d012c-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d012c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d012c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="d012c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d012c-105">Members</span></span>  
  
|<span data-ttu-id="d012c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d012c-106">Member</span></span>|<span data-ttu-id="d012c-107">Description</span><span class="sxs-lookup"><span data-stu-id="d012c-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="d012c-108">Specifica che il dump dell'heap personalizzato deve iniziare come minidump e includere dati aggiuntivi specificati da qualsiasi istanza di [CustomDumpItem](customdumpitem-structure.md) passata allo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="d012c-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="d012c-109">Specifica che il dump dell'heap personalizzato deve raccogliere tutti i dati sullo stato della fase di esecuzione che non sono stati allocati in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="d012c-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d012c-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d012c-110">Remarks</span></span>  
 <span data-ttu-id="d012c-111">Un parametro di tipo `ECustomDumpFlavor` viene passato al metodo [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d012c-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d012c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d012c-112">Requirements</span></span>  
 <span data-ttu-id="d012c-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d012c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d012c-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d012c-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d012c-115">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d012c-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d012c-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d012c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d012c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d012c-117">See also</span></span>

- [<span data-ttu-id="d012c-118">Enumerazione ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="d012c-118">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="d012c-119">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="d012c-119">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="d012c-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="d012c-120">Hosting Enumerations</span></span>](hosting-enumerations.md)

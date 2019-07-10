---
title: Enumerazione EApiCategories
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41513d9b6f98743bfad95e4d9606cfb4927369e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769785"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="b7f20-102">Enumerazione EApiCategories</span><span class="sxs-lookup"><span data-stu-id="b7f20-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="b7f20-103">Vengono descritte le categorie di funzionalità che l'host può impedire l'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7f20-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7f20-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a><span data-ttu-id="b7f20-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b7f20-105">Members</span></span>  
  
|<span data-ttu-id="b7f20-106">Member</span><span class="sxs-lookup"><span data-stu-id="b7f20-106">Member</span></span>|<span data-ttu-id="b7f20-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7f20-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="b7f20-108">Specifica che tutte le classi gestite e membri che vengono analizzati da altri `EApiCategories` campi essere impedita l'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="b7f20-109">Specifica che le classi gestite e i membri che consentono la creazione, modifica e l'eliminazione di processi esterni bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="b7f20-110">Specifica che le classi gestite e i membri che consentono la creazione, modifica e la distruzione di thread esterni bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="b7f20-111">Specifica che i tipi gestiti e i membri che potrebbero causare una perdita di memoria in caso di interruzione bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="b7f20-112">Specifica che nessuna categoria di codice gestito bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="b7f20-113">Specifica che l'infrastruttura di sicurezza di common language runtime (CLR) essere bloccate vengano utilizzati da codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="b7f20-114">Specifica che le classi gestite e i membri cui capacità può influenzare il processo ospitato bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="b7f20-115">Specifica che le classi gestite e i membri cui capacità possono influire sui thread nel processo host bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="b7f20-116">Specifica che le classi gestite e i membri che espongono lo stato condiviso bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="b7f20-117">Specifica che common language runtime e classi i membri che consentono il codice utente per mantenere attivi i blocchi bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="b7f20-118">Specifica che le classi gestite e i membri che consentono o richiedono l'interazione umana bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b7f20-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7f20-119">Note</span><span class="sxs-lookup"><span data-stu-id="b7f20-119">Remarks</span></span>  
 <span data-ttu-id="b7f20-120">Il [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) metodo accetta un parametro di tipo `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="b7f20-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="b7f20-121">Il `EApiCategories` enumerazione e la `SetProtectedCategories` metodo sono direttamente correlati all'oggetto gestito <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="b7f20-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="b7f20-122">La classe gestita viene utilizzata con il <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumerazione, i cui valori corrispondono direttamente al `EApiCategories` valori, per contrassegnare tipi e membri che espongono funzionalità corrispondenti per le categorie descritte dal gestiti `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="b7f20-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7f20-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7f20-123">Requirements</span></span>  
 <span data-ttu-id="b7f20-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7f20-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7f20-125">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b7f20-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7f20-126">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7f20-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7f20-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7f20-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f20-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7f20-128">See also</span></span>

- [<span data-ttu-id="b7f20-129">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="b7f20-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="b7f20-130">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="b7f20-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

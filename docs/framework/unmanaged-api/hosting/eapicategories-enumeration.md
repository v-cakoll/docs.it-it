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
ms.openlocfilehash: d31b0190ef9a697fb27c849db080bec6c57618ae
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616385"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="3ddd6-102">Enumerazione EApiCategories</span><span class="sxs-lookup"><span data-stu-id="3ddd6-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="3ddd6-103">Vengono descritte le categorie di funzionalità che l'host può bloccare dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ddd6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ddd6-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="3ddd6-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3ddd6-105">Members</span></span>  
  
|<span data-ttu-id="3ddd6-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3ddd6-106">Member</span></span>|<span data-ttu-id="3ddd6-107">Description</span><span class="sxs-lookup"><span data-stu-id="3ddd6-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="3ddd6-108">Specifica che tutte le classi gestite e i membri che sono coperti da altri `EApiCategories` campi vengono bloccati dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="3ddd6-109">Specifica che le classi gestite e i membri che consentono la creazione, la manipolazione e la distruzione di processi esterni vengono bloccati dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="3ddd6-110">Specifica che le classi gestite e i membri che consentono la creazione, la manipolazione e la distruzione di thread esterni vengono bloccati dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="3ddd6-111">Specifica che i tipi e i membri gestiti che potrebbero causare perdite di memoria in Abort non possono essere eseguiti in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="3ddd6-112">Specifica che non è possibile bloccare l'esecuzione di nessuna categoria di codice gestito in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="3ddd6-113">Specifica che l'infrastruttura di sicurezza di Common Language Runtime (CLR) non viene utilizzata da codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="3ddd6-114">Specifica che le classi gestite e i membri le cui funzionalità possono influenzare il processo ospitato vengono bloccati dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="3ddd6-115">Specifica che le classi gestite e i membri le cui funzionalità possono influenzare i thread nel processo ospitato vengono bloccati dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="3ddd6-116">Specifica che le classi gestite e i membri che espongono lo stato condiviso vengono bloccati dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="3ddd6-117">Specifica che Common Language Runtime classi e membri che consentono al codice utente di mantenere i blocchi possono essere bloccati dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="3ddd6-118">Specifica che le classi gestite e i membri che consentono o richiedono un'interazione umana possono essere bloccati dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ddd6-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ddd6-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3ddd6-119">Remarks</span></span>  
 <span data-ttu-id="3ddd6-120">Il metodo [ICLRHostProtectionManager:: SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md) accetta un parametro di tipo `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="3ddd6-120">The [ICLRHostProtectionManager::SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="3ddd6-121">L' `EApiCategories` enumerazione e il `SetProtectedCategories` metodo sono direttamente correlati alla classe gestita <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3ddd6-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="3ddd6-122">La classe gestita viene utilizzata con l' <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumerazione, i cui valori corrispondono direttamente ai `EApiCategories` valori, per contrassegnare i tipi e i membri gestiti che espongono le funzionalità corrispondenti alle categorie descritte da `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="3ddd6-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ddd6-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ddd6-123">Requirements</span></span>  
 <span data-ttu-id="3ddd6-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ddd6-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ddd6-125">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3ddd6-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ddd6-126">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3ddd6-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ddd6-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ddd6-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ddd6-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ddd6-128">See also</span></span>

- [<span data-ttu-id="3ddd6-129">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="3ddd6-129">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="3ddd6-130">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="3ddd6-130">Hosting Enumerations</span></span>](hosting-enumerations.md)

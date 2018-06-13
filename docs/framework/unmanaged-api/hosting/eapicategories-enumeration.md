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
ms.openlocfilehash: f25348410387a7b0e03ef897e8534336baeb126a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432209"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="15573-102">Enumerazione EApiCategories</span><span class="sxs-lookup"><span data-stu-id="15573-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="15573-103">Vengono descritte le categorie di funzionalità che l'host può impedire l'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="15573-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15573-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15573-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="15573-105">Membri</span><span class="sxs-lookup"><span data-stu-id="15573-105">Members</span></span>  
  
|<span data-ttu-id="15573-106">Membro</span><span class="sxs-lookup"><span data-stu-id="15573-106">Member</span></span>|<span data-ttu-id="15573-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15573-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="15573-108">Specifica che tutte le classi gestite e membri inclusi da altri `EApiCategories` campi bloccare l'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="15573-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="15573-109">Specifica che deve essere impedita l'esecuzione in codice parzialmente attendibile di classi gestite e i membri che consentono la creazione, modifica e l'eliminazione di processi esterni.</span><span class="sxs-lookup"><span data-stu-id="15573-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="15573-110">Specifica che le classi gestite e i membri che consentono la creazione, la modifica e la distruzione di thread esterni bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="15573-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="15573-111">Specifica che deve essere impedita l'esecuzione in codice parzialmente attendibile di tipi gestiti e i membri che potrebbero causare una perdita di memoria in caso di interruzione.</span><span class="sxs-lookup"><span data-stu-id="15573-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="15573-112">Specifica che deve non essere impedita l'esecuzione in codice parzialmente attendibile categorie nessun codice gestito.</span><span class="sxs-lookup"><span data-stu-id="15573-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="15573-113">Specifica che l'infrastruttura di protezione di common language runtime (CLR) bloccato vengano utilizzati da codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="15573-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="15573-114">Specifica che le classi gestite e i membri le cui funzionalità può influenzare il processo di hosting bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="15573-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="15573-115">Specifica che le classi gestite e i membri che possono influire sulla thread nel processo host bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="15573-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="15573-116">Specifica che deve essere impedita l'esecuzione in codice parzialmente attendibile di classi gestite e i membri che espongono lo stato condiviso.</span><span class="sxs-lookup"><span data-stu-id="15573-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="15573-117">Specifica che deve essere impedita l'esecuzione in codice parzialmente attendibile di common language runtime e classi i membri che consentono di mantenere attivi i blocchi di codice utente.</span><span class="sxs-lookup"><span data-stu-id="15573-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="15573-118">Specifica che le classi gestite e i membri che consentono o richiedono l'interazione umana bloccato dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="15573-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15573-119">Note</span><span class="sxs-lookup"><span data-stu-id="15573-119">Remarks</span></span>  
 <span data-ttu-id="15573-120">Il [ICLRHostProtectionManager::](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) metodo accetta un parametro di tipo `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="15573-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="15573-121">Il `EApiCategories` enumerazione e `SetProtectedCategories` metodo sono direttamente correlati all'oggetto gestito <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="15573-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="15573-122">La classe gestita viene utilizzata con la <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumerazione, i cui valori corrispondono direttamente al `EApiCategories` valori, per contrassegnare i tipi gestiti e i membri che espongono funzionalità corrispondenti alle categorie descritte da `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="15573-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15573-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15573-123">Requirements</span></span>  
 <span data-ttu-id="15573-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15573-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15573-125">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="15573-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15573-126">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="15573-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15573-127">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15573-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15573-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15573-128">See Also</span></span>  
 [<span data-ttu-id="15573-129">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="15573-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="15573-130">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="15573-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

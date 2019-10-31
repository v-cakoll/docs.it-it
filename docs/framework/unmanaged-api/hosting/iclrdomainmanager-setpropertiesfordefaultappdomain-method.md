---
title: Metodo ICLRDomainManager::SetPropertiesForDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: 37919be2d0ebd7d243615bc5845b0781ac13e574
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129319"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="59ee2-102">Metodo ICLRDomainManager::SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="59ee2-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="59ee2-103">Imposta le proprietà che verranno utilizzate per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="59ee2-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ee2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59ee2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59ee2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="59ee2-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="59ee2-106">in Numero di voci in `pwszPropertyNames` e `pwszPropertyValues`.</span><span class="sxs-lookup"><span data-stu-id="59ee2-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="59ee2-107">in Matrice di nomi di proprietà oppure null se non sono presenti proprietà.</span><span class="sxs-lookup"><span data-stu-id="59ee2-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="59ee2-108">Attualmente, l'unico nome di proprietà riconosciuto da questo metodo è "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="59ee2-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="59ee2-109">in Matrice di valori di proprietà o null se non sono presenti proprietà.</span><span class="sxs-lookup"><span data-stu-id="59ee2-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59ee2-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="59ee2-110">Return Value</span></span>  
 <span data-ttu-id="59ee2-111">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="59ee2-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="59ee2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59ee2-112">HRESULT</span></span>|<span data-ttu-id="59ee2-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59ee2-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59ee2-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="59ee2-114">S_OK</span></span>|<span data-ttu-id="59ee2-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="59ee2-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="59ee2-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="59ee2-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="59ee2-117">`pwszPropertyNames` include un nome di proprietà non riconosciuto da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="59ee2-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59ee2-118">Note</span><span class="sxs-lookup"><span data-stu-id="59ee2-118">Remarks</span></span>  
 <span data-ttu-id="59ee2-119">Il valore della proprietà per "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" è un elenco di assembly con l'attributo condizionale <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) con il flag <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType>, che devono essere resi visibili ai chiamanti parzialmente attendibili nel dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="59ee2-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59ee2-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59ee2-120">Requirements</span></span>  
 <span data-ttu-id="59ee2-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59ee2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59ee2-122">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="59ee2-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="59ee2-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="59ee2-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59ee2-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59ee2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ee2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59ee2-125">See also</span></span>

- [<span data-ttu-id="59ee2-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="59ee2-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="59ee2-127">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="59ee2-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)

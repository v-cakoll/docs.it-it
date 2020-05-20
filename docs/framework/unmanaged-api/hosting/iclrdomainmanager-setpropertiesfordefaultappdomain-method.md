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
ms.openlocfilehash: 5e1c1b1984c63bedb3c073f45a7b9a3574afdcec
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615683"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="74caa-102">Metodo ICLRDomainManager::SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="74caa-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="74caa-103">Imposta le proprietà che verranno utilizzate per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="74caa-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74caa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74caa-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74caa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74caa-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="74caa-106">in Numero di voci in `pwszPropertyNames` e `pwszPropertyValues` .</span><span class="sxs-lookup"><span data-stu-id="74caa-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="74caa-107">in Matrice di nomi di proprietà oppure null se non sono presenti proprietà.</span><span class="sxs-lookup"><span data-stu-id="74caa-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="74caa-108">Attualmente, l'unico nome di proprietà riconosciuto da questo metodo è "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="74caa-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="74caa-109">in Matrice di valori di proprietà o null se non sono presenti proprietà.</span><span class="sxs-lookup"><span data-stu-id="74caa-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74caa-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="74caa-110">Return Value</span></span>  
 <span data-ttu-id="74caa-111">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="74caa-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="74caa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74caa-112">HRESULT</span></span>|<span data-ttu-id="74caa-113">Description</span><span class="sxs-lookup"><span data-stu-id="74caa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74caa-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="74caa-114">S_OK</span></span>|<span data-ttu-id="74caa-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="74caa-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="74caa-116">HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="74caa-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="74caa-117">`pwszPropertyNames`include un nome di proprietà non riconosciuto da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="74caa-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74caa-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="74caa-118">Remarks</span></span>  
 <span data-ttu-id="74caa-119">Il valore della proprietà per "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" è un elenco di assembly con l'attributo condizionale <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) con il <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, che devono essere resi visibili ai chiamanti parzialmente attendibili nel dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="74caa-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74caa-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74caa-120">Requirements</span></span>  
 <span data-ttu-id="74caa-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74caa-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74caa-122">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="74caa-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="74caa-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="74caa-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74caa-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74caa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74caa-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74caa-125">See also</span></span>

- [<span data-ttu-id="74caa-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="74caa-126">Hosting</span></span>](index.md)
- [<span data-ttu-id="74caa-127">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="74caa-127">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)

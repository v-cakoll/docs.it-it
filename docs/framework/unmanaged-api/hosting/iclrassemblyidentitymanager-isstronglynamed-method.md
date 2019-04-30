---
title: Metodo ICLRAssemblyIdentityManager::IsStronglyNamed
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 166583f690fc7ed80f80cf2cf5cd5b0348708cc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970157"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="0d423-102">Metodo ICLRAssemblyIdentityManager::IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="0d423-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="0d423-103">Ottiene un valore che indica se l'assembly specificato è un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="0d423-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d423-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d423-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d423-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d423-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="0d423-106">[in] I dati di identità di assembly canonico opaco dell'assembly da valutare.</span><span class="sxs-lookup"><span data-stu-id="0d423-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="0d423-107">[out] `true`, se il riferimento all'assembly il `pwzAssemblyIdentity` parametro è fortemente denominato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0d423-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d423-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0d423-108">Return Value</span></span>  
  
|<span data-ttu-id="0d423-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d423-109">HRESULT</span></span>|<span data-ttu-id="0d423-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d423-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d423-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d423-111">S_OK</span></span>|<span data-ttu-id="0d423-112">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0d423-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="0d423-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d423-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d423-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d423-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d423-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d423-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d423-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d423-116">The call timed out.</span></span>|  
|<span data-ttu-id="0d423-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d423-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d423-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="0d423-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d423-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d423-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d423-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0d423-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d423-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d423-121">E_FAIL</span></span>|<span data-ttu-id="0d423-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0d423-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d423-123">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0d423-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d423-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0d423-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d423-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d423-125">Requirements</span></span>  
 <span data-ttu-id="0d423-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d423-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d423-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d423-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d423-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0d423-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d423-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d423-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d423-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d423-130">See also</span></span>

- [<span data-ttu-id="0d423-131">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="0d423-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)

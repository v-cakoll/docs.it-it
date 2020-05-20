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
ms.openlocfilehash: d388f366671f50c3dcb3bd9d387300dd1bbb168f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615904"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="5af5c-102">Metodo ICLRAssemblyIdentityManager::IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="5af5c-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="5af5c-103">Ottiene un valore che indica se l'assembly specificato ha un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="5af5c-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af5c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5af5c-104">Syntax</span></span>  
  
```cpp  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5af5c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5af5c-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="5af5c-106">in Dati di identità dell'assembly canonico opaco dell'assembly da valutare.</span><span class="sxs-lookup"><span data-stu-id="5af5c-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="5af5c-107">[out] `true` , se l'assembly a cui fa riferimento il `pwzAssemblyIdentity` parametro ha un nome sicuro; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="5af5c-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5af5c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5af5c-108">Return Value</span></span>  
  
|<span data-ttu-id="5af5c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5af5c-109">HRESULT</span></span>|<span data-ttu-id="5af5c-110">Description</span><span class="sxs-lookup"><span data-stu-id="5af5c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5af5c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5af5c-111">S_OK</span></span>|<span data-ttu-id="5af5c-112">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5af5c-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="5af5c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5af5c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5af5c-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5af5c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5af5c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5af5c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5af5c-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5af5c-116">The call timed out.</span></span>|  
|<span data-ttu-id="5af5c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5af5c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5af5c-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="5af5c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5af5c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5af5c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5af5c-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5af5c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5af5c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5af5c-121">E_FAIL</span></span>|<span data-ttu-id="5af5c-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5af5c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5af5c-123">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5af5c-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5af5c-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5af5c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5af5c-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5af5c-125">Requirements</span></span>  
 <span data-ttu-id="5af5c-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5af5c-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5af5c-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5af5c-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5af5c-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5af5c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5af5c-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5af5c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af5c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5af5c-130">See also</span></span>

- [<span data-ttu-id="5af5c-131">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="5af5c-131">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)

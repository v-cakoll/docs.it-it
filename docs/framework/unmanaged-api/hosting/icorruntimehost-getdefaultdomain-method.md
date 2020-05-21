---
title: Metodo ICorRuntimeHost::GetDefaultDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
ms.openlocfilehash: a23083777d0cd5965511f3689578a60220008420
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762230"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="36364-102">Metodo ICorRuntimeHost::GetDefaultDomain</span><span class="sxs-lookup"><span data-stu-id="36364-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="36364-103">Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> che rappresenta il dominio predefinito per il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="36364-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36364-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36364-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36364-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="36364-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="36364-106">out Puntatore di interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> all' <xref:System.AppDomain> istanza di che rappresenta il dominio applicazione predefinito per il processo.</span><span class="sxs-lookup"><span data-stu-id="36364-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="36364-107">Questo puntatore è tipizzato `IUnknown` , quindi i chiamanti devono in genere chiamare `QueryInterface` per ottenere un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36364-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36364-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="36364-108">Return Value</span></span>  
  
|<span data-ttu-id="36364-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36364-109">HRESULT</span></span>|<span data-ttu-id="36364-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36364-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36364-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="36364-111">S_OK</span></span>|<span data-ttu-id="36364-112">L'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="36364-112">The operation was successful.</span></span>|  
|<span data-ttu-id="36364-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="36364-113">S_FALSE</span></span>|<span data-ttu-id="36364-114">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="36364-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="36364-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="36364-115">E_FAIL</span></span>|<span data-ttu-id="36364-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="36364-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="36364-117">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="36364-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="36364-118">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="36364-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="36364-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36364-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="36364-120">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="36364-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36364-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36364-121">Requirements</span></span>  
 <span data-ttu-id="36364-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36364-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36364-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="36364-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36364-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="36364-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36364-125">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="36364-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36364-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36364-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="36364-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="36364-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)

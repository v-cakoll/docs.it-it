---
title: Metodo ICorRuntimeHost::CreateDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
ms.openlocfilehash: 74f17c77e74edb1226dda2d9ebaa9486e1769ce4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762357"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="42a40-102">Metodo ICorRuntimeHost::CreateDomain</span><span class="sxs-lookup"><span data-stu-id="42a40-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="42a40-103">Crea un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="42a40-103">Creates an application domain.</span></span> <span data-ttu-id="42a40-104">Il chiamante riceve un puntatore di interfaccia di tipo <xref:System._AppDomain> a un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="42a40-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42a40-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42a40-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42a40-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="42a40-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="42a40-107">in Parametro facoltativo utilizzato per assegnare un nome descrittivo al dominio.</span><span class="sxs-lookup"><span data-stu-id="42a40-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="42a40-108">Questo nome descrittivo può essere visualizzato nelle interfacce utente, ad esempio i debugger, per identificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="42a40-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="42a40-109">in Matrice facoltativa di puntatori a `IIdentity` istanze che rappresentano l'evidenza mappata tramite i criteri di sicurezza per stabilire un set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="42a40-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="42a40-110">Un `IIdentity` oggetto può essere ottenuto chiamando il metodo [CreateEvidence](icorruntimehost-createevidence-method.md) .</span><span class="sxs-lookup"><span data-stu-id="42a40-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="42a40-111">out Puntatore a un'interfaccia di tipo <xref:System._AppDomain> a un'istanza di <xref:System.AppDomain?displayProperty=nameWithType> che può essere utilizzata per controllare ulteriormente il dominio.</span><span class="sxs-lookup"><span data-stu-id="42a40-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42a40-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="42a40-112">Return Value</span></span>  
  
|<span data-ttu-id="42a40-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42a40-113">HRESULT</span></span>|<span data-ttu-id="42a40-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42a40-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42a40-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="42a40-115">S_OK</span></span>|<span data-ttu-id="42a40-116">L'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="42a40-116">The operation was successful.</span></span>|  
|<span data-ttu-id="42a40-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="42a40-117">S_FALSE</span></span>|<span data-ttu-id="42a40-118">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="42a40-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="42a40-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42a40-119">E_FAIL</span></span>|<span data-ttu-id="42a40-120">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="42a40-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="42a40-121">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="42a40-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="42a40-122">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="42a40-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="42a40-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42a40-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42a40-124">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="42a40-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42a40-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42a40-125">Requirements</span></span>  
 <span data-ttu-id="42a40-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a40-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a40-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="42a40-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42a40-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="42a40-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42a40-129">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="42a40-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a40-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42a40-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="42a40-131">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="42a40-131">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)

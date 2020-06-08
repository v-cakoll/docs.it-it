---
title: Interfaccia IHostSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: f6e25bfe11880730f6f447ccc0406d716d185624
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501495"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="41638-102">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="41638-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="41638-103">Consente all'Common Language Runtime (CLR) di mantenere le informazioni sul contesto di sicurezza implementate dall'host.</span><span class="sxs-lookup"><span data-stu-id="41638-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41638-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="41638-104">Methods</span></span>  
  
|<span data-ttu-id="41638-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="41638-105">Method</span></span>|<span data-ttu-id="41638-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41638-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41638-107">Metodo Capture</span><span class="sxs-lookup"><span data-stu-id="41638-107">Capture Method</span></span>](ihostsecuritycontext-capture-method.md)|<span data-ttu-id="41638-108">Ottiene un clone dell' `IHostSecurityContext` istanza di restituita da una chiamata a [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="41638-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41638-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="41638-109">Remarks</span></span>  
 <span data-ttu-id="41638-110">Un host può controllare l'accesso al codice a token di thread sia dal codice CLR che dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="41638-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="41638-111">Può inoltre garantire che le informazioni complete sul contesto di sicurezza vengano passate tra le operazioni asincrone o i punti di codice con accesso limitato al codice.</span><span class="sxs-lookup"><span data-stu-id="41638-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="41638-112">`IHostSecurityContext`Incapsula le informazioni sul contesto di sicurezza, che è opaco per il Runtime.</span><span class="sxs-lookup"><span data-stu-id="41638-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="41638-113">Il runtime acquisisce queste informazioni usando `Capture` e le sposta tra la distribuzione degli elementi di lavoro del pool di thread, l'esecuzione del finalizzatore e i costruttori di moduli e classi.</span><span class="sxs-lookup"><span data-stu-id="41638-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41638-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41638-114">Requirements</span></span>  
 <span data-ttu-id="41638-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41638-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41638-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="41638-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="41638-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="41638-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41638-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41638-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41638-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41638-119">See also</span></span>

- [<span data-ttu-id="41638-120">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="41638-120">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="41638-121">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="41638-121">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="41638-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="41638-122">Hosting Interfaces</span></span>](hosting-interfaces.md)

---
title: Interfaccia IHostControl
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 9dd89abb332853b966aa81dc506099b7af6ca3b2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804925"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="403d7-102">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="403d7-102">IHostControl Interface</span></span>
<span data-ttu-id="403d7-103">Fornisce metodi per la configurazione del caricamento di assembly e per la determinazione delle interfacce di hosting supportate dall'host.</span><span class="sxs-lookup"><span data-stu-id="403d7-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="403d7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="403d7-104">Methods</span></span>  
  
|<span data-ttu-id="403d7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="403d7-105">Method</span></span>|<span data-ttu-id="403d7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="403d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="403d7-107">Metodo GetHostManager</span><span class="sxs-lookup"><span data-stu-id="403d7-107">GetHostManager Method</span></span>](ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="403d7-108">Ottiene un puntatore di interfaccia all'implementazione dell'host dell'interfaccia con l'oggetto specificato `IID` .</span><span class="sxs-lookup"><span data-stu-id="403d7-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="403d7-109">Metodo SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="403d7-109">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="403d7-110">Notifica all'host che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="403d7-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="403d7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="403d7-111">Requirements</span></span>  
 <span data-ttu-id="403d7-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="403d7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="403d7-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="403d7-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="403d7-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="403d7-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="403d7-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="403d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="403d7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="403d7-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="403d7-117">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="403d7-117">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="403d7-118">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="403d7-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="403d7-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="403d7-119">Hosting Interfaces</span></span>](hosting-interfaces.md)

---
title: Funzione ClrCreateManagedInstance
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f82303a3d38e7a5baaf1c3edcc41518228360d34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088457"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="93ccc-102">Funzione ClrCreateManagedInstance</span><span class="sxs-lookup"><span data-stu-id="93ccc-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="93ccc-103">Crea un'istanza del tipo gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="93ccc-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="93ccc-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93ccc-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="93ccc-105">Utilizzare l'attivazione di COM per creare un'istanza del tipo gestito o utilizzare l'hosting (vedere [CLR Hosting interfacce aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="93ccc-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93ccc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93ccc-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93ccc-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="93ccc-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="93ccc-108">[in] Un puntatore al nome del tipo di istanza richiesto.</span><span class="sxs-lookup"><span data-stu-id="93ccc-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="93ccc-109">[in] Il `IID` del tipo di istanza richiesto.</span><span class="sxs-lookup"><span data-stu-id="93ccc-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="93ccc-110">[out] Un puntatore a un puntatore a un'istanza del tipo gestito che è stata richiesta dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="93ccc-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93ccc-111">Note</span><span class="sxs-lookup"><span data-stu-id="93ccc-111">Remarks</span></span>  
 <span data-ttu-id="93ccc-112">Common language runtime deve già essere caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="93ccc-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="93ccc-113">Ad esempio, possono essere caricato tramite una chiamata ai [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funzionare prima il `ClrCreateManagedInstance` funzione viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="93ccc-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="93ccc-114">Se il runtime non viene caricato, `ClrCreateManagedInstance` innanzitutto tenta di caricare v1.0.3705 del runtime.</span><span class="sxs-lookup"><span data-stu-id="93ccc-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="93ccc-115">Se il problema persiste, tenta di caricare la versione più recente del runtime.</span><span class="sxs-lookup"><span data-stu-id="93ccc-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93ccc-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93ccc-116">Requirements</span></span>  
 <span data-ttu-id="93ccc-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93ccc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93ccc-118">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="93ccc-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93ccc-119">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93ccc-119">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="93ccc-120">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="93ccc-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="93ccc-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93ccc-121">See also</span></span>

- [<span data-ttu-id="93ccc-122">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="93ccc-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="93ccc-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="93ccc-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

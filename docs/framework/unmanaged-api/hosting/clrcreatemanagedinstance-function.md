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
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176539"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="c3694-102">Funzione ClrCreateManagedInstance</span><span class="sxs-lookup"><span data-stu-id="c3694-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="c3694-103">Crea un'istanza del tipo gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="c3694-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="c3694-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c3694-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="c3694-105">Utilizzare l'attivazione COM per creare un'istanza del tipo gestito oppure utilizzare l'hosting (vedere Interfacce di [hosting CLR aggiunte in .NET Framework 4 e 4.5).](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)</span><span class="sxs-lookup"><span data-stu-id="c3694-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3694-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3694-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3694-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3694-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="c3694-108">[in] Puntatore al nome del tipo di istanza richiesto.</span><span class="sxs-lookup"><span data-stu-id="c3694-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="c3694-109">[in] Oggetto `IID` del tipo di istanza richiesto.</span><span class="sxs-lookup"><span data-stu-id="c3694-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="c3694-110">[fuori] Puntatore a un puntatore a un'istanza del tipo gestito richiesto dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="c3694-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3694-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c3694-111">Remarks</span></span>  
 <span data-ttu-id="c3694-112">Common Language Runtime deve essere già caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="c3694-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="c3694-113">Ad esempio, può essere caricato utilizzando una chiamata alla funzione `ClrCreateManagedInstance` [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) prima che venga chiamata la funzione.</span><span class="sxs-lookup"><span data-stu-id="c3694-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="c3694-114">Se il runtime non `ClrCreateManagedInstance` viene caricato, si tenta innanzitutto di caricare v1.0.3705 del runtime.</span><span class="sxs-lookup"><span data-stu-id="c3694-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="c3694-115">Se l'operazione non riesce, tenta di caricare la versione più recente del runtime.</span><span class="sxs-lookup"><span data-stu-id="c3694-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3694-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3694-116">Requirements</span></span>  
 <span data-ttu-id="c3694-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3694-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3694-118">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c3694-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3694-119">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="c3694-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3694-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3694-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3694-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3694-121">See also</span></span>

- [<span data-ttu-id="c3694-122">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="c3694-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="c3694-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="c3694-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

---
title: Metodo ICLRMetaHost::RequestRuntimeLoadedNotification
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e7c1de620979b387e969f4b8c9f17f493e7bcb8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776554"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="43c37-102">Metodo ICLRMetaHost::RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="43c37-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="43c37-103">Fornisce una funzione di callback che viene garantita da chiamare quando viene caricata inizialmente una versione di common language runtime (CLR), ma non ancora iniziata.</span><span class="sxs-lookup"><span data-stu-id="43c37-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="43c37-104">Questo metodo sostituisce le [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="43c37-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c37-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43c37-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43c37-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="43c37-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="43c37-107">[in] La funzione di callback che viene richiamata quando è stato caricato un nuovo runtime.</span><span class="sxs-lookup"><span data-stu-id="43c37-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43c37-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="43c37-108">Return Value</span></span>  
 <span data-ttu-id="43c37-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="43c37-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="43c37-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43c37-110">HRESULT</span></span>|<span data-ttu-id="43c37-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43c37-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43c37-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="43c37-112">S_OK</span></span>|<span data-ttu-id="43c37-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="43c37-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="43c37-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="43c37-114">E_POINTER</span></span>|<span data-ttu-id="43c37-115">`pCallbackFunction` è null.</span><span class="sxs-lookup"><span data-stu-id="43c37-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43c37-116">Note</span><span class="sxs-lookup"><span data-stu-id="43c37-116">Remarks</span></span>  
 <span data-ttu-id="43c37-117">La richiamata funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="43c37-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="43c37-118">Il callback viene richiamato solo quando viene caricato un runtime per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="43c37-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="43c37-119">Non viene richiamato il callback per i caricamenti rientranti dello stesso runtime.</span><span class="sxs-lookup"><span data-stu-id="43c37-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="43c37-120">Per i carichi di runtime non rientrante, le chiamate alla funzione di callback vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="43c37-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="43c37-121">La funzione di callback presenta il seguente prototipo:</span><span class="sxs-lookup"><span data-stu-id="43c37-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="43c37-122">I prototipi di funzione di callback sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="43c37-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="43c37-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="43c37-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="43c37-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="43c37-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="43c37-125">Se l'host si intende caricare o provocare un altro runtime da caricare in modo rientrante, la `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` parametri che vengono messe a disposizione nel callback di funzione deve essere utilizzata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="43c37-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="43c37-126">`pfnCallbackThreadSet` deve essere chiamato dal thread che potrebbe causare un carico di runtime prima del tentativo di un carico di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="43c37-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="43c37-127">`pfnCallbackThreadUnset` deve essere chiamato quando il thread non è più comporterà un caricamento di runtime (e prima della restituzione dal callback iniziale).</span><span class="sxs-lookup"><span data-stu-id="43c37-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="43c37-128">`pfnCallbackThreadSet` e `pfnCallbackThreadUnset` sono entrambi non rientrante.</span><span class="sxs-lookup"><span data-stu-id="43c37-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43c37-129">Hosting di applicazioni non devono chiamare `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` rientrano nell'ambito del `pCallbackFunction` parametro.</span><span class="sxs-lookup"><span data-stu-id="43c37-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c37-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43c37-130">Requirements</span></span>  
 <span data-ttu-id="43c37-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43c37-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c37-132">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="43c37-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="43c37-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="43c37-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43c37-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c37-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c37-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43c37-135">See also</span></span>

- [<span data-ttu-id="43c37-136">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="43c37-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="43c37-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="43c37-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

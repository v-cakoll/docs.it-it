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
ms.openlocfilehash: 9ac041db64a874cc143657c601f30e4482dd2462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434435"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="9753f-102">Metodo ICLRMetaHost::RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="9753f-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="9753f-103">Fornisce una funzione di callback che viene chiamato quando è caricata una versione di common language runtime (CLR), ma non ancora avviata.</span><span class="sxs-lookup"><span data-stu-id="9753f-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="9753f-104">Questo metodo sostituisce il [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="9753f-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9753f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9753f-105">Syntax</span></span>  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9753f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9753f-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="9753f-107">[in] La funzione di callback che viene richiamata quando un nuovo runtime è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="9753f-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9753f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9753f-108">Return Value</span></span>  
 <span data-ttu-id="9753f-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="9753f-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9753f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9753f-110">HRESULT</span></span>|<span data-ttu-id="9753f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9753f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9753f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9753f-112">S_OK</span></span>|<span data-ttu-id="9753f-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9753f-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="9753f-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9753f-114">E_POINTER</span></span>|<span data-ttu-id="9753f-115">`pCallbackFunction` è null.</span><span class="sxs-lookup"><span data-stu-id="9753f-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9753f-116">Note</span><span class="sxs-lookup"><span data-stu-id="9753f-116">Remarks</span></span>  
 <span data-ttu-id="9753f-117">Il callback funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="9753f-117">The callback works in the following way:</span></span>  
  
-   <span data-ttu-id="9753f-118">Il callback viene richiamato solo quando viene caricato un runtime per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="9753f-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
-   <span data-ttu-id="9753f-119">Per i caricamenti rientranti del runtime stesso non viene richiamato il callback.</span><span class="sxs-lookup"><span data-stu-id="9753f-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
-   <span data-ttu-id="9753f-120">Per i caricamenti di runtime non rientrante, le chiamate alla funzione di callback vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="9753f-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="9753f-121">La funzione di callback è il seguente prototipo:</span><span class="sxs-lookup"><span data-stu-id="9753f-121">The callback function has the following prototype:</span></span>  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="9753f-122">I prototipi di funzione di callback sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9753f-122">The callback function prototypes are as follows:</span></span>  
  
-   <span data-ttu-id="9753f-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="9753f-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   <span data-ttu-id="9753f-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="9753f-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="9753f-125">Se l'host tenta di caricare o causare un altro runtime da caricare in modo rientrante, la `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` parametri che vengono fornite nel callback di funzione deve essere utilizzata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="9753f-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
-   <span data-ttu-id="9753f-126">`pfnCallbackThreadSet` deve essere chiamato dal thread che potrebbero causare un carico di runtime prima di tenta un carico di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="9753f-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
-   <span data-ttu-id="9753f-127">`pfnCallbackThreadUnset` deve essere chiamato quando il thread non comporterà un carico di runtime (e prima di restituire il callback iniziale).</span><span class="sxs-lookup"><span data-stu-id="9753f-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
-   <span data-ttu-id="9753f-128">`pfnCallbackThreadSet` e `pfnCallbackThreadUnset` sono entrambi non rientrante.</span><span class="sxs-lookup"><span data-stu-id="9753f-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9753f-129">Hosting di applicazioni non devono chiamare `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` all'esterno dell'ambito del `pCallbackFunction` parametro.</span><span class="sxs-lookup"><span data-stu-id="9753f-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9753f-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9753f-130">Requirements</span></span>  
 <span data-ttu-id="9753f-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9753f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9753f-132">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="9753f-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9753f-133">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9753f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9753f-134">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9753f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9753f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9753f-135">See Also</span></span>  
 [<span data-ttu-id="9753f-136">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="9753f-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="9753f-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="9753f-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

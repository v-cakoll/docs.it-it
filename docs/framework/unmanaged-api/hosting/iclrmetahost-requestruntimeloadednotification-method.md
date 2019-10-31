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
ms.openlocfilehash: 23f868bba2dc058d99f1c5c09e9b311b1ff3634a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140897"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="8a3ba-102">Metodo ICLRMetaHost::RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="8a3ba-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="8a3ba-103">Fornisce una funzione di callback che è garantita per essere chiamata quando una versione di Common Language Runtime (CLR) viene caricata per la prima volta, ma non ancora avviata.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="8a3ba-104">Questo metodo sostituisce la funzione [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="8a3ba-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a3ba-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a3ba-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a3ba-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a3ba-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="8a3ba-107">in Funzione di callback richiamata quando un nuovo runtime è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a3ba-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8a3ba-108">Return Value</span></span>  
 <span data-ttu-id="8a3ba-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8a3ba-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a3ba-110">HRESULT</span></span>|<span data-ttu-id="8a3ba-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a3ba-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a3ba-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a3ba-112">S_OK</span></span>|<span data-ttu-id="8a3ba-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="8a3ba-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8a3ba-114">E_POINTER</span></span>|<span data-ttu-id="8a3ba-115">`pCallbackFunction` è null.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a3ba-116">Note</span><span class="sxs-lookup"><span data-stu-id="8a3ba-116">Remarks</span></span>  
 <span data-ttu-id="8a3ba-117">Il callback funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="8a3ba-118">Il callback viene richiamato solo quando un runtime viene caricato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="8a3ba-119">Il callback non viene richiamato per i caricamenti rientranti dello stesso runtime.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="8a3ba-120">Per i caricamenti del runtime non rientranti, le chiamate alla funzione di callback vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="8a3ba-121">La funzione di callback presenta il seguente prototipo:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="8a3ba-122">I prototipi di funzione di callback sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="8a3ba-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="8a3ba-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="8a3ba-125">Se l'host intende caricare o causare il caricamento di un altro runtime in modo rientrante, i parametri `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` forniti nella funzione di callback devono essere utilizzati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8a3ba-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="8a3ba-126">`pfnCallbackThreadSet` deve essere chiamato dal thread che potrebbe causare un caricamento in fase di esecuzione prima che venga eseguito un tentativo di caricamento.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="8a3ba-127">`pfnCallbackThreadUnset` necessario chiamare quando il thread non provocherà più un carico di runtime di questo tipo (e prima della restituzione dal callback iniziale).</span><span class="sxs-lookup"><span data-stu-id="8a3ba-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="8a3ba-128">`pfnCallbackThreadSet` e `pfnCallbackThreadUnset` sono entrambi non rientranti.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a3ba-129">Le applicazioni host non devono chiamare `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` al di fuori dell'ambito del parametro `pCallbackFunction`.</span><span class="sxs-lookup"><span data-stu-id="8a3ba-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3ba-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a3ba-130">Requirements</span></span>  
 <span data-ttu-id="8a3ba-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a3ba-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3ba-132">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="8a3ba-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8a3ba-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8a3ba-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a3ba-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3ba-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3ba-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a3ba-135">See also</span></span>

- [<span data-ttu-id="8a3ba-136">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="8a3ba-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="8a3ba-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="8a3ba-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

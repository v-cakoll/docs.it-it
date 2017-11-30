---
title: Metodo ICLRRuntimeInfo::SetDefaultStartupFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.SetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1732073b9799453bd32447e7a688b0280e66f1ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="4f6ca-102">Metodo ICLRRuntimeInfo::SetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="4f6ca-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="4f6ca-103">Imposta i flag di avvio e il file di configurazione di host che verrà utilizzato per avviare il runtime.</span><span class="sxs-lookup"><span data-stu-id="4f6ca-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="4f6ca-104">Questo metodo sostituisce l'uso del `startupFlags` parametro il [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funzioni.</span><span class="sxs-lookup"><span data-stu-id="4f6ca-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f6ca-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f6ca-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f6ca-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f6ca-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="4f6ca-107">[in] I flag di avvio di host da impostare.</span><span class="sxs-lookup"><span data-stu-id="4f6ca-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="4f6ca-108">Utilizzare gli stessi flag come con la [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funzioni.</span><span class="sxs-lookup"><span data-stu-id="4f6ca-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="4f6ca-109">[in] Il percorso della directory del file di configurazione di host da impostare.</span><span class="sxs-lookup"><span data-stu-id="4f6ca-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f6ca-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4f6ca-110">Return Value</span></span>  
 <span data-ttu-id="4f6ca-111">Questo metodo restituisce il valore HRESULT specifico seguente nonché gli errori HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="4f6ca-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4f6ca-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f6ca-112">HRESULT</span></span>|<span data-ttu-id="4f6ca-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f6ca-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f6ca-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f6ca-114">S_OK</span></span>|<span data-ttu-id="4f6ca-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4f6ca-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f6ca-116">Note</span><span class="sxs-lookup"><span data-stu-id="4f6ca-116">Remarks</span></span>  
 <span data-ttu-id="4f6ca-117">Un host multithreading deve sincronizzare le chiamate a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="4f6ca-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="4f6ca-118">In caso contrario, il thread può chiamare il `SetStartupFlags` metodo dopo i thread B ha completato una chiamata a `SetStartupFlags` e prima che il thread B avvia il runtime.</span><span class="sxs-lookup"><span data-stu-id="4f6ca-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f6ca-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f6ca-119">Requirements</span></span>  
 <span data-ttu-id="4f6ca-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f6ca-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f6ca-121">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="4f6ca-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4f6ca-122">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f6ca-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f6ca-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f6ca-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f6ca-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f6ca-124">See Also</span></span>  
 [<span data-ttu-id="4f6ca-125">ICLRRuntimeInfo (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f6ca-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="4f6ca-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4f6ca-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="4f6ca-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="4f6ca-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

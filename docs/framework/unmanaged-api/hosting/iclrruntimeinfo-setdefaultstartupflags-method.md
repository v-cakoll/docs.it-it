---
title: Metodo ICLRRuntimeInfo::SetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d021eb2d8da8c85fe538f0c73527876482429718
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656882"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="b101d-102">Metodo ICLRRuntimeInfo::SetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="b101d-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="b101d-103">Imposta i flag di avvio e il file di configurazione di host che verrà usato per avviare il runtime.</span><span class="sxs-lookup"><span data-stu-id="b101d-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="b101d-104">Questo metodo sostituisce l'uso del `startupFlags` parametro il [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funzioni.</span><span class="sxs-lookup"><span data-stu-id="b101d-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b101d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b101d-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b101d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b101d-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="b101d-107">[in] I flag di avvio host da impostare.</span><span class="sxs-lookup"><span data-stu-id="b101d-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="b101d-108">Usare gli stessi flag come con le [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funzioni.</span><span class="sxs-lookup"><span data-stu-id="b101d-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="b101d-109">[in] Il percorso della directory del file di configurazione di host da impostare.</span><span class="sxs-lookup"><span data-stu-id="b101d-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b101d-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b101d-110">Return Value</span></span>  
 <span data-ttu-id="b101d-111">Questo metodo restituisce il valore HRESULT specifico seguente, nonché gli errori HRESULT che indicano un errore di metodo.</span><span class="sxs-lookup"><span data-stu-id="b101d-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b101d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b101d-112">HRESULT</span></span>|<span data-ttu-id="b101d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b101d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b101d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b101d-114">S_OK</span></span>|<span data-ttu-id="b101d-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="b101d-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b101d-116">Note</span><span class="sxs-lookup"><span data-stu-id="b101d-116">Remarks</span></span>  
 <span data-ttu-id="b101d-117">Un host a thread multipli è necessario sincronizzare le chiamate a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="b101d-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="b101d-118">In caso contrario, il thread può chiamare le `SetStartupFlags` metodo dopo che il thread B viene completata una chiamata a `SetStartupFlags` e prima che il thread B avvia il runtime.</span><span class="sxs-lookup"><span data-stu-id="b101d-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b101d-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b101d-119">Requirements</span></span>  
 <span data-ttu-id="b101d-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b101d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b101d-121">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b101d-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b101d-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b101d-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b101d-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b101d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b101d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b101d-124">See also</span></span>
- [<span data-ttu-id="b101d-125">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="b101d-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="b101d-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="b101d-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b101d-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="b101d-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

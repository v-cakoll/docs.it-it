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
ms.openlocfilehash: 7d201962976d198372226eb686696fcdccf3eb69
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762162"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="36996-102">Metodo ICLRRuntimeInfo::SetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="36996-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="36996-103">Imposta i flag di avvio e il file di configurazione host che verranno usati per avviare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="36996-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="36996-104">Questo metodo sostituisce l'utilizzo del `startupFlags` parametro nelle funzioni [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="36996-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36996-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36996-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36996-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="36996-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="36996-107">in Flag di avvio dell'host da impostare.</span><span class="sxs-lookup"><span data-stu-id="36996-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="36996-108">Utilizzare gli stessi flag delle funzioni [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="36996-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="36996-109">in Percorso della directory del file di configurazione host da impostare.</span><span class="sxs-lookup"><span data-stu-id="36996-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36996-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="36996-110">Return Value</span></span>  
 <span data-ttu-id="36996-111">Questo metodo restituisce il seguente HRESULT specifico, oltre a errori HRESULT che indicano un errore del metodo.</span><span class="sxs-lookup"><span data-stu-id="36996-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="36996-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36996-112">HRESULT</span></span>|<span data-ttu-id="36996-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36996-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36996-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="36996-114">S_OK</span></span>|<span data-ttu-id="36996-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="36996-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36996-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="36996-116">Remarks</span></span>  
 <span data-ttu-id="36996-117">Un host multithread deve sincronizzare le chiamate a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="36996-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="36996-118">In caso contrario, il thread A può chiamare il `SetStartupFlags` metodo dopo che il thread b completa una chiamata a `SetStartupFlags` e prima che il thread b avvii il Runtime.</span><span class="sxs-lookup"><span data-stu-id="36996-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36996-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36996-119">Requirements</span></span>  
 <span data-ttu-id="36996-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36996-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36996-121">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="36996-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="36996-122">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="36996-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36996-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36996-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36996-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36996-124">See also</span></span>

- [<span data-ttu-id="36996-125">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="36996-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="36996-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="36996-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="36996-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="36996-127">Hosting</span></span>](index.md)

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
ms.openlocfilehash: aa02d42511a863434fef236f90afae2c5417a78d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504017"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="5c398-102">Metodo ICLRRuntimeInfo::SetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="5c398-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="5c398-103">Imposta i flag di avvio e il file di configurazione host che verranno usati per avviare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="5c398-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="5c398-104">Questo metodo sostituisce l'utilizzo del `startupFlags` parametro nelle funzioni [CorBindToRuntimeEx](corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="5c398-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c398-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c398-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c398-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c398-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="5c398-107">in Flag di avvio dell'host da impostare.</span><span class="sxs-lookup"><span data-stu-id="5c398-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="5c398-108">Utilizzare gli stessi flag delle funzioni [CorBindToRuntimeEx](corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="5c398-108">Use the same flags as with the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="5c398-109">in Percorso della directory del file di configurazione host da impostare.</span><span class="sxs-lookup"><span data-stu-id="5c398-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c398-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5c398-110">Return Value</span></span>  
 <span data-ttu-id="5c398-111">Questo metodo restituisce il seguente HRESULT specifico, oltre a errori HRESULT che indicano un errore del metodo.</span><span class="sxs-lookup"><span data-stu-id="5c398-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5c398-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c398-112">HRESULT</span></span>|<span data-ttu-id="5c398-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c398-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c398-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c398-114">S_OK</span></span>|<span data-ttu-id="5c398-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="5c398-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c398-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5c398-116">Remarks</span></span>  
 <span data-ttu-id="5c398-117">Un host multithread deve sincronizzare le chiamate a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="5c398-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="5c398-118">In caso contrario, il thread A può chiamare il `SetStartupFlags` metodo dopo che il thread b completa una chiamata a `SetStartupFlags` e prima che il thread b avvii il Runtime.</span><span class="sxs-lookup"><span data-stu-id="5c398-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c398-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c398-119">Requirements</span></span>  
 <span data-ttu-id="5c398-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c398-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c398-121">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="5c398-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5c398-122">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c398-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c398-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c398-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c398-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c398-124">See also</span></span>

- [<span data-ttu-id="5c398-125">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="5c398-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="5c398-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5c398-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="5c398-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="5c398-127">Hosting</span></span>](index.md)

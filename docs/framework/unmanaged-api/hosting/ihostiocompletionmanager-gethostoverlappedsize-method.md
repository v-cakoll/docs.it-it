---
title: Metodo IHostIoCompletionManager::GetHostOverlappedSize
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
ms.openlocfilehash: 3c662021894acbb8eb448fa2166498254158caa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133870"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="66146-102">Metodo IHostIoCompletionManager::GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="66146-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="66146-103">Ottiene le dimensioni dei dati personalizzati che l'host intende accodare alle richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="66146-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66146-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66146-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66146-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="66146-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="66146-106">out Puntatore al numero di byte che il Common Language Runtime (CLR) deve allocare oltre alla dimensione dell'oggetto Win32 `OVERLAPPED`.</span><span class="sxs-lookup"><span data-stu-id="66146-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66146-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="66146-107">Return Value</span></span>  
  
|<span data-ttu-id="66146-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66146-108">HRESULT</span></span>|<span data-ttu-id="66146-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66146-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66146-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="66146-110">S_OK</span></span>|<span data-ttu-id="66146-111">`GetHostOverlappedSize` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="66146-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="66146-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="66146-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="66146-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="66146-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="66146-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="66146-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="66146-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="66146-115">The call timed out.</span></span>|  
|<span data-ttu-id="66146-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="66146-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="66146-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="66146-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="66146-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="66146-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="66146-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="66146-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="66146-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="66146-120">E_FAIL</span></span>|<span data-ttu-id="66146-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="66146-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="66146-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="66146-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="66146-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="66146-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66146-124">Note</span><span class="sxs-lookup"><span data-stu-id="66146-124">Remarks</span></span>  
 <span data-ttu-id="66146-125">Tutte le chiamate di I/O asincrone alle API della piattaforma Windows accettano un oggetto `OVERLAPPED` Win32, che fornisce informazioni come la posizione del puntatore del file.</span><span class="sxs-lookup"><span data-stu-id="66146-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="66146-126">Per mantenere lo stato, le applicazioni che effettuano chiamate di I/O asincrone aggiungono in genere dati personalizzati alla struttura.</span><span class="sxs-lookup"><span data-stu-id="66146-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="66146-127">`GetHostOverlappedSize` e [IHostIoCompletionManager:: InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) offrono la possibilità per l'host di includere tali dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="66146-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="66146-128">CLR chiama il metodo `GetHostOverlappedSize` per determinare le dimensioni dei dati personalizzati che l'host intende accodare all'oggetto `OVERLAPPED`.</span><span class="sxs-lookup"><span data-stu-id="66146-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66146-129">`GetHostOverlappedSize` viene chiamata una sola volta.</span><span class="sxs-lookup"><span data-stu-id="66146-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="66146-130">I dati personalizzati dell'host devono avere le stesse dimensioni per ogni richiesta di I/O.</span><span class="sxs-lookup"><span data-stu-id="66146-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="66146-131">Le dimensioni dell'oggetto `OVERLAPPED` stesso non sono incluse nel valore di `pcbSize`.</span><span class="sxs-lookup"><span data-stu-id="66146-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="66146-132">Per ulteriori informazioni sulla struttura `OVERLAPPED`, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="66146-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66146-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="66146-133">Requirements</span></span>  
 <span data-ttu-id="66146-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66146-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66146-135">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="66146-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66146-136">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="66146-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66146-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66146-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66146-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66146-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="66146-139">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="66146-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="66146-140">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="66146-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

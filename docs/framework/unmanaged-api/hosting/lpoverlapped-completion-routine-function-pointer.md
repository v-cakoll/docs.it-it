---
title: Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LPOVERLAPPED_COMPLETION_ROUTINE
api_location: mscoree.dll
api_type: COM
f1_keywords: LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords: LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d50f2058796d4c5c900474cdcbe71d8a5a911ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="9eaac-102">Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="9eaac-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="9eaac-103">Punta a una funzione che notifica all'host quando un sovrapposte (vale a dire asincrona) i/o in un dispositivo è stata completata.</span><span class="sxs-lookup"><span data-stu-id="9eaac-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="9eaac-104">Questo puntatore a funzione è stato deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9eaac-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eaac-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9eaac-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9eaac-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9eaac-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="9eaac-107">[in] Un valore che è un codice di errore se il dispositivo è stata chiusa; in caso contrario, questo valore è zero.</span><span class="sxs-lookup"><span data-stu-id="9eaac-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="9eaac-108">La chiusura di un dispositivo causa tutte in sospeso i/o al dispositivo per essere completate immediatamente.</span><span class="sxs-lookup"><span data-stu-id="9eaac-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="9eaac-109">[in] Il numero di byte trasferiti dall'operazione dei / o.</span><span class="sxs-lookup"><span data-stu-id="9eaac-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="9eaac-110">[in] Un puntatore a una struttura che contiene le informazioni da utilizzare per completare la richiesta dei / o.</span><span class="sxs-lookup"><span data-stu-id="9eaac-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9eaac-111">Note</span><span class="sxs-lookup"><span data-stu-id="9eaac-111">Remarks</span></span>  
 <span data-ttu-id="9eaac-112">La funzione a cui `LPOVERLAPPED_COMPLETION_ROUTINE` punti è una funzione di callback e deve essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="9eaac-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="9eaac-113">La funzione di callback consente all'host di elaborare la richiesta dei / o completata.</span><span class="sxs-lookup"><span data-stu-id="9eaac-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eaac-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9eaac-114">Requirements</span></span>  
 <span data-ttu-id="9eaac-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9eaac-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eaac-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9eaac-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9eaac-117">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="9eaac-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="9eaac-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eaac-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eaac-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9eaac-119">See Also</span></span>  
 [<span data-ttu-id="9eaac-120">Funzioni di Hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="9eaac-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

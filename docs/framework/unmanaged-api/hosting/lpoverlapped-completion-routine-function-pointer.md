---
title: Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce2ce6dd1210eef94e77b5d6a2d58a35cf971e6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138775"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="5f893-102">Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="5f893-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="5f893-103">Punta a una funzione che notifica all'host quando un sovrapposta (vale a dire, asincrona) i/o a un dispositivo è stata completata.</span><span class="sxs-lookup"><span data-stu-id="5f893-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="5f893-104">Questo puntatore a funzione è stato deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f893-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f893-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f893-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f893-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f893-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="5f893-107">[in] Un valore che corrisponde a un codice di errore se il dispositivo è stato chiuso; in caso contrario, questo valore è zero.</span><span class="sxs-lookup"><span data-stu-id="5f893-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="5f893-108">Chiusura di un dispositivo fa sì che tutte in sospeso i/o al dispositivo per essere completata immediatamente.</span><span class="sxs-lookup"><span data-stu-id="5f893-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="5f893-109">[in] Il numero di byte trasferiti dall'operazione dei / o.</span><span class="sxs-lookup"><span data-stu-id="5f893-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="5f893-110">[in] Un puntatore a una struttura che contiene le informazioni da utilizzare per completare la richiesta dei / o.</span><span class="sxs-lookup"><span data-stu-id="5f893-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f893-111">Note</span><span class="sxs-lookup"><span data-stu-id="5f893-111">Remarks</span></span>  
 <span data-ttu-id="5f893-112">La funzione a cui `LPOVERLAPPED_COMPLETION_ROUTINE` punti è una funzione di callback e devono essere implementati dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="5f893-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="5f893-113">La funzione di richiamata consente all'host elaborare la richiesta dei / o completata.</span><span class="sxs-lookup"><span data-stu-id="5f893-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f893-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f893-114">Requirements</span></span>  
 <span data-ttu-id="5f893-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f893-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f893-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5f893-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f893-117">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="5f893-117">**Library:** MSCorWks.dll</span></span>  
  
 **<span data-ttu-id="5f893-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5f893-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5f893-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f893-119">See also</span></span>

- [<span data-ttu-id="5f893-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="5f893-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

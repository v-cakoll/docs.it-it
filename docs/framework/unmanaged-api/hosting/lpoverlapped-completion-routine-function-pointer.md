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
ms.openlocfilehash: c0bdd9e59f5794dbb0d447dc2cc6cb682bfdf09f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008482"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a><span data-ttu-id="f7510-102">Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="f7510-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="f7510-103">Punta a una funzione che notifica all'host quando è stata completata un'operazione di I/O sovrapposta (ovvero asincrona) a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7510-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="f7510-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f7510-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7510-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7510-105">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7510-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7510-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="f7510-107">in Valore che rappresenta un codice di errore se il dispositivo è stato chiuso; in caso contrario, questo valore è zero.</span><span class="sxs-lookup"><span data-stu-id="f7510-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="f7510-108">La chiusura di un dispositivo comporta immediatamente il completamento di tutte le operazioni di I/O in sospeso nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7510-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="f7510-109">in Numero di byte trasferiti dall'operazione di I/O.</span><span class="sxs-lookup"><span data-stu-id="f7510-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="f7510-110">in Puntatore a una struttura che contiene le informazioni da utilizzare per completare la richiesta di I/O.</span><span class="sxs-lookup"><span data-stu-id="f7510-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7510-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="f7510-111">Remarks</span></span>  
 <span data-ttu-id="f7510-112">Funzione a cui `LPOVERLAPPED_COMPLETION_ROUTINE` punta è una funzione di callback e deve essere implementata dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="f7510-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="f7510-113">La funzione di callback consente all'host di elaborare la richiesta di I/O completata.</span><span class="sxs-lookup"><span data-stu-id="f7510-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7510-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7510-114">Requirements</span></span>  
 <span data-ttu-id="f7510-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7510-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7510-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f7510-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7510-117">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="f7510-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f7510-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7510-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7510-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7510-119">See also</span></span>

- [<span data-ttu-id="f7510-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="f7510-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

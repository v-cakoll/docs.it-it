---
title: Metodo ICoreClrDebugTarget::EnumRuntimes
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
ms.openlocfilehash: fc8269d4cc22ab53569edaa48c27b4a01970dcc7
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397180"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="a1b19-102">Metodo ICoreClrDebugTarget::EnumRuntimes</span><span class="sxs-lookup"><span data-stu-id="a1b19-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="a1b19-103">Enumera i Common Language Runtime (CLR) nel processo specificato in cui è in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="a1b19-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1b19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1b19-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1b19-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1b19-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="a1b19-106">[in] ID del processo interno per il quale si vogliono enumerare i runtime.</span><span class="sxs-lookup"><span data-stu-id="a1b19-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="a1b19-107">Si produrrà `m_dwInternalID` dal [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a1b19-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="a1b19-108">[out] Numero di runtime restituiti in `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="a1b19-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="a1b19-109">Il valore può essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="a1b19-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="a1b19-110">out Matrice di strutture [CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md) che rappresentano i runtime caricati nel processo di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="a1b19-110">[out] An array of [CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1b19-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a1b19-111">Return Value</span></span>  
 <span data-ttu-id="a1b19-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1b19-112">S_OK</span></span>  
 <span data-ttu-id="a1b19-113">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="a1b19-113">Success.</span></span>  
  
 <span data-ttu-id="a1b19-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a1b19-114">S_FALSE</span></span>  
 <span data-ttu-id="a1b19-115">`dwInternalProcessID` non corrisponde a nessun processo in esecuzione nel computer, probabilmente perché il processo è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="a1b19-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="a1b19-116">`pcRuntimes` e `ppRuntimes` saranno null.</span><span class="sxs-lookup"><span data-stu-id="a1b19-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="a1b19-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a1b19-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="a1b19-118">Non è possibile allocare memoria sufficiente per `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="a1b19-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="a1b19-119">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="a1b19-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a1b19-120">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="a1b19-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1b19-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="a1b19-121">Remarks</span></span>  
 <span data-ttu-id="a1b19-122">Per liberare la memoria allocata da questo metodo, chiamare il metodo [ICoreClrDebugTarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a1b19-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1b19-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1b19-123">Requirements</span></span>  
 <span data-ttu-id="a1b19-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1b19-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1b19-125">**Intestazione:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="a1b19-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="a1b19-126">**Libreria:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="a1b19-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="a1b19-127">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="a1b19-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b19-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a1b19-128">See also</span></span>

- [<span data-ttu-id="a1b19-129">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="a1b19-129">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)

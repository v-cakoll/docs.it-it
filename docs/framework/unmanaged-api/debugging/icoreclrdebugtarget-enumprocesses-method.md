---
title: Metodo ICoreClrDebugTarget::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
ms.openlocfilehash: 6484832e8e737b9a0d0b3eaf3ede4078729f7a4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178434"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="ff79b-102">Metodo ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="ff79b-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="ff79b-103">Enumera i processi in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="ff79b-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff79b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff79b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff79b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff79b-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="ff79b-106">[out] Numero di processi restituiti in `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="ff79b-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="ff79b-107">Il valore può essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="ff79b-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="ff79b-108">[fuori] Matrice di strutture [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) che rappresentano i processi in esecuzione nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="ff79b-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff79b-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ff79b-109">Return Value</span></span>  
 <span data-ttu-id="ff79b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff79b-110">S_OK</span></span>  
 <span data-ttu-id="ff79b-111">Esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ff79b-111">Success.</span></span>  
  
 <span data-ttu-id="ff79b-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ff79b-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="ff79b-113">Non è possibile allocare memoria sufficiente per `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="ff79b-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="ff79b-114">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="ff79b-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="ff79b-115">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="ff79b-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff79b-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ff79b-116">Remarks</span></span>  
 <span data-ttu-id="ff79b-117">Per liberare la memoria allocata da questo metodo, chiamare il [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="ff79b-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff79b-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff79b-118">Requirements</span></span>  
 <span data-ttu-id="ff79b-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff79b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff79b-120">**Intestazione:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="ff79b-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ff79b-121">**Libreria:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ff79b-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ff79b-122">Versioni di **.NET Framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ff79b-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff79b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff79b-123">See also</span></span>

- [<span data-ttu-id="ff79b-124">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="ff79b-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)

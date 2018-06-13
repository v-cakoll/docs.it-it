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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c09b70b5afb0561d32e55dd89df6cac083abc068
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422016"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="bf83e-102">Metodo ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="bf83e-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="bf83e-103">Enumera i processi in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="bf83e-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf83e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf83e-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf83e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bf83e-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="bf83e-106">[out] Numero di processi restituiti in `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="bf83e-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="bf83e-107">Il valore può essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="bf83e-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="bf83e-108">[out] Matrice di [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) strutture che rappresentano i processi in esecuzione nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="bf83e-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf83e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bf83e-109">Return Value</span></span>  
 <span data-ttu-id="bf83e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf83e-110">S_OK</span></span>  
 <span data-ttu-id="bf83e-111">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="bf83e-111">Success.</span></span>  
  
 <span data-ttu-id="bf83e-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bf83e-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="bf83e-113">Non è possibile allocare memoria sufficiente per `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="bf83e-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="bf83e-114">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="bf83e-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="bf83e-115">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="bf83e-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf83e-116">Note</span><span class="sxs-lookup"><span data-stu-id="bf83e-116">Remarks</span></span>  
 <span data-ttu-id="bf83e-117">Per liberare la memoria allocata da questo metodo, chiamare il [ICoreClrDebugTarget:: FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="bf83e-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf83e-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf83e-118">Requirements</span></span>  
 <span data-ttu-id="bf83e-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf83e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf83e-120">**Intestazione:** coreclrremotedebugginginterfaces. H</span><span class="sxs-lookup"><span data-stu-id="bf83e-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="bf83e-121">**Libreria:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="bf83e-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="bf83e-122">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="bf83e-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf83e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf83e-123">See Also</span></span>  
 [<span data-ttu-id="bf83e-124">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="bf83e-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)

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
ms.openlocfilehash: 0c1b18f24fd30b5f6d5e85633fc0c25839aba6df
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396412"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="39213-102">Metodo ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="39213-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="39213-103">Enumera i processi in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="39213-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39213-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39213-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39213-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="39213-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="39213-106">[out] Numero di processi restituiti in `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="39213-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="39213-107">Il valore può essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="39213-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="39213-108">out Matrice di strutture [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) che rappresentano i processi in esecuzione nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="39213-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39213-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="39213-109">Return Value</span></span>  
 <span data-ttu-id="39213-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="39213-110">S_OK</span></span>  
 <span data-ttu-id="39213-111">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="39213-111">Success.</span></span>  
  
 <span data-ttu-id="39213-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="39213-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="39213-113">Non è possibile allocare memoria sufficiente per `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="39213-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="39213-114">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="39213-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="39213-115">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="39213-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39213-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="39213-116">Remarks</span></span>  
 <span data-ttu-id="39213-117">Per liberare la memoria allocata da questo metodo, chiamare il metodo [ICoreClrDebugTarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="39213-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39213-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39213-118">Requirements</span></span>  
 <span data-ttu-id="39213-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39213-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39213-120">**Intestazione:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="39213-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="39213-121">**Libreria:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="39213-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="39213-122">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="39213-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39213-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="39213-123">See also</span></span>

- [<span data-ttu-id="39213-124">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="39213-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)

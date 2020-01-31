---
title: Metodo ICorProfilerInfo2::GetAppDomainStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 05d8c44655d8670194035c336bd62ae5d53bfec3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862971"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="62087-102">Metodo ICorProfilerInfo2::GetAppDomainStaticAddress</span><span class="sxs-lookup"><span data-stu-id="62087-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="62087-103">Ottiene l'indirizzo del campo statico del dominio dell'applicazione specificato nell'ambito del dominio dell'applicazione specificato.</span><span class="sxs-lookup"><span data-stu-id="62087-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62087-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62087-104">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62087-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="62087-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="62087-106">in ID classe della classe che contiene il campo statico dell'applicazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="62087-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="62087-107">in Token di metadati per il campo di dominio applicazione richiesto-statico.</span><span class="sxs-lookup"><span data-stu-id="62087-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="62087-108">in ID del dominio applicazione che rappresenta l'ambito per il campo statico richiesto.</span><span class="sxs-lookup"><span data-stu-id="62087-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="62087-109">out Puntatore all'indirizzo del campo statico che si trova all'interno del dominio applicazione specificato.</span><span class="sxs-lookup"><span data-stu-id="62087-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62087-110">Note</span><span class="sxs-lookup"><span data-stu-id="62087-110">Remarks</span></span>  
 <span data-ttu-id="62087-111">Il metodo `GetAppDomainStaticAddress` può restituire uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="62087-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="62087-112">CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="62087-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="62087-113">Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="62087-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="62087-114">Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo Garbage Collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="62087-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="62087-115">Prima che il costruttore della classe di una classe venga completato, `GetAppDomainStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbero essere già inizializzati e vengono radicati Garbage Collection oggetti.</span><span class="sxs-lookup"><span data-stu-id="62087-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62087-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="62087-116">Requirements</span></span>  
 <span data-ttu-id="62087-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62087-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62087-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62087-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62087-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62087-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62087-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62087-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62087-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62087-121">See also</span></span>

- [<span data-ttu-id="62087-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="62087-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="62087-123">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="62087-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

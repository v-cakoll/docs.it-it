---
title: Metodo ICorProfilerInfo::GetAppDomainInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAppDomainInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type:
- apiref
ms.openlocfilehash: 0407b7057753f7fdee6ea6b1d05144b135b6378a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864089"
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a><span data-ttu-id="860e2-102">Metodo ICorProfilerInfo::GetAppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="860e2-102">ICorProfilerInfo::GetAppDomainInfo Method</span></span>
<span data-ttu-id="860e2-103">Accetta un ID del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="860e2-103">Accepts an application domain ID.</span></span> <span data-ttu-id="860e2-104">Restituisce il nome di un domino applicazione e l'ID del processo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="860e2-104">Returns an application domain name and the ID of the process that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="860e2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="860e2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="860e2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="860e2-106">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="860e2-107">[in] ID del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="860e2-107">[in] The ID of the application domain.</span></span>  
  
 `cchName`  
 <span data-ttu-id="860e2-108">[in] Lunghezza, espressa in caratteri, del buffer restituito `szName`.</span><span class="sxs-lookup"><span data-stu-id="860e2-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="860e2-109">[out] Puntatore ai caratteri totali del nome del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="860e2-109">[out] A pointer to the total character length of the application domain name.</span></span>  
  
 `szName`  
 <span data-ttu-id="860e2-110">[out] Buffer per caratteri di tipo "wide" fornito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="860e2-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="860e2-111">Una volta completato il metodo, il parametro `szName` conterrà il nome del dominio dell'applicazione completo o parziale.</span><span class="sxs-lookup"><span data-stu-id="860e2-111">When the method returns, `szName` will contain the full or partial application domain name.</span></span>  
  
 `pProcessId`  
 <span data-ttu-id="860e2-112">[out] Puntatore all'ID del processo che contiene il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="860e2-112">[out] A pointer to the ID of the process that contains the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="860e2-113">Note</span><span class="sxs-lookup"><span data-stu-id="860e2-113">Remarks</span></span>  
 <span data-ttu-id="860e2-114">Dopo il completamento del metodo, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome completo del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="860e2-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the application domain.</span></span> <span data-ttu-id="860e2-115">A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="860e2-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="860e2-116">Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetAppDomainInfo`.</span><span class="sxs-lookup"><span data-stu-id="860e2-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAppDomainInfo` again.</span></span>  
  
 <span data-ttu-id="860e2-117">In alternativa, è possibile chiamare innanzitutto `GetAppDomainInfo` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="860e2-117">Alternatively, you can first call `GetAppDomainInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="860e2-118">È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcchName` e chiamare nuovamente `GetAppDomainInfo`.</span><span class="sxs-lookup"><span data-stu-id="860e2-118">You can then set the buffer size to the value returned in `pcchName` and call `GetAppDomainInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="860e2-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="860e2-119">Requirements</span></span>  
 <span data-ttu-id="860e2-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="860e2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="860e2-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="860e2-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="860e2-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="860e2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="860e2-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="860e2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="860e2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="860e2-124">See also</span></span>

- [<span data-ttu-id="860e2-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="860e2-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="860e2-126">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="860e2-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="860e2-127">Profilatura</span><span class="sxs-lookup"><span data-stu-id="860e2-127">Profiling</span></span>](index.md)

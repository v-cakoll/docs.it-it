---
title: Metodo ICorProfilerInfo3::GetRuntimeInformation
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
ms.openlocfilehash: 20556d85655a0a1bbe069a94b99c19c774a13ce6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449690"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="30a30-102">Metodo ICorProfilerInfo3::GetRuntimeInformation</span><span class="sxs-lookup"><span data-stu-id="30a30-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="30a30-103">Fornisce informazioni sulla versione per il Common Language Runtime (CLR) sottofilato.</span><span class="sxs-lookup"><span data-stu-id="30a30-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a30-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30a30-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30a30-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30a30-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="30a30-106">out ID rappresentativo di un'istanza CLR in esecuzione in un processo.</span><span class="sxs-lookup"><span data-stu-id="30a30-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="30a30-107">Si tratta dello stesso `ClrInstanceID` che l'evento di avvio di Event Tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="30a30-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="30a30-108">out Tipo di Runtime.</span><span class="sxs-lookup"><span data-stu-id="30a30-108">[out] The runtime type.</span></span> <span data-ttu-id="30a30-109">Questo parametro restituisce `COR_PRF_DESKTOP_CLR` per la versione desktop di CLR o `COR_PRF_CORE_CLR` per la versione principale di CLR utilizzata in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="30a30-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="30a30-110">out Numero di versione principale di CLR.</span><span class="sxs-lookup"><span data-stu-id="30a30-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="30a30-111">out Numero di versione secondario di CLR.</span><span class="sxs-lookup"><span data-stu-id="30a30-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="30a30-112">out Numero di versione della build di CLR.</span><span class="sxs-lookup"><span data-stu-id="30a30-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="30a30-113">out Numero di versione di CLR associato a un aggiornamento software.</span><span class="sxs-lookup"><span data-stu-id="30a30-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="30a30-114">in Lunghezza, in caratteri, del buffer a cui punta il `szVersionString`.</span><span class="sxs-lookup"><span data-stu-id="30a30-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="30a30-115">out Lunghezza, in caratteri, del `szVersionString`.</span><span class="sxs-lookup"><span data-stu-id="30a30-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="30a30-116">out Stringa della versione CLR.</span><span class="sxs-lookup"><span data-stu-id="30a30-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30a30-117">Note</span><span class="sxs-lookup"><span data-stu-id="30a30-117">Remarks</span></span>  
 <span data-ttu-id="30a30-118">È possibile passare null per qualsiasi parametro.</span><span class="sxs-lookup"><span data-stu-id="30a30-118">You may pass null for any parameter.</span></span> <span data-ttu-id="30a30-119">Tuttavia, `pcchVersionString` non può essere null a meno che anche `szVersionString` non sia null.</span><span class="sxs-lookup"><span data-stu-id="30a30-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a30-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30a30-120">Requirements</span></span>  
 <span data-ttu-id="30a30-121">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30a30-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a30-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30a30-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30a30-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30a30-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30a30-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a30-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a30-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30a30-125">See also</span></span>

- [<span data-ttu-id="30a30-126">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="30a30-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="30a30-127">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="30a30-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="30a30-128">Profilatura</span><span class="sxs-lookup"><span data-stu-id="30a30-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

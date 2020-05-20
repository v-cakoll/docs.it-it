---
title: Metodo ICLRRuntimeInfo::GetProcAddress
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 2690a5c2e7c499d68ef9e903c62bff8f85e72e8e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703871"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="e00b3-102">Metodo ICLRRuntimeInfo::GetProcAddress</span><span class="sxs-lookup"><span data-stu-id="e00b3-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="e00b3-103">Ottiene l'indirizzo di una funzione specificata esportata dalla Common Language Runtime (CLR) associata a questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e00b3-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="e00b3-104">Questo metodo sostituisce la funzione [GetRealProcAddress](getrealprocaddress-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e00b3-104">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e00b3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e00b3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e00b3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e00b3-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="e00b3-107">in Nome della funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="e00b3-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="e00b3-108">out Indirizzo della funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="e00b3-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e00b3-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e00b3-109">Return Value</span></span>  
 <span data-ttu-id="e00b3-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="e00b3-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e00b3-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e00b3-111">HRESULT</span></span>|<span data-ttu-id="e00b3-112">Description</span><span class="sxs-lookup"><span data-stu-id="e00b3-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e00b3-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e00b3-113">S_OK</span></span>|<span data-ttu-id="e00b3-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e00b3-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="e00b3-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e00b3-115">E_POINTER</span></span>|<span data-ttu-id="e00b3-116">`pszProcName` o `ppProc` è null.</span><span class="sxs-lookup"><span data-stu-id="e00b3-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="e00b3-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="e00b3-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="e00b3-118">La funzione specificata non è una funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="e00b3-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e00b3-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e00b3-119">Remarks</span></span>  
 <span data-ttu-id="e00b3-120">Questo metodo fa sì che CLR venga caricato ma non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="e00b3-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e00b3-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e00b3-121">Requirements</span></span>  
 <span data-ttu-id="e00b3-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e00b3-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e00b3-123">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="e00b3-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e00b3-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e00b3-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e00b3-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e00b3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e00b3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e00b3-126">See also</span></span>

- [<span data-ttu-id="e00b3-127">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="e00b3-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="e00b3-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="e00b3-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e00b3-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="e00b3-129">Hosting</span></span>](index.md)

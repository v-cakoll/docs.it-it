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
ms.openlocfilehash: cedda39aeebc62c6bf43f42ae2daf6f6f515fd27
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120278"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="770b7-102">Metodo ICLRRuntimeInfo::GetProcAddress</span><span class="sxs-lookup"><span data-stu-id="770b7-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="770b7-103">Ottiene l'indirizzo di una funzione specificata esportata dalla Common Language Runtime (CLR) associata a questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="770b7-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="770b7-104">Questo metodo sostituisce la funzione [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) .</span><span class="sxs-lookup"><span data-stu-id="770b7-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="770b7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="770b7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="770b7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="770b7-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="770b7-107">in Nome della funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="770b7-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="770b7-108">out Indirizzo della funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="770b7-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="770b7-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="770b7-109">Return Value</span></span>  
 <span data-ttu-id="770b7-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="770b7-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="770b7-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="770b7-111">HRESULT</span></span>|<span data-ttu-id="770b7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="770b7-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="770b7-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="770b7-113">S_OK</span></span>|<span data-ttu-id="770b7-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="770b7-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="770b7-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="770b7-115">E_POINTER</span></span>|<span data-ttu-id="770b7-116">`pszProcName` o `ppProc` è null.</span><span class="sxs-lookup"><span data-stu-id="770b7-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="770b7-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="770b7-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="770b7-118">La funzione specificata non è una funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="770b7-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="770b7-119">Note</span><span class="sxs-lookup"><span data-stu-id="770b7-119">Remarks</span></span>  
 <span data-ttu-id="770b7-120">Questo metodo fa sì che CLR venga caricato ma non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="770b7-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="770b7-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="770b7-121">Requirements</span></span>  
 <span data-ttu-id="770b7-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="770b7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="770b7-123">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="770b7-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="770b7-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="770b7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="770b7-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="770b7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="770b7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="770b7-126">See also</span></span>

- [<span data-ttu-id="770b7-127">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="770b7-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="770b7-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="770b7-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="770b7-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="770b7-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

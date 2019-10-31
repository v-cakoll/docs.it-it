---
title: Metodo ICLRRuntimeInfo::GetRuntimeDirectory
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: b0a2e5f259fe1ee566f9cc25152b2d2a1f740bea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120334"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="d5455-102">Metodo ICLRRuntimeInfo::GetRuntimeDirectory</span><span class="sxs-lookup"><span data-stu-id="d5455-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="d5455-103">Ottiene la directory di installazione del Common Language Runtime (CLR) associato a questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d5455-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="d5455-104">Questo metodo sostituisce la funzione [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) fornita in .NET Framework versioni 2,0, 3,0 e 3,5.</span><span class="sxs-lookup"><span data-stu-id="d5455-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5455-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5455-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5455-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5455-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="d5455-107">out Restituisce la directory di installazione CLR.</span><span class="sxs-lookup"><span data-stu-id="d5455-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="d5455-108">Il percorso di installazione è completo. ad esempio, "c:\Windows\Microsoft.net\framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="d5455-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="d5455-109">[in, out] Specifica le dimensioni del `pwzBuffer` per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="d5455-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="d5455-110">Se `pwzBuffer` è null, `pchBuffer` restituisce la dimensione richiesta di `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="d5455-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5455-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5455-111">Return Value</span></span>  
 <span data-ttu-id="d5455-112">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="d5455-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d5455-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5455-113">HRESULT</span></span>|<span data-ttu-id="d5455-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5455-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5455-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5455-115">S_OK</span></span>|<span data-ttu-id="d5455-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5455-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="d5455-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d5455-117">E_POINTER</span></span>|<span data-ttu-id="d5455-118">`pwzBuffer` o `pchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="d5455-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5455-119">Note</span><span class="sxs-lookup"><span data-stu-id="d5455-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5455-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5455-120">Requirements</span></span>  
 <span data-ttu-id="d5455-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5455-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5455-122">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d5455-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d5455-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d5455-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5455-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5455-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5455-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5455-125">See also</span></span>

- [<span data-ttu-id="d5455-126">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="d5455-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="d5455-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="d5455-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

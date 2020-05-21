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
ms.openlocfilehash: d744abf5c502e9b9510cf9fd6479149b6c2177cc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762214"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="f9ce0-102">Metodo ICLRRuntimeInfo::GetRuntimeDirectory</span><span class="sxs-lookup"><span data-stu-id="f9ce0-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="f9ce0-103">Ottiene la directory di installazione del Common Language Runtime (CLR) associato a questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f9ce0-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="f9ce0-104">Questo metodo sostituisce la funzione [GetCORSystemDirectory](getcorsystemdirectory-function.md) fornita in .NET Framework versioni 2,0, 3,0 e 3,5.</span><span class="sxs-lookup"><span data-stu-id="f9ce0-104">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9ce0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9ce0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9ce0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9ce0-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="f9ce0-107">out Restituisce la directory di installazione CLR.</span><span class="sxs-lookup"><span data-stu-id="f9ce0-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="f9ce0-108">Il percorso di installazione è completo. ad esempio, "c:\Windows\Microsoft.net\framework\v1.0.3705 \\ ".</span><span class="sxs-lookup"><span data-stu-id="f9ce0-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="f9ce0-109">[in, out] Specifica la dimensione di `pwzBuffer` per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="f9ce0-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="f9ce0-110">Se `pwzBuffer` è null, `pchBuffer` restituisce la dimensione richiesta di `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="f9ce0-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9ce0-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f9ce0-111">Return Value</span></span>  
 <span data-ttu-id="f9ce0-112">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="f9ce0-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f9ce0-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f9ce0-113">HRESULT</span></span>|<span data-ttu-id="f9ce0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9ce0-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f9ce0-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f9ce0-115">S_OK</span></span>|<span data-ttu-id="f9ce0-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f9ce0-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="f9ce0-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f9ce0-117">E_POINTER</span></span>|<span data-ttu-id="f9ce0-118">`pwzBuffer` o `pchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="f9ce0-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9ce0-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f9ce0-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9ce0-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9ce0-120">Requirements</span></span>  
 <span data-ttu-id="f9ce0-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9ce0-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9ce0-122">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f9ce0-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f9ce0-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f9ce0-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9ce0-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9ce0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ce0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9ce0-125">See also</span></span>

- [<span data-ttu-id="f9ce0-126">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="f9ce0-126">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f9ce0-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="f9ce0-127">Hosting</span></span>](index.md)

---
title: Metodo ICLRRuntimeInfo::LoadErrorString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: da6efae38cd70a68feea56b12e86be23fde7f0cb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762188"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="8f85f-102">Metodo ICLRRuntimeInfo::LoadErrorString</span><span class="sxs-lookup"><span data-stu-id="8f85f-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="8f85f-103">Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="8f85f-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="8f85f-104">Questo metodo sostituisce le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f85f-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="8f85f-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="8f85f-105">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="8f85f-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="8f85f-106">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="8f85f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f85f-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f85f-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f85f-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="8f85f-109">in HRESULT da tradurre.</span><span class="sxs-lookup"><span data-stu-id="8f85f-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="8f85f-110">out Stringa di messaggio associata al valore HRESULT specificato.</span><span class="sxs-lookup"><span data-stu-id="8f85f-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="8f85f-111">[in, out] Dimensioni di `pwzbuffer` per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="8f85f-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="8f85f-112">Se `pwzbuffer` è null, `pcchBuffer` fornisce le dimensioni previste di `pwzbuffer` per consentire la preallocazione.</span><span class="sxs-lookup"><span data-stu-id="8f85f-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="8f85f-113">in Identificatore delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="8f85f-113">[in] The culture identifier.</span></span> <span data-ttu-id="8f85f-114">Per utilizzare le impostazioni cultura predefinite, è necessario specificare-1.</span><span class="sxs-lookup"><span data-stu-id="8f85f-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f85f-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8f85f-115">Return Value</span></span>  
 <span data-ttu-id="8f85f-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="8f85f-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8f85f-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f85f-117">HRESULT</span></span>|<span data-ttu-id="8f85f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f85f-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f85f-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f85f-119">S_OK</span></span>|<span data-ttu-id="8f85f-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="8f85f-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="8f85f-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8f85f-121">E_POINTER</span></span>|<span data-ttu-id="8f85f-122">`pcchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="8f85f-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="8f85f-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8f85f-123">E_INVALIDARG</span></span>|<span data-ttu-id="8f85f-124">`pwzBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="8f85f-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f85f-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f85f-125">Requirements</span></span>  
 <span data-ttu-id="8f85f-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f85f-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f85f-127">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="8f85f-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8f85f-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8f85f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f85f-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f85f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f85f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f85f-130">See also</span></span>

- [<span data-ttu-id="8f85f-131">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="8f85f-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="8f85f-132">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="8f85f-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="8f85f-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="8f85f-133">Hosting</span></span>](index.md)

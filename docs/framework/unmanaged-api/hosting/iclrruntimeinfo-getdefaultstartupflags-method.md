---
title: Metodo ICLRRuntimeInfo::GetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: 8513787f48ae89632816face386bbcda20555dac
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703879"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="f114e-102">Metodo ICLRRuntimeInfo::GetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="f114e-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="f114e-103">Ottiene i flag di avvio e il file di configurazione host che verranno utilizzati per avviare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="f114e-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f114e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f114e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f114e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f114e-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="f114e-106">out Puntatore ai flag di avvio dell'host attualmente impostati.</span><span class="sxs-lookup"><span data-stu-id="f114e-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="f114e-107">out Puntatore al percorso della directory del file di configurazione dell'host corrente.</span><span class="sxs-lookup"><span data-stu-id="f114e-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="f114e-108">[in, out] In input, dimensione di `pwzHostConfigFile` , per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="f114e-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="f114e-109">Se `pwzHostConfigFile` è null, il metodo restituisce la dimensione richiesta di `pwzHostConfigFile` per la pre-allocazione.</span><span class="sxs-lookup"><span data-stu-id="f114e-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f114e-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f114e-110">Return Value</span></span>  
 <span data-ttu-id="f114e-111">Questo metodo restituisce il seguente HRESULT specifico, oltre a errori HRESULT che indicano un errore del metodo.</span><span class="sxs-lookup"><span data-stu-id="f114e-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f114e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f114e-112">HRESULT</span></span>|<span data-ttu-id="f114e-113">Description</span><span class="sxs-lookup"><span data-stu-id="f114e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f114e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f114e-114">S_OK</span></span>|<span data-ttu-id="f114e-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f114e-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f114e-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f114e-116">Remarks</span></span>  
 <span data-ttu-id="f114e-117">Questo metodo restituisce i valori dei flag predefiniti ( `STARTUP_CONCURRENT_GC` e `NULL` ) o i valori forniti da una chiamata precedente al [Metodo ICLRRuntimeInfo:: SetDefaultStartupFlags](iclrruntimeinfo-setdefaultstartupflags-method.md)o i valori impostati da uno dei `CorBind*` metodi se sono associati a questo runtime.</span><span class="sxs-lookup"><span data-stu-id="f114e-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f114e-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f114e-118">Requirements</span></span>  
 <span data-ttu-id="f114e-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f114e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f114e-120">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f114e-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f114e-121">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f114e-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f114e-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f114e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f114e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f114e-123">See also</span></span>

- [<span data-ttu-id="f114e-124">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="f114e-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f114e-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="f114e-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="f114e-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="f114e-126">Hosting</span></span>](index.md)

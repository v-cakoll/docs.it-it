---
title: Funzione GetRequestedRuntimeVersionForCLSID
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178107"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="4aedc-102">Funzione GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="4aedc-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="4aedc-103">Ottiene le informazioni sulla versione di Common Language Runtime `CLSID`(CLR) appropriate per la classe con l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="4aedc-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="4aedc-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4aedc-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aedc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4aedc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4aedc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4aedc-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="4aedc-107">[in]  Il `CLSID` del componente.</span><span class="sxs-lookup"><span data-stu-id="4aedc-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="4aedc-108">[fuori]  Un buffer che contiene la stringa del numero di versione al completamento.</span><span class="sxs-lookup"><span data-stu-id="4aedc-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="4aedc-109">[in]  Dimensione, in caratteri wide, `pVersion` del buffer.</span><span class="sxs-lookup"><span data-stu-id="4aedc-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="4aedc-110">[fuori] Lunghezza, in byte, del buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="4aedc-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="4aedc-111">[in]  Uno dei valori CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="4aedc-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="4aedc-112">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4aedc-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="4aedc-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifica che deve essere utilizzato il comportamento di interoperabilità predefinito.</span><span class="sxs-lookup"><span data-stu-id="4aedc-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="4aedc-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifica che la ricerca nel Registro di sistema deve essere eseguita e che devono essere applicati i criteri di shim.</span><span class="sxs-lookup"><span data-stu-id="4aedc-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4aedc-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4aedc-115">Return Value</span></span>  
  
|<span data-ttu-id="4aedc-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4aedc-116">HRESULT</span></span>|<span data-ttu-id="4aedc-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4aedc-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4aedc-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="4aedc-118">S_OK</span></span>|<span data-ttu-id="4aedc-119">La funzione restituita correttamente.</span><span class="sxs-lookup"><span data-stu-id="4aedc-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="4aedc-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4aedc-120">E_INVALIDARG</span></span>|<span data-ttu-id="4aedc-121">Uno dei parametri ha un tipo o un formato non valido.</span><span class="sxs-lookup"><span data-stu-id="4aedc-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="4aedc-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4aedc-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4aedc-123">Il `pVersion` buffer non è sufficientemente grande per contenere l'intera stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="4aedc-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="4aedc-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="4aedc-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="4aedc-125">Nessuna classe registrata con `CLSID`l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="4aedc-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="4aedc-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4aedc-126">E_POINTER</span></span>|<span data-ttu-id="4aedc-127">`dwLength`è null, `cchBuffer` o è abbastanza grande per `pVersion` contenere la stringa di versione, ma è null.</span><span class="sxs-lookup"><span data-stu-id="4aedc-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4aedc-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4aedc-128">Requirements</span></span>  
 <span data-ttu-id="4aedc-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aedc-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aedc-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4aedc-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4aedc-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aedc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aedc-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4aedc-132">See also</span></span>

- [<span data-ttu-id="4aedc-133">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="4aedc-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

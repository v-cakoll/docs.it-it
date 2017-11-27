---
title: Funzione GetRequestedRuntimeVersionForCLSID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersionForCLSID
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersionForCLSID
helpviewer_keywords: GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a5b9e4b186b6c9b91c1182e8700268f0e1c038f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="917e6-102">Funzione GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="917e6-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="917e6-103">Ottiene le informazioni sulla versione di common language runtime (CLR) appropriato per la classe con l'oggetto specificato `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="917e6-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="917e6-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="917e6-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="917e6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="917e6-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="917e6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="917e6-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="917e6-107">[in]  Il `CLSID` del componente.</span><span class="sxs-lookup"><span data-stu-id="917e6-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="917e6-108">[out]  Un buffer che contiene la stringa del numero di versione al completamento.</span><span class="sxs-lookup"><span data-stu-id="917e6-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="917e6-109">[in]  Le dimensioni, in caratteri wide, del `pVersion` buffer.</span><span class="sxs-lookup"><span data-stu-id="917e6-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="917e6-110">[out] La lunghezza, espressa in byte, del buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="917e6-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="917e6-111">[in]  Uno dei valori di CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="917e6-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="917e6-112">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="917e6-112">The following values are supported:</span></span>  
  
-   <span data-ttu-id="917e6-113">CLSID_RESOLUTION_DEFAULT: (0x0) specifica il comportamento di interoperabilità predefinito deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="917e6-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
-   <span data-ttu-id="917e6-114">CLSID_RESOLUTION_REGISTERED: (0x1) specifica che il Registro di sistema deve essere eseguita e criteri di shim deve essere applicato.</span><span class="sxs-lookup"><span data-stu-id="917e6-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="917e6-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="917e6-115">Return Value</span></span>  
  
|<span data-ttu-id="917e6-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="917e6-116">HRESULT</span></span>|<span data-ttu-id="917e6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="917e6-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="917e6-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="917e6-118">S_OK</span></span>|<span data-ttu-id="917e6-119">La funzione ha restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="917e6-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="917e6-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="917e6-120">E_INVALIDARG</span></span>|<span data-ttu-id="917e6-121">Uno dei parametri contiene un formato o tipo non valido.</span><span class="sxs-lookup"><span data-stu-id="917e6-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="917e6-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="917e6-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="917e6-123">Il `pVersion` buffer non è sufficientemente grande da contenere l'intera stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="917e6-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="917e6-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="917e6-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="917e6-125">Nessuna classe registrata con l'oggetto specificato `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="917e6-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="917e6-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="917e6-126">E_POINTER</span></span>|<span data-ttu-id="917e6-127">`dwLength`è null, o `cchBuffer` è sufficientemente grande da contenere la stringa di versione, ma `pVersion` è null.</span><span class="sxs-lookup"><span data-stu-id="917e6-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="917e6-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="917e6-128">Requirements</span></span>  
 <span data-ttu-id="917e6-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="917e6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="917e6-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="917e6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="917e6-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="917e6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="917e6-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="917e6-132">See Also</span></span>  
 [<span data-ttu-id="917e6-133">Funzioni di Hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="917e6-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

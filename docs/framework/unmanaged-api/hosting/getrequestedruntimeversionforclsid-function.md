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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b4ac1a37c2b3506216499ed0c9f8194949b768
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081892"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="8602a-102">Funzione GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="8602a-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="8602a-103">Ottiene le informazioni sulla versione di common language runtime (CLR) appropriata per la classe con l'oggetto specificato `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="8602a-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="8602a-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8602a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8602a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8602a-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8602a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8602a-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="8602a-107">[in]  Il `CLSID` del componente.</span><span class="sxs-lookup"><span data-stu-id="8602a-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="8602a-108">[out]  Un buffer che contiene la stringa del numero di versione al completamento.</span><span class="sxs-lookup"><span data-stu-id="8602a-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="8602a-109">[in]  Le dimensioni, in caratteri "wide", del `pVersion` buffer.</span><span class="sxs-lookup"><span data-stu-id="8602a-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="8602a-110">[out] La lunghezza, espressa in byte, del buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="8602a-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="8602a-111">[in]  Uno dei valori CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="8602a-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="8602a-112">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8602a-112">The following values are supported:</span></span>  
  
-   <span data-ttu-id="8602a-113">CLSID_RESOLUTION_DEFAULT: (0x0) specifica che deve essere utilizzato il comportamento predefinito di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="8602a-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
-   <span data-ttu-id="8602a-114">CLSID_RESOLUTION_REGISTERED: (0x1) consente di specificare che deve essere ricercato nel Registro di sistema e devono essere applicati criteri shim.</span><span class="sxs-lookup"><span data-stu-id="8602a-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8602a-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8602a-115">Return Value</span></span>  
  
|<span data-ttu-id="8602a-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8602a-116">HRESULT</span></span>|<span data-ttu-id="8602a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8602a-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8602a-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="8602a-118">S_OK</span></span>|<span data-ttu-id="8602a-119">La funzione ha restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8602a-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="8602a-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8602a-120">E_INVALIDARG</span></span>|<span data-ttu-id="8602a-121">Uno dei parametri è un formato o tipo non valido.</span><span class="sxs-lookup"><span data-stu-id="8602a-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="8602a-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="8602a-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="8602a-123">Il `pVersion` buffer non è sufficientemente grande da contenere l'intera stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="8602a-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="8602a-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="8602a-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="8602a-125">Nessuna classe registrata con l'oggetto specificato `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="8602a-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="8602a-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8602a-126">E_POINTER</span></span>|`dwLength` <span data-ttu-id="8602a-127">è null, o `cchBuffer` sia abbastanza grande da contenere la stringa di versione, ma `pVersion` è null.</span><span class="sxs-lookup"><span data-stu-id="8602a-127">is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8602a-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8602a-128">Requirements</span></span>  
 <span data-ttu-id="8602a-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8602a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8602a-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8602a-130">**Header:** MSCorEE.h</span></span>  
  
 **<span data-ttu-id="8602a-131">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8602a-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8602a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8602a-132">See also</span></span>

- [<span data-ttu-id="8602a-133">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="8602a-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

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
ms.openlocfilehash: ce0c6307defd93dcf63ac4e9051fc798041475f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127049"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="c80f8-102">Funzione GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="c80f8-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="c80f8-103">Ottiene le informazioni sulla versione di Common Language Runtime (CLR) appropriate per la classe con la `CLSID`specificata.</span><span class="sxs-lookup"><span data-stu-id="c80f8-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="c80f8-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c80f8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c80f8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c80f8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c80f8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c80f8-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="c80f8-107">in  `CLSID` del componente.</span><span class="sxs-lookup"><span data-stu-id="c80f8-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="c80f8-108">out  Buffer che contiene la stringa del numero di versione al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="c80f8-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="c80f8-109">in  Dimensione, in caratteri wide, del buffer `pVersion`.</span><span class="sxs-lookup"><span data-stu-id="c80f8-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="c80f8-110">out Lunghezza, in byte, del buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="c80f8-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="c80f8-111">in  Uno dei valori CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="c80f8-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="c80f8-112">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c80f8-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="c80f8-113">CLSID_RESOLUTION_DEFAULT: (0x0) specifica che deve essere utilizzato il comportamento di interoperabilità predefinito.</span><span class="sxs-lookup"><span data-stu-id="c80f8-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="c80f8-114">CLSID_RESOLUTION_REGISTERED: (0x1) specifica che deve essere eseguita la ricerca nel registro di sistema e applicare i criteri shim.</span><span class="sxs-lookup"><span data-stu-id="c80f8-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c80f8-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c80f8-115">Return Value</span></span>  
  
|<span data-ttu-id="c80f8-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c80f8-116">HRESULT</span></span>|<span data-ttu-id="c80f8-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c80f8-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c80f8-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c80f8-118">S_OK</span></span>|<span data-ttu-id="c80f8-119">La funzione ha restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c80f8-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="c80f8-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c80f8-120">E_INVALIDARG</span></span>|<span data-ttu-id="c80f8-121">Il tipo o il formato di uno dei parametri non è valido.</span><span class="sxs-lookup"><span data-stu-id="c80f8-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="c80f8-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="c80f8-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="c80f8-123">Il buffer di `pVersion` non è sufficientemente grande da mantenere l'intera stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="c80f8-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="c80f8-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="c80f8-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="c80f8-125">Non è stata registrata alcuna classe con la `CLSID`specificata.</span><span class="sxs-lookup"><span data-stu-id="c80f8-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="c80f8-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c80f8-126">E_POINTER</span></span>|<span data-ttu-id="c80f8-127">`dwLength` è null o `cchBuffer` è sufficientemente grande per poter essere contenuta nella stringa di versione, ma `pVersion` è null.</span><span class="sxs-lookup"><span data-stu-id="c80f8-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c80f8-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c80f8-128">Requirements</span></span>  
 <span data-ttu-id="c80f8-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c80f8-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c80f8-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c80f8-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c80f8-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c80f8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80f8-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c80f8-132">See also</span></span>

- [<span data-ttu-id="c80f8-133">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="c80f8-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

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
ms.openlocfilehash: 899d6e74902e47f1f41b849bd5c25048baa175f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617139"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="e8de0-102">Funzione GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="e8de0-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="e8de0-103">Ottiene le informazioni sulla versione di Common Language Runtime (CLR) appropriate per la classe con l'oggetto specificato `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="e8de0-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="e8de0-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e8de0-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8de0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8de0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8de0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8de0-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="e8de0-107">in  Oggetto `CLSID` del componente.</span><span class="sxs-lookup"><span data-stu-id="e8de0-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="e8de0-108">out  Buffer che contiene la stringa del numero di versione al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e8de0-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="e8de0-109">in  Dimensione, in caratteri wide, del `pVersion` buffer.</span><span class="sxs-lookup"><span data-stu-id="e8de0-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e8de0-110">out Lunghezza, in byte, del buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="e8de0-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="e8de0-111">in  Uno dei valori di CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="e8de0-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="e8de0-112">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8de0-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="e8de0-113">CLSID_RESOLUTION_DEFAULT: (0x0) specifica che deve essere utilizzato il comportamento di interoperabilità predefinito.</span><span class="sxs-lookup"><span data-stu-id="e8de0-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="e8de0-114">CLSID_RESOLUTION_REGISTERED: (0x1) specifica che deve essere eseguita la ricerca nel registro di sistema e applicare i criteri shim.</span><span class="sxs-lookup"><span data-stu-id="e8de0-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8de0-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e8de0-115">Return Value</span></span>  
  
|<span data-ttu-id="e8de0-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8de0-116">HRESULT</span></span>|<span data-ttu-id="e8de0-117">Description</span><span class="sxs-lookup"><span data-stu-id="e8de0-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e8de0-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8de0-118">S_OK</span></span>|<span data-ttu-id="e8de0-119">La funzione ha restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e8de0-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="e8de0-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e8de0-120">E_INVALIDARG</span></span>|<span data-ttu-id="e8de0-121">Il tipo o il formato di uno dei parametri non è valido.</span><span class="sxs-lookup"><span data-stu-id="e8de0-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="e8de0-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e8de0-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e8de0-123">Il `pVersion` buffer non è sufficientemente grande da mantenere l'intera stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="e8de0-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="e8de0-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="e8de0-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="e8de0-125">Non è stata registrata alcuna classe con l'oggetto specificato `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="e8de0-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="e8de0-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e8de0-126">E_POINTER</span></span>|<span data-ttu-id="e8de0-127">`dwLength`è null o `cchBuffer` è sufficientemente grande per poter essere contenuta nella stringa di versione, ma `pVersion` è null.</span><span class="sxs-lookup"><span data-stu-id="e8de0-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8de0-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8de0-128">Requirements</span></span>  
 <span data-ttu-id="e8de0-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8de0-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8de0-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e8de0-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8de0-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8de0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8de0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8de0-132">See also</span></span>

- [<span data-ttu-id="e8de0-133">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="e8de0-133">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

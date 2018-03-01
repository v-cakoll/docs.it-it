---
title: Funzione CreateDebuggingInterfaceFromVersion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b3f269f5b1758481995d6064e7137e62bff4a868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="7f35e-102">Funzione CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="7f35e-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="7f35e-103">Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) oggetto in base alle informazioni di versione specificata.</span><span class="sxs-lookup"><span data-stu-id="7f35e-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="7f35e-104">Questa funzione è obsoleta nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f35e-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="7f35e-105">Per ottenere un'interfaccia per common language runtime (CLR) 2.0, usare invece il [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) (metodo) e specificare l'identificatore di classe CLSID_CLRDebuggingLegacy e l'identificatore di interfaccia IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="7f35e-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="7f35e-106">Per ottenere un'interfaccia per 4 di CLR o in un secondo momento, chiamare il [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funzione e specificare l'identificatore di classe CLSID_CLRDebugging e l'identificatore di interfaccia IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="7f35e-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f35e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f35e-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f35e-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f35e-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="7f35e-109">[in] La versione di `ICorDebug` prevista dal debugger.</span><span class="sxs-lookup"><span data-stu-id="7f35e-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="7f35e-110">Vedere il [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumerazione per i valori validi.</span><span class="sxs-lookup"><span data-stu-id="7f35e-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="7f35e-111">[in] La versione common language runtime associata con l'applicazione o il processo di cui eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="7f35e-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="7f35e-112">Vedere il [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) metodo per informazioni su come recuperare questo valore.</span><span class="sxs-lookup"><span data-stu-id="7f35e-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="7f35e-113">[out] La posizione che riceve un puntatore di `ICorDebug` oggetto.</span><span class="sxs-lookup"><span data-stu-id="7f35e-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f35e-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7f35e-114">Return Value</span></span>  
 <span data-ttu-id="7f35e-115">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="7f35e-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="7f35e-116">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="7f35e-116">Return code</span></span>|<span data-ttu-id="7f35e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f35e-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7f35e-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f35e-118">S_OK</span></span>|<span data-ttu-id="7f35e-119">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7f35e-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="7f35e-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7f35e-120">E_INVALIDARG</span></span>|<span data-ttu-id="7f35e-121">`szDebuggeeVersion`o `ppCordb` è null o la versione stringa non è corretta.</span><span class="sxs-lookup"><span data-stu-id="7f35e-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f35e-122">Note</span><span class="sxs-lookup"><span data-stu-id="7f35e-122">Remarks</span></span>  
 <span data-ttu-id="7f35e-123">Il `szDebuggeeVersion` esegue il mapping di parametro per la versione corrispondente di MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="7f35e-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f35e-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f35e-124">Requirements</span></span>  
 <span data-ttu-id="7f35e-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f35e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f35e-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7f35e-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f35e-127">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7f35e-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f35e-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f35e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f35e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f35e-129">See Also</span></span>  
 [<span data-ttu-id="7f35e-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="7f35e-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

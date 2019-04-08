---
title: Funzione CreateDebuggingInterfaceFromVersion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60d1c49e8762d00e3e154c598c2542c4a76b9b28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107497"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="903e4-102">Funzione CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="903e4-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="903e4-103">Crea un' [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) oggetto basata sulle informazioni versione specificata.</span><span class="sxs-lookup"><span data-stu-id="903e4-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="903e4-104">Questa funzione è obsoleta nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="903e4-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="903e4-105">Per ottenere un'interfaccia per common language runtime (CLR) 2.0, usare invece i [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) (metodo) e specificare l'identificatore di classe CLSID_CLRDebuggingLegacy e l'identificatore di interfaccia IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="903e4-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="903e4-106">Per ottenere un'interfaccia per CLR 4 o versioni successive, chiamare il [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funzione e specificare l'identificatore di classe CLSID_CLRDebugging e l'identificatore di interfaccia IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="903e4-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903e4-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="903e4-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="903e4-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="903e4-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="903e4-109">[in] La versione di `ICorDebug` che è previsto dal debugger.</span><span class="sxs-lookup"><span data-stu-id="903e4-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="903e4-110">Vedere le [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumerazione per i valori validi.</span><span class="sxs-lookup"><span data-stu-id="903e4-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="903e4-111">[in] La versione common language runtime associata con l'applicazione o il processo di cui eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="903e4-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="903e4-112">Vedere le [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) oppure [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) metodo per informazioni su come recuperare questo valore.</span><span class="sxs-lookup"><span data-stu-id="903e4-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="903e4-113">[out] La posizione che riceve un puntatore al `ICorDebug` oggetto.</span><span class="sxs-lookup"><span data-stu-id="903e4-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="903e4-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="903e4-114">Return Value</span></span>  
 <span data-ttu-id="903e4-115">Questo metodo restituisce i codici di errore COM standard, come definito nel file Winerror h oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="903e4-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="903e4-116">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="903e4-116">Return code</span></span>|<span data-ttu-id="903e4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="903e4-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="903e4-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="903e4-118">S_OK</span></span>|<span data-ttu-id="903e4-119">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="903e4-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="903e4-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="903e4-120">E_INVALIDARG</span></span>|`szDebuggeeVersion` <span data-ttu-id="903e4-121">o `ppCordb` è null o una versione stringa non è corretta.</span><span class="sxs-lookup"><span data-stu-id="903e4-121">or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="903e4-122">Note</span><span class="sxs-lookup"><span data-stu-id="903e4-122">Remarks</span></span>  
 <span data-ttu-id="903e4-123">Il `szDebuggeeVersion` parametro esegue il mapping alla versione corrispondente di mscordbi. dll.</span><span class="sxs-lookup"><span data-stu-id="903e4-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="903e4-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="903e4-124">Requirements</span></span>  
 <span data-ttu-id="903e4-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="903e4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="903e4-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="903e4-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="903e4-127">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="903e4-127">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="903e4-128">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="903e4-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="903e4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="903e4-129">See also</span></span>

- [<span data-ttu-id="903e4-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="903e4-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

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
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176448"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="776c1-102">Funzione CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="776c1-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="776c1-103">Crea un [oggetto ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) in base alle informazioni sulla versione specificate.</span><span class="sxs-lookup"><span data-stu-id="776c1-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="776c1-104">Questa funzione è obsoleta in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="776c1-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="776c1-105">Al contrario, per ottenere un'interfaccia per Common Language Runtime (CLR) 2.0, utilizzare il [metodo ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) e specificare l'identificatore di classe CLSID_CLRDebuggingLegacy e l'identificatore di interfaccia IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="776c1-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="776c1-106">Per ottenere un'interfaccia per CLR 4 o versione successiva, chiamare la funzione [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) e specificare l'identificatore di classe CLSID_CLRDebugging e l'identificatore di interfaccia IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="776c1-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="776c1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="776c1-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="776c1-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="776c1-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="776c1-109">[in] La versione `ICorDebug` di che è previsto dal debugger.</span><span class="sxs-lookup"><span data-stu-id="776c1-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="776c1-110">Vedere il [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumerazione per i valori validi.</span><span class="sxs-lookup"><span data-stu-id="776c1-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="776c1-111">[in] Versione di Common Language Runtime associata all'applicazione o al processo di cui eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="776c1-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="776c1-112">Vedere il [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) metodo per informazioni sul recupero di questo valore.</span><span class="sxs-lookup"><span data-stu-id="776c1-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="776c1-113">[fuori] Posizione che riceve un puntatore all'oggetto. `ICorDebug`</span><span class="sxs-lookup"><span data-stu-id="776c1-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="776c1-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="776c1-114">Return Value</span></span>  
 <span data-ttu-id="776c1-115">Questo metodo restituisce codici di errore COM standard come definito nel file WinError.h oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="776c1-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="776c1-116">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="776c1-116">Return code</span></span>|<span data-ttu-id="776c1-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="776c1-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="776c1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="776c1-118">S_OK</span></span>|<span data-ttu-id="776c1-119">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="776c1-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="776c1-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="776c1-120">E_INVALIDARG</span></span>|<span data-ttu-id="776c1-121">`szDebuggeeVersion`o `ppCordb` è null o la stringa di versione non è corretta.</span><span class="sxs-lookup"><span data-stu-id="776c1-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="776c1-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="776c1-122">Remarks</span></span>  
 <span data-ttu-id="776c1-123">Il `szDebuggeeVersion` parametro esegue il mapping alla versione corrispondente di MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="776c1-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="776c1-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="776c1-124">Requirements</span></span>  
 <span data-ttu-id="776c1-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="776c1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="776c1-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="776c1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="776c1-127">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="776c1-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="776c1-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="776c1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776c1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="776c1-129">See also</span></span>

- [<span data-ttu-id="776c1-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="776c1-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

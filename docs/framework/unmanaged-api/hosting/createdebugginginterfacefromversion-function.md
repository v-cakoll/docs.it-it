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
ms.openlocfilehash: 6f5eec282aec6a2757664023ce8031410e316f10
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501846"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="18f01-102">Funzione CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="18f01-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="18f01-103">Crea un oggetto [ICorDebug](../debugging/icordebug-interface.md) in base alle informazioni sulla versione specificate.</span><span class="sxs-lookup"><span data-stu-id="18f01-103">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="18f01-104">Questa funzione è obsoleta in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="18f01-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="18f01-105">Per ottenere un'interfaccia per il Common Language Runtime (CLR) 2,0, usare invece il metodo [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) e specificare l'identificatore di classe CLSID_CLRDebuggingLegacy e l'identificatore di interfaccia IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="18f01-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="18f01-106">Per ottenere un'interfaccia per CLR 4 o versione successiva, chiamare la funzione [CLRCreateInstance](clrcreateinstance-function.md) e specificare l'identificatore di classe CLSID_CLRDebugging e l'identificatore di interfaccia IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="18f01-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f01-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18f01-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18f01-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="18f01-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="18f01-109">in Versione di `ICorDebug` prevista dal debugger.</span><span class="sxs-lookup"><span data-stu-id="18f01-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="18f01-110">Per i valori validi, vedere l'enumerazione [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="18f01-110">See the [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="18f01-111">in Versione Common Language Runtime associata all'applicazione o al processo di cui eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="18f01-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="18f01-112">Per informazioni sul recupero di questo valore, vedere il metodo [GetVersionFromProcess](getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="18f01-112">See the [GetVersionFromProcess](getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="18f01-113">out Posizione che riceve un puntatore all' `ICorDebug` oggetto.</span><span class="sxs-lookup"><span data-stu-id="18f01-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18f01-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="18f01-114">Return Value</span></span>  
 <span data-ttu-id="18f01-115">Questo metodo restituisce i codici di errore COM standard come definito nel file WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="18f01-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="18f01-116">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="18f01-116">Return code</span></span>|<span data-ttu-id="18f01-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18f01-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="18f01-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="18f01-118">S_OK</span></span>|<span data-ttu-id="18f01-119">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="18f01-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="18f01-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="18f01-120">E_INVALIDARG</span></span>|<span data-ttu-id="18f01-121">`szDebuggeeVersion`o `ppCordb` è null oppure la stringa di versione non è corretta.</span><span class="sxs-lookup"><span data-stu-id="18f01-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18f01-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="18f01-122">Remarks</span></span>  
 <span data-ttu-id="18f01-123">Il `szDebuggeeVersion` parametro esegue il mapping alla versione corrispondente di mscordbi. dll.</span><span class="sxs-lookup"><span data-stu-id="18f01-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f01-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18f01-124">Requirements</span></span>  
 <span data-ttu-id="18f01-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18f01-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f01-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="18f01-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="18f01-127">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="18f01-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18f01-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f01-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f01-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18f01-129">See also</span></span>

- [<span data-ttu-id="18f01-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="18f01-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

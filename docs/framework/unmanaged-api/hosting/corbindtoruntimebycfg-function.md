---
title: Funzione CorBindToRuntimeByCfg
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: 3802354bf52cd2aab2a4149d565993b9965e8312
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138291"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="99029-102">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="99029-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="99029-103">Carica il Common Language Runtime (CLR) in un processo utilizzando le informazioni sulla versione lette da un file XML.</span><span class="sxs-lookup"><span data-stu-id="99029-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="99029-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="99029-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99029-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99029-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99029-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="99029-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="99029-107">in Puntatore a un oggetto `IStream` che legge il file XML.</span><span class="sxs-lookup"><span data-stu-id="99029-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="99029-108">in Riservato per usi futuri.</span><span class="sxs-lookup"><span data-stu-id="99029-108">[in] Reserved for future use.</span></span> <span data-ttu-id="99029-109">Usare 0 (zero) come valore.</span><span class="sxs-lookup"><span data-stu-id="99029-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="99029-110">in Valore dell'enumerazione [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) che specifica il comportamento di avvio di CLR.</span><span class="sxs-lookup"><span data-stu-id="99029-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="99029-111">in `CLSID` della coclasse che implementa l'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="99029-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="99029-112">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="99029-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="99029-113">in `IID` dell'interfaccia `ICorRuntimeHost` o `ICLRRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="99029-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="99029-114">I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="99029-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="99029-115">out Puntatore all'indirizzo dell'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="99029-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99029-116">Note</span><span class="sxs-lookup"><span data-stu-id="99029-116">Remarks</span></span>  
 <span data-ttu-id="99029-117">Il formato del file XML viene modellato dopo il file di configurazione dell'applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="99029-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="99029-118">Per ulteriori informazioni sui file XML, vedere [schema del file di configurazione](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="99029-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99029-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99029-119">Requirements</span></span>  
 <span data-ttu-id="99029-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99029-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99029-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="99029-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99029-122">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="99029-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99029-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99029-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99029-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99029-124">See also</span></span>

- [<span data-ttu-id="99029-125">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="99029-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="99029-126">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="99029-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="99029-127">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="99029-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="99029-128">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="99029-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="99029-129">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="99029-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="99029-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="99029-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

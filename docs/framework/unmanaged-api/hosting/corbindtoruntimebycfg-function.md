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
ms.openlocfilehash: 9326484c6a9f96d245e3c61a0ac3e3465a8a6dcd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616645"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="01a48-102">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="01a48-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="01a48-103">Carica il Common Language Runtime (CLR) in un processo utilizzando le informazioni sulla versione lette da un file XML.</span><span class="sxs-lookup"><span data-stu-id="01a48-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="01a48-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="01a48-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a48-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01a48-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="01a48-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="01a48-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="01a48-107">in Puntatore a un `IStream` oggetto che legge il file XML.</span><span class="sxs-lookup"><span data-stu-id="01a48-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="01a48-108">[in] Riservato per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="01a48-108">[in] Reserved for future use.</span></span> <span data-ttu-id="01a48-109">Usare 0 (zero) come valore.</span><span class="sxs-lookup"><span data-stu-id="01a48-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="01a48-110">in Valore dell'enumerazione [STARTUP_FLAGS](startup-flags-enumeration.md) che specifica il comportamento di avvio di CLR.</span><span class="sxs-lookup"><span data-stu-id="01a48-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="01a48-111">in `CLSID`Della coclasse che implementa l'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="01a48-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="01a48-112">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="01a48-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="01a48-113">in Oggetto `IID` dell' `ICorRuntimeHost` `ICLRRuntimeHost` interfaccia o.</span><span class="sxs-lookup"><span data-stu-id="01a48-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="01a48-114">I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="01a48-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="01a48-115">out Puntatore all'indirizzo dell'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="01a48-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01a48-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="01a48-116">Remarks</span></span>  
 <span data-ttu-id="01a48-117">Il formato del file XML viene modellato dopo il file di configurazione dell'applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="01a48-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="01a48-118">Per ulteriori informazioni sui file XML, vedere [schema del file di configurazione](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="01a48-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01a48-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01a48-119">Requirements</span></span>  
 <span data-ttu-id="01a48-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01a48-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01a48-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="01a48-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01a48-122">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="01a48-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01a48-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01a48-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a48-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01a48-124">See also</span></span>

- [<span data-ttu-id="01a48-125">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="01a48-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="01a48-126">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="01a48-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="01a48-127">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="01a48-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="01a48-128">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="01a48-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="01a48-129">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="01a48-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="01a48-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="01a48-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

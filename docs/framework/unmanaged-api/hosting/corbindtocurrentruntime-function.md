---
title: Funzione CorBindToCurrentRuntime
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
ms.openlocfilehash: 77a0a8f58c11673a1958d837b4c3a21a05754c94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138325"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="3264b-102">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="3264b-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="3264b-103">Carica il Common Language Runtime (CLR) in un processo utilizzando le informazioni sulla versione archiviate in un file XML.</span><span class="sxs-lookup"><span data-stu-id="3264b-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="3264b-104">Il formato del file XML viene modellato dopo il file di configurazione dell'applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="3264b-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="3264b-105">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="3264b-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="3264b-106">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3264b-106">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="3264b-107">Vedere [caricamento di Common Language Runtime in un processo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3264b-107">See [Loading the Common Language Runtime into a Process](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3264b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3264b-108">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3264b-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="3264b-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="3264b-110">in Nome di un file di configurazione dell'applicazione che specifica la versione di CLR da caricare.</span><span class="sxs-lookup"><span data-stu-id="3264b-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="3264b-111">Se il nome del file non è completo, si presuppone che si trovi nella stessa directory del file eseguibile che effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3264b-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="3264b-112">La versione del runtime da caricare è descritta dall'attributo Version nell'elemento [\<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3264b-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="3264b-113">Se non viene specificata alcuna versione o se non è possibile trovare l'elemento `<requiredRuntime>`, viene caricata la versione più recente di CLR installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="3264b-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="3264b-114">in `CLSID` della coclasse che implementa l'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3264b-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="3264b-115">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="3264b-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="3264b-116">in `IID` dell'interfaccia richiesta.</span><span class="sxs-lookup"><span data-stu-id="3264b-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="3264b-117">I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="3264b-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="3264b-118">out Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="3264b-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3264b-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3264b-119">Requirements</span></span>  
 <span data-ttu-id="3264b-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3264b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3264b-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3264b-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3264b-122">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3264b-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3264b-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3264b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3264b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3264b-124">See also</span></span>

- [<span data-ttu-id="3264b-125">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="3264b-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="3264b-126">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="3264b-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="3264b-127">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="3264b-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="3264b-128">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3264b-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="3264b-129">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3264b-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="3264b-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="3264b-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

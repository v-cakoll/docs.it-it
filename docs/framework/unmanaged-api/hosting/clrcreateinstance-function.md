---
title: Funzione CLRCreateInstance
ms.date: 03/30/2017
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
ms.openlocfilehash: c3011149b9b23e776ad3baac9e41f3c42213654d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616827"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="62d4b-102">Funzione CLRCreateInstance</span><span class="sxs-lookup"><span data-stu-id="62d4b-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="62d4b-103">Fornisce una delle tre interfacce seguenti: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="62d4b-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62d4b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62d4b-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62d4b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="62d4b-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="62d4b-106">in Uno dei tre identificatori di classe: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="62d4b-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="62d4b-107">in Uno dei tre identificatori di interfaccia (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="62d4b-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="62d4b-108">out Una delle tre interfacce seguenti: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="62d4b-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62d4b-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="62d4b-109">Return Value</span></span>  
 <span data-ttu-id="62d4b-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="62d4b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="62d4b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62d4b-111">HRESULT</span></span>|<span data-ttu-id="62d4b-112">Description</span><span class="sxs-lookup"><span data-stu-id="62d4b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62d4b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="62d4b-113">S_OK</span></span>|<span data-ttu-id="62d4b-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="62d4b-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="62d4b-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="62d4b-115">E_POINTER</span></span>|<span data-ttu-id="62d4b-116">`ppInterface` è null.</span><span class="sxs-lookup"><span data-stu-id="62d4b-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62d4b-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="62d4b-117">Remarks</span></span>  
 <span data-ttu-id="62d4b-118">Nella tabella seguente vengono illustrate le combinazioni supportate per `clsid` e `riid` .</span><span class="sxs-lookup"><span data-stu-id="62d4b-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="62d4b-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="62d4b-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="62d4b-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="62d4b-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="62d4b-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="62d4b-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="62d4b-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="62d4b-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="62d4b-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="62d4b-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="62d4b-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="62d4b-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="62d4b-125">Il codice seguente illustra come usare `CLRCreateInstance` per ottenere tutte e tre le interfacce:</span><span class="sxs-lookup"><span data-stu-id="62d4b-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```cpp  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a><span data-ttu-id="62d4b-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62d4b-126">Requirements</span></span>  
 <span data-ttu-id="62d4b-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62d4b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d4b-128">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="62d4b-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="62d4b-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62d4b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62d4b-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d4b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d4b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62d4b-131">See also</span></span>

- [<span data-ttu-id="62d4b-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="62d4b-132">Hosting</span></span>](index.md)

---
title: Funzione CorLaunchApplication
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a53b0a9cdcec33846f9d491e7d6567bcf9235b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428762"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="b6373-102">Funzione CorLaunchApplication</span><span class="sxs-lookup"><span data-stu-id="b6373-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="b6373-103">Avvia l'applicazione in corrispondenza del percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b6373-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="b6373-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6373-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6373-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6373-105">Syntax</span></span>  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6373-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6373-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="b6373-107">[in] Il valore di [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumerazione che specifica il tipo di host che sta avviando l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b6373-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="b6373-108">[in] Il nome completo dell'applicazione che si sta avviando.</span><span class="sxs-lookup"><span data-stu-id="b6373-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="b6373-109">[in] Il numero di percorsi di manifesto per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b6373-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="b6373-110">[in] Matrice di stringhe, ognuna delle quali specifica un percorso di un manifesto dell'applicazione che si sta avviando.</span><span class="sxs-lookup"><span data-stu-id="b6373-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="b6373-111">[in] Il numero di elementi di dati di attivazione per l'applicazione che si sta avviando.</span><span class="sxs-lookup"><span data-stu-id="b6373-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="b6373-112">[in] Matrice di stringhe, ognuna delle quali è un elemento di dati di attivazione per l'applicazione che si sta avviando.</span><span class="sxs-lookup"><span data-stu-id="b6373-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="b6373-113">[out] Puntatore alle informazioni sul processo in cui è stata caricata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b6373-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6373-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6373-114">Requirements</span></span>  
 <span data-ttu-id="b6373-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6373-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6373-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="b6373-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6373-117">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b6373-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6373-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6373-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6373-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6373-119">See Also</span></span>  
 [<span data-ttu-id="b6373-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="b6373-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

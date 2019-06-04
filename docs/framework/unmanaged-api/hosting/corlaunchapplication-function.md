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
ms.openlocfilehash: 64527221e81569bf08a3cfd34a66681725755a55
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490533"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="20b0b-102">Funzione CorLaunchApplication</span><span class="sxs-lookup"><span data-stu-id="20b0b-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="20b0b-103">Avvia l'applicazione nel percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="20b0b-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="20b0b-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="20b0b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20b0b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20b0b-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="20b0b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="20b0b-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="20b0b-107">[in] Valore di [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumerazione che specifica il tipo di host che è l'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="20b0b-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="20b0b-108">[in] Il nome completo dell'applicazione in corso di avvio.</span><span class="sxs-lookup"><span data-stu-id="20b0b-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="20b0b-109">[in] Il numero di percorsi di manifesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="20b0b-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="20b0b-110">[in] Matrice di stringhe, ognuna delle quali specifica un percorso di un manifesto dell'applicazione in corso di avvio.</span><span class="sxs-lookup"><span data-stu-id="20b0b-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="20b0b-111">[in] Il numero di elementi di dati di attivazione per l'applicazione in corso di avvio.</span><span class="sxs-lookup"><span data-stu-id="20b0b-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="20b0b-112">[in] Matrice di stringhe, ognuna delle quali è un elemento di dati di attivazione per l'applicazione in corso di avvio.</span><span class="sxs-lookup"><span data-stu-id="20b0b-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="20b0b-113">[out] Puntatore alle informazioni sul processo in cui è stata caricata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="20b0b-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20b0b-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20b0b-114">Requirements</span></span>  
 <span data-ttu-id="20b0b-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20b0b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20b0b-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20b0b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20b0b-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20b0b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20b0b-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20b0b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b0b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20b0b-119">See also</span></span>

- [<span data-ttu-id="20b0b-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="20b0b-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

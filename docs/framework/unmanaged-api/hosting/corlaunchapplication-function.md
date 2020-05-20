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
ms.openlocfilehash: 031bfc3d7fcd9f1f04e616e460cb3201813eae55
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616554"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="62d91-102">Funzione CorLaunchApplication</span><span class="sxs-lookup"><span data-stu-id="62d91-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="62d91-103">Avvia l'applicazione nel percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62d91-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="62d91-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="62d91-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62d91-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62d91-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="62d91-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="62d91-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="62d91-107">in Valore dell'enumerazione [HOST_TYPE](host-type-enumeration.md) che specifica il tipo di host che sta avviando l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62d91-107">[in] A value of the [HOST_TYPE](host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="62d91-108">in Nome completo dell'applicazione in fase di avvio.</span><span class="sxs-lookup"><span data-stu-id="62d91-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="62d91-109">in Numero di percorsi del manifesto per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62d91-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="62d91-110">in Matrice di stringhe, ognuna delle quali specifica un percorso di un manifesto per l'applicazione in fase di avvio.</span><span class="sxs-lookup"><span data-stu-id="62d91-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="62d91-111">in Numero di elementi di dati di attivazione per l'applicazione in fase di avvio.</span><span class="sxs-lookup"><span data-stu-id="62d91-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="62d91-112">in Una matrice di stringhe, ognuna delle quali è un elemento di dati di attivazione per l'applicazione che viene avviata.</span><span class="sxs-lookup"><span data-stu-id="62d91-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="62d91-113">out Puntatore alle informazioni sul processo in cui è stata caricata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62d91-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62d91-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62d91-114">Requirements</span></span>  
 <span data-ttu-id="62d91-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62d91-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d91-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="62d91-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62d91-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62d91-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62d91-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d91-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d91-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62d91-119">See also</span></span>

- [<span data-ttu-id="62d91-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="62d91-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

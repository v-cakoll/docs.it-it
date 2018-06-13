---
title: Funzione CreateApplicationContext
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80012d030d0ea51ab3d150a7fd346b78e29dbde5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430100"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="3cf82-102">Funzione CreateApplicationContext</span><span class="sxs-lookup"><span data-stu-id="3cf82-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="3cf82-103">Questa funzione supporta l'infrastruttura .NET Framework e non deve essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="3cf82-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cf82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3cf82-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3cf82-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3cf82-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="3cf82-106">[in] Un puntatore a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="3cf82-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="3cf82-107">[out] Puntatore a un contesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cf82-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cf82-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3cf82-108">Requirements</span></span>  
 <span data-ttu-id="3cf82-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cf82-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cf82-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3cf82-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3cf82-111">**Libreria:** inclusa come risorsa in Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="3cf82-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="3cf82-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cf82-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf82-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cf82-113">See Also</span></span>  
 [<span data-ttu-id="3cf82-114">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="3cf82-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="3cf82-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="3cf82-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="3cf82-116">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="3cf82-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)

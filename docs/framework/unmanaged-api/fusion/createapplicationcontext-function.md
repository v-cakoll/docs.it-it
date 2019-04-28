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
ms.openlocfilehash: d98829b29100824e5d606e23aaf287c9f6e81d69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771917"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="0c3fd-102">Funzione CreateApplicationContext</span><span class="sxs-lookup"><span data-stu-id="0c3fd-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="0c3fd-103">Questa funzione supporta l'infrastruttura .NET Framework e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c3fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c3fd-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c3fd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c3fd-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="0c3fd-106">[in] Un puntatore a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="0c3fd-107">[out] Un puntatore a un contesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c3fd-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c3fd-108">Requirements</span></span>  
 <span data-ttu-id="0c3fd-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c3fd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c3fd-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="0c3fd-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0c3fd-111">**Libreria:** Inclusa come risorsa in Fusion</span><span class="sxs-lookup"><span data-stu-id="0c3fd-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="0c3fd-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c3fd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3fd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c3fd-113">See also</span></span>

- [<span data-ttu-id="0c3fd-114">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="0c3fd-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="0c3fd-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="0c3fd-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="0c3fd-116">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="0c3fd-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)

---
title: Metodo ICorDebugAppDomain::EnumerateAssemblies
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13137dcf7c2edd96397916cc7db905c9e48a3d0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401600"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="ed189-102">Metodo ICorDebugAppDomain::EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="ed189-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="ed189-103">Ottiene un enumeratore per gli assembly nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ed189-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed189-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed189-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed189-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed189-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="ed189-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugAssemblyEnum che è l'enumeratore per gli assembly nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ed189-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed189-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed189-107">Requirements</span></span>  
 <span data-ttu-id="ed189-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed189-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed189-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ed189-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed189-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ed189-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed189-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed189-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

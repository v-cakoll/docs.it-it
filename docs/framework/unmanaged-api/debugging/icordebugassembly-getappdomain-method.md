---
title: Metodo ICorDebugAssembly::GetAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
ms.openlocfilehash: 53042e722809a6574396648529c677d749154716
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132732"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="9957a-102">Metodo ICorDebugAssembly::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="9957a-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="9957a-103">Ottiene un puntatore a interfaccia per il dominio dell'applicazione che contiene questa istanza di `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="9957a-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9957a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9957a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9957a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9957a-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="9957a-106">out Puntatore all'indirizzo di un'interfaccia ICorDebugAppDomain che rappresenta il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9957a-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9957a-107">Note</span><span class="sxs-lookup"><span data-stu-id="9957a-107">Remarks</span></span>  
 <span data-ttu-id="9957a-108">Se questo assembly è l'assembly di sistema, `GetAppDomain` restituisce null.</span><span class="sxs-lookup"><span data-stu-id="9957a-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9957a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9957a-109">Requirements</span></span>  
 <span data-ttu-id="9957a-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9957a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9957a-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9957a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9957a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9957a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9957a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9957a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

---
title: Metodo ICorDebugAppDomain::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
ms.openlocfilehash: f2c881603cfa0e4b3d2dc8d1e996631b51d1e850
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134706"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="8fc9a-102">Metodo ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="8fc9a-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="8fc9a-103">Ottiene un puntatore a interfaccia per il dominio dell'applicazione Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8fc9a-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fc9a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fc9a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fc9a-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="8fc9a-106">out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugValue che rappresenta il dominio applicazione CLR.</span><span class="sxs-lookup"><span data-stu-id="8fc9a-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fc9a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8fc9a-107">Return Value</span></span>  
 <span data-ttu-id="8fc9a-108">Se per questo dominio applicazione non è stato costruito un oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito, il metodo restituisce `S_FALSE` e inserisce `NULL` in `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="8fc9a-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fc9a-109">Note</span><span class="sxs-lookup"><span data-stu-id="8fc9a-109">Remarks</span></span>  
 <span data-ttu-id="8fc9a-110">Ogni dominio applicazione in un processo può avere un oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito nel runtime che lo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="8fc9a-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="8fc9a-111">Questa funzione ottiene un oggetto interfaccia ICorDebugValue che corrisponde a questo oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito.</span><span class="sxs-lookup"><span data-stu-id="8fc9a-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fc9a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8fc9a-112">Requirements</span></span>  
 <span data-ttu-id="8fc9a-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fc9a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc9a-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fc9a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fc9a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fc9a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fc9a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fc9a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

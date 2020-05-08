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
ms.openlocfilehash: a21f3b36e418bbde5dcb90f25a39dae03fde77c9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895217"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="72726-102">Metodo ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="72726-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="72726-103">Ottiene un puntatore a interfaccia per il dominio dell'applicazione Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="72726-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72726-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72726-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72726-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="72726-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="72726-106">out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugValue che rappresenta il dominio applicazione CLR.</span><span class="sxs-lookup"><span data-stu-id="72726-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72726-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="72726-107">Return Value</span></span>  
 <span data-ttu-id="72726-108">Se un oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito non è stato costruito per questo dominio dell'applicazione, il `S_FALSE` metodo restituisce `NULL` e `*ppObject`inserisce in.</span><span class="sxs-lookup"><span data-stu-id="72726-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72726-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="72726-109">Remarks</span></span>  
 <span data-ttu-id="72726-110">Ogni dominio applicazione in un processo può avere un oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito nel runtime che lo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="72726-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="72726-111">Questa funzione ottiene un oggetto interfaccia ICorDebugValue che corrisponde a questo oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito.</span><span class="sxs-lookup"><span data-stu-id="72726-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72726-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72726-112">Requirements</span></span>  
 <span data-ttu-id="72726-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72726-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72726-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72726-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72726-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72726-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72726-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72726-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

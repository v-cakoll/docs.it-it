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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f528bcef7d06b503b1ee9d7bd4a61d3d3e9672
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406520"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="bea79-102">Metodo ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="bea79-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="bea79-103">Ottiene un puntatore a interfaccia per il dominio di applicazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bea79-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bea79-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bea79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bea79-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="bea79-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugValue che rappresenta il dominio dell'applicazione CLR.</span><span class="sxs-lookup"><span data-stu-id="bea79-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bea79-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bea79-107">Return Value</span></span>  
 <span data-ttu-id="bea79-108">Se un oggetto gestito <xref:System.AppDomain?displayProperty=nameWithType> oggetto non è stato costruito per il dominio applicazione, il metodo restituisce `S_FALSE` e inserisce `NULL` in `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="bea79-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bea79-109">Note</span><span class="sxs-lookup"><span data-stu-id="bea79-109">Remarks</span></span>  
 <span data-ttu-id="bea79-110">Ogni dominio applicazione in un processo potrebbe essere gestita <xref:System.AppDomain?displayProperty=nameWithType> oggetto runtime che lo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="bea79-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="bea79-111">Questa funzione Ottiene un oggetto di interfaccia ICorDebugValue che corrisponde a questo gestiti <xref:System.AppDomain?displayProperty=nameWithType> oggetto.</span><span class="sxs-lookup"><span data-stu-id="bea79-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bea79-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bea79-112">Requirements</span></span>  
 <span data-ttu-id="bea79-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bea79-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bea79-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bea79-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bea79-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="bea79-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bea79-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea79-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

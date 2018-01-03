---
title: Metodo ICorDebugAppDomain::GetObject
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetObject
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f8206c6e5efbee8522f425f9078d99a39bbdd42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="bc203-102">Metodo ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="bc203-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="bc203-103">Ottiene un puntatore a interfaccia per il dominio di applicazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bc203-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc203-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc203-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc203-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bc203-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="bc203-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugValue che rappresenta il dominio dell'applicazione CLR.</span><span class="sxs-lookup"><span data-stu-id="bc203-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc203-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bc203-107">Return Value</span></span>  
 <span data-ttu-id="bc203-108">Se un oggetto gestito <xref:System.AppDomain?displayProperty=nameWithType> oggetto non è stato costruito per il dominio applicazione, il metodo restituisce `S_FALSE` e inserisce `NULL` in `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="bc203-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc203-109">Note</span><span class="sxs-lookup"><span data-stu-id="bc203-109">Remarks</span></span>  
 <span data-ttu-id="bc203-110">Ogni dominio applicazione in un processo potrebbe essere gestita <xref:System.AppDomain?displayProperty=nameWithType> oggetto runtime che lo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="bc203-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="bc203-111">Questa funzione Ottiene un oggetto di interfaccia ICorDebugValue che corrisponde a questo gestiti <xref:System.AppDomain?displayProperty=nameWithType> oggetto.</span><span class="sxs-lookup"><span data-stu-id="bc203-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc203-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc203-112">Requirements</span></span>  
 <span data-ttu-id="bc203-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc203-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc203-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bc203-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc203-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc203-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc203-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc203-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

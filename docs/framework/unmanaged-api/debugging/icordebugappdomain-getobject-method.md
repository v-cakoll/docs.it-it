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
ms.openlocfilehash: c4f923d8e9bf9762d5208dd6e9be527a50a688b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="4491b-102">Metodo ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="4491b-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="4491b-103">Ottiene un puntatore a interfaccia per il dominio di applicazione di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4491b-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4491b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4491b-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4491b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4491b-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="4491b-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugValue che rappresenta il dominio dell'applicazione CLR.</span><span class="sxs-lookup"><span data-stu-id="4491b-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4491b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4491b-107">Return Value</span></span>  
 <span data-ttu-id="4491b-108">Se un oggetto gestito <xref:System.AppDomain?displayProperty=nameWithType> oggetto non è stato costruito per il dominio applicazione, il metodo restituisce `S_FALSE` e inserisce `NULL` in `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="4491b-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4491b-109">Note</span><span class="sxs-lookup"><span data-stu-id="4491b-109">Remarks</span></span>  
 <span data-ttu-id="4491b-110">Ogni dominio applicazione in un processo potrebbe essere gestita <xref:System.AppDomain?displayProperty=nameWithType> oggetto runtime che lo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="4491b-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="4491b-111">Questa funzione Ottiene un oggetto di interfaccia ICorDebugValue che corrisponde a questo gestiti <xref:System.AppDomain?displayProperty=nameWithType> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4491b-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4491b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4491b-112">Requirements</span></span>  
 <span data-ttu-id="4491b-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4491b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4491b-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4491b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4491b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4491b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4491b-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4491b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

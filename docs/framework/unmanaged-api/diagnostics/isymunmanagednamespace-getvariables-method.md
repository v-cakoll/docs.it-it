---
title: Metodo ISymUnmanagedNamespace::GetVariables
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetVariables
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fcfeba065bcdc996b5bc742dfea33b4417a29f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="99a3e-102">Metodo ISymUnmanagedNamespace::GetVariables</span><span class="sxs-lookup"><span data-stu-id="99a3e-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="99a3e-103">Restituisce tutte le variabili definite in ambito globale all'interno di questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="99a3e-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99a3e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99a3e-104">Syntax</span></span>  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99a3e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="99a3e-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="99a3e-106">[in] Oggetto `ULONG32` che indica le dimensioni del `pVars` matrice.</span><span class="sxs-lookup"><span data-stu-id="99a3e-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="99a3e-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="99a3e-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="99a3e-108">[out] Puntatore a un buffer che contiene gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="99a3e-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99a3e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="99a3e-109">Return Value</span></span>  
 <span data-ttu-id="99a3e-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="99a3e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99a3e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99a3e-111">Requirements</span></span>  
 <span data-ttu-id="99a3e-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="99a3e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99a3e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99a3e-113">See Also</span></span>  
 [<span data-ttu-id="99a3e-114">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="99a3e-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)

---
title: Metodo ISymUnmanagedNamespace::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c5b65cdeb36b8abf17c74d41a7fc7dfb34fa5731
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939490"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="3f4e0-102">Metodo ISymUnmanagedNamespace::GetVariables</span><span class="sxs-lookup"><span data-stu-id="3f4e0-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="3f4e0-103">Restituisce tutte le variabili definite in ambito globale all'interno di questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3f4e0-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f4e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f4e0-104">Syntax</span></span>  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f4e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f4e0-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="3f4e0-106">[in] Oggetto `ULONG32` che indica le dimensioni del `pVars` matrice.</span><span class="sxs-lookup"><span data-stu-id="3f4e0-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="3f4e0-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3f4e0-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="3f4e0-108">[out] Puntatore a un buffer che contiene gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3f4e0-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f4e0-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3f4e0-109">Return Value</span></span>  
 <span data-ttu-id="3f4e0-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="3f4e0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f4e0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f4e0-111">Requirements</span></span>  
 <span data-ttu-id="3f4e0-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3f4e0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4e0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f4e0-113">See also</span></span>

- [<span data-ttu-id="3f4e0-114">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="3f4e0-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)

---
title: Metodo ISymUnmanagedReader::GetUserEntryPoint
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea0cba1f1b9154ccb14d75f7c377a8153c24f2b0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499483"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="d3671-102">Metodo ISymUnmanagedReader::GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="d3671-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="d3671-103">Restituisce il metodo che è stato specificato come punto di ingresso utente per il modulo, se presente.</span><span class="sxs-lookup"><span data-stu-id="d3671-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="d3671-104">Questo metodo, ad esempio, potrebbe essere il metodo dell'utente principale anziché stub generato dal compilatore prima del metodo main.</span><span class="sxs-lookup"><span data-stu-id="d3671-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3671-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3671-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3671-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3671-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="d3671-107">[out] Puntatore a una variabile che riceve il punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="d3671-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3671-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d3671-108">Return Value</span></span>  
 <span data-ttu-id="d3671-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d3671-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3671-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3671-110">Requirements</span></span>  
 <span data-ttu-id="d3671-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d3671-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3671-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3671-112">See also</span></span>
- [<span data-ttu-id="d3671-113">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="d3671-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

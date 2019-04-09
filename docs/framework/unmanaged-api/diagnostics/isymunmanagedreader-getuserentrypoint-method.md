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
ms.openlocfilehash: 0267ae8b57c837b097d496c8e119085d03417e36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211270"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="a2f6e-102">Metodo ISymUnmanagedReader::GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="a2f6e-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="a2f6e-103">Restituisce il metodo che è stato specificato come punto di ingresso utente per il modulo, se presente.</span><span class="sxs-lookup"><span data-stu-id="a2f6e-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="a2f6e-104">Questo metodo, ad esempio, potrebbe essere il metodo dell'utente principale anziché stub generato dal compilatore prima del metodo main.</span><span class="sxs-lookup"><span data-stu-id="a2f6e-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2f6e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2f6e-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2f6e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2f6e-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="a2f6e-107">[out] Puntatore a una variabile che riceve il punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="a2f6e-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2f6e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a2f6e-108">Return Value</span></span>  
 <span data-ttu-id="a2f6e-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="a2f6e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2f6e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2f6e-110">Requirements</span></span>  
 <span data-ttu-id="a2f6e-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a2f6e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f6e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2f6e-112">See also</span></span>

- [<span data-ttu-id="a2f6e-113">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="a2f6e-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

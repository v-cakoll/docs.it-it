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
ms.openlocfilehash: 7b4c334d82320066bf9459907660fe6b7e2acefd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425321"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="e104b-102">Metodo ISymUnmanagedReader::GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="e104b-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="e104b-103">Restituisce il metodo che è stato specificato come punto di ingresso utente per il modulo, se presente.</span><span class="sxs-lookup"><span data-stu-id="e104b-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="e104b-104">Ad esempio, questo metodo potrebbe essere metodo principale dell'utente anziché gli stub generato dal compilatore prima del metodo principale.</span><span class="sxs-lookup"><span data-stu-id="e104b-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e104b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e104b-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e104b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e104b-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="e104b-107">[out] Puntatore a una variabile che riceve il punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="e104b-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e104b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e104b-108">Return Value</span></span>  
 <span data-ttu-id="e104b-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e104b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e104b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e104b-110">Requirements</span></span>  
 <span data-ttu-id="e104b-111">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e104b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e104b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e104b-112">See Also</span></span>  
 [<span data-ttu-id="e104b-113">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="e104b-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

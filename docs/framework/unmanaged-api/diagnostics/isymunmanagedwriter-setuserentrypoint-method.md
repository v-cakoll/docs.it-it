---
title: Metodo ISymUnmanagedWriter::SetUserEntryPoint
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3bd3d411ad6fe7f65d1eeb25754794704752009e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488357"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="ca007-102">Metodo ISymUnmanagedWriter::SetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="ca007-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="ca007-103">Specifica il metodo definito dall'utente che è il punto di ingresso per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="ca007-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="ca007-104">Ad esempio, il punto di ingresso potrebbe essere il metodo dell'utente principale invece stub generato dal compilatore prima main.</span><span class="sxs-lookup"><span data-stu-id="ca007-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca007-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca007-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca007-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca007-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="ca007-107">[in] Scegliere il token di metadati per il metodo che è la voce dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ca007-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca007-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ca007-108">Return Value</span></span>  
 <span data-ttu-id="ca007-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ca007-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca007-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca007-110">Requirements</span></span>  
 <span data-ttu-id="ca007-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ca007-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca007-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca007-112">See also</span></span>
- [<span data-ttu-id="ca007-113">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ca007-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

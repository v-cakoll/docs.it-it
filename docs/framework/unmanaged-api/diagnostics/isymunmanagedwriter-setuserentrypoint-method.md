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
ms.openlocfilehash: d14d542a8c1d8adeaf56dc1564e8e10121cd4064
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224221"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="e0c34-102">Metodo ISymUnmanagedWriter::SetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="e0c34-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="e0c34-103">Specifica il metodo definito dall'utente che è il punto di ingresso per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="e0c34-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="e0c34-104">Ad esempio, il punto di ingresso potrebbe essere il metodo dell'utente principale invece stub generato dal compilatore prima main.</span><span class="sxs-lookup"><span data-stu-id="e0c34-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c34-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0c34-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0c34-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0c34-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="e0c34-107">[in] Scegliere il token di metadati per il metodo che è la voce dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e0c34-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0c34-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e0c34-108">Return Value</span></span>  
 <span data-ttu-id="e0c34-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e0c34-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c34-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0c34-110">Requirements</span></span>  
 <span data-ttu-id="e0c34-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e0c34-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c34-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0c34-112">See also</span></span>

- [<span data-ttu-id="e0c34-113">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="e0c34-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

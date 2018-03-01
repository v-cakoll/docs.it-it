---
title: Metodo ISymUnmanagedWriter::SetUserEntryPoint
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5da021bce46df02789547eb7ee50133b6f4d4af6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="d5f71-102">Metodo ISymUnmanagedWriter::SetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="d5f71-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="d5f71-103">Specifica il metodo definito dall'utente che è il punto di ingresso per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="d5f71-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="d5f71-104">Ad esempio, questo punto di ingresso potrebbe essere il metodo dell'utente principale invece stub generato dal compilatore prima del form principale.</span><span class="sxs-lookup"><span data-stu-id="d5f71-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5f71-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5f71-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5f71-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5f71-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="d5f71-107">[in] Scegliere il token di metadati per il metodo che è la voce dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d5f71-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5f71-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5f71-108">Return Value</span></span>  
 <span data-ttu-id="d5f71-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d5f71-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5f71-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5f71-110">Requirements</span></span>  
 <span data-ttu-id="d5f71-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d5f71-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f71-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5f71-112">See Also</span></span>  
 [<span data-ttu-id="d5f71-113">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d5f71-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

---
title: Metodo ISymUnmanagedWriter::SetUserEntryPoint
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetUserEntryPoint
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be7f348237fdcf0a136d34ce3b6b8548c16d5547
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="b57ec-102">Metodo ISymUnmanagedWriter::SetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="b57ec-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="b57ec-103">Specifica il metodo definito dall'utente che è il punto di ingresso per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="b57ec-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="b57ec-104">Ad esempio, questo punto di ingresso potrebbe essere il metodo dell'utente principale invece stub generato dal compilatore prima del form principale.</span><span class="sxs-lookup"><span data-stu-id="b57ec-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b57ec-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b57ec-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b57ec-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b57ec-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="b57ec-107">[in] Scegliere il token di metadati per il metodo che è la voce dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b57ec-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b57ec-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b57ec-108">Return Value</span></span>  
 <span data-ttu-id="b57ec-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b57ec-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b57ec-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b57ec-110">Requirements</span></span>  
 <span data-ttu-id="b57ec-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b57ec-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57ec-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b57ec-112">See Also</span></span>  
 [<span data-ttu-id="b57ec-113">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b57ec-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

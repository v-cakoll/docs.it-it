---
title: Metodo ISymUnmanagedWriter::UsingNamespace
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
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d02a36a43e8a831fbbef051f5898696d4d8e04c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="4ac87-102">Metodo ISymUnmanagedWriter::UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="4ac87-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="4ac87-103">Specifica il nome completo dello spazio dei nomi specificato viene utilizzato all'interno dell'ambito lessicale aperto.</span><span class="sxs-lookup"><span data-stu-id="4ac87-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="4ac87-104">Verrà utilizzato lo spazio dei nomi all'interno di tutti gli ambiti che ereditano dall'ambito attualmente aperto.</span><span class="sxs-lookup"><span data-stu-id="4ac87-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="4ac87-105">La chiusura dell'ambito corrente interromperà anche l'utilizzo dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4ac87-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ac87-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ac87-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ac87-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="4ac87-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="4ac87-108">[in] Un puntatore al nome completo dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4ac87-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ac87-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4ac87-109">Return Value</span></span>  
 <span data-ttu-id="4ac87-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4ac87-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ac87-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ac87-111">Requirements</span></span>  
 <span data-ttu-id="4ac87-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4ac87-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac87-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ac87-113">See Also</span></span>  
 [<span data-ttu-id="4ac87-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="4ac87-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

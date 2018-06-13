---
title: Metodo ISymUnmanagedWriter::UsingNamespace
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a5ff52a95fd6ebaec05439cbc702d5513d0cc78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427769"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="b6fc1-102">Metodo ISymUnmanagedWriter::UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="b6fc1-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="b6fc1-103">Specifica il nome completo dello spazio dei nomi specificato viene utilizzato all'interno dell'ambito lessicale aperto.</span><span class="sxs-lookup"><span data-stu-id="b6fc1-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="b6fc1-104">Verrà utilizzato lo spazio dei nomi all'interno di tutti gli ambiti che ereditano dall'ambito attualmente aperto.</span><span class="sxs-lookup"><span data-stu-id="b6fc1-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="b6fc1-105">La chiusura dell'ambito corrente interromperà anche l'utilizzo dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b6fc1-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6fc1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6fc1-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6fc1-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6fc1-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="b6fc1-108">[in] Un puntatore al nome completo dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b6fc1-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6fc1-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b6fc1-109">Return Value</span></span>  
 <span data-ttu-id="b6fc1-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b6fc1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6fc1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6fc1-111">Requirements</span></span>  
 <span data-ttu-id="b6fc1-112">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6fc1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6fc1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6fc1-113">See Also</span></span>  
 [<span data-ttu-id="b6fc1-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="b6fc1-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

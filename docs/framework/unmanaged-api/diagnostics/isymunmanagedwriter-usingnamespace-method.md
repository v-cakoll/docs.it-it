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
ms.openlocfilehash: d0739cc38d1f12967f0daef2d6828e04a256ade6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201845"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="5b2e2-102">Metodo ISymUnmanagedWriter::UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="5b2e2-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="5b2e2-103">Specifica il nome completo dello spazio dei nomi specificato viene utilizzato all'interno dell'ambito lessicale attualmente aperto.</span><span class="sxs-lookup"><span data-stu-id="5b2e2-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="5b2e2-104">Verrà usato lo spazio dei nomi all'interno di tutti gli ambiti che ereditano dall'ambito attualmente aperto.</span><span class="sxs-lookup"><span data-stu-id="5b2e2-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="5b2e2-105">La chiusura dell'ambito corrente anche interromperà l'utilizzo dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5b2e2-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b2e2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b2e2-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b2e2-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b2e2-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="5b2e2-108">[in] Un puntatore al nome completo dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5b2e2-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b2e2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5b2e2-109">Return Value</span></span>  
 <span data-ttu-id="5b2e2-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5b2e2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b2e2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b2e2-111">Requirements</span></span>  
 <span data-ttu-id="5b2e2-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5b2e2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b2e2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b2e2-113">See also</span></span>

- [<span data-ttu-id="5b2e2-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="5b2e2-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

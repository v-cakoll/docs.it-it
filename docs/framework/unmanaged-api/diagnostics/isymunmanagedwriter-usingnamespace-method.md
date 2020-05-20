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
ms.openlocfilehash: e4348cc59924b65b6c6bb53a9c2a98f1a1161b50
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614734"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="143a4-102">Metodo ISymUnmanagedWriter::UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="143a4-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="143a4-103">Specifica che il nome dello spazio dei nomi completo specificato viene utilizzato all'interno dell'ambito lessicale attualmente aperto.</span><span class="sxs-lookup"><span data-stu-id="143a4-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="143a4-104">Lo spazio dei nomi verrà usato in tutti gli ambiti che ereditano dall'ambito attualmente aperto.</span><span class="sxs-lookup"><span data-stu-id="143a4-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="143a4-105">La chiusura dell'ambito corrente interrompe anche l'uso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="143a4-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="143a4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="143a4-106">Syntax</span></span>  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="143a4-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="143a4-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="143a4-108">in Puntatore al nome completo dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="143a4-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="143a4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="143a4-109">Return Value</span></span>  
 <span data-ttu-id="143a4-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="143a4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="143a4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="143a4-111">Requirements</span></span>  
 <span data-ttu-id="143a4-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="143a4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143a4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="143a4-113">See also</span></span>

- [<span data-ttu-id="143a4-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="143a4-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

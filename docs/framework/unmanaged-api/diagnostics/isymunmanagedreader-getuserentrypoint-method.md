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
ms.openlocfilehash: d465f830fa73016c3cf3f7df3a4a4d0c42bc0980
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615501"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="5ef49-102">Metodo ISymUnmanagedReader::GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="5ef49-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="5ef49-103">Restituisce il metodo specificato come punto di ingresso utente per il modulo, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="5ef49-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="5ef49-104">Questo metodo, ad esempio, potrebbe essere il metodo principale dell'utente anziché gli stub generati dal compilatore prima del metodo Main.</span><span class="sxs-lookup"><span data-stu-id="5ef49-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef49-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ef49-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ef49-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5ef49-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="5ef49-107">out Puntatore a una variabile che riceve il punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="5ef49-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ef49-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5ef49-108">Return Value</span></span>  
 <span data-ttu-id="5ef49-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5ef49-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ef49-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ef49-110">Requirements</span></span>  
 <span data-ttu-id="5ef49-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5ef49-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef49-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ef49-112">See also</span></span>

- [<span data-ttu-id="5ef49-113">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="5ef49-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

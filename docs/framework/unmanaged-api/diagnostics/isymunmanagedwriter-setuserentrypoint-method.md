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
ms.openlocfilehash: 8b51a9dc3a968c6bd2f5f9b149f13f88dc6a1e05
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614747"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="f002e-102">Metodo ISymUnmanagedWriter::SetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="f002e-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="f002e-103">Specifica il metodo definito dall'utente che rappresenta il punto di ingresso per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="f002e-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="f002e-104">Questo punto di ingresso, ad esempio, potrebbe essere il metodo principale dell'utente anziché gli stub generati dal compilatore prima di Main.</span><span class="sxs-lookup"><span data-stu-id="f002e-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f002e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f002e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f002e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f002e-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="f002e-107">in Token di metadati per il metodo che rappresenta il punto di ingresso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f002e-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f002e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f002e-108">Return Value</span></span>  
 <span data-ttu-id="f002e-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f002e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f002e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f002e-110">Requirements</span></span>  
 <span data-ttu-id="f002e-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f002e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f002e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f002e-112">See also</span></span>

- [<span data-ttu-id="f002e-113">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f002e-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

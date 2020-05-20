---
title: Metodo ISymUnmanagedWriter::CloseScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 4d8790dc68bc063deed4c58ba0df8e9ea258b9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610080"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="d05bd-102">Metodo ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="d05bd-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="d05bd-103">Chiude l'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="d05bd-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d05bd-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d05bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d05bd-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="d05bd-106">in Offset dall'inizio del metodo del punto alla fine dell'ultima istruzione nell'ambito lessicale, espresso in byte.</span><span class="sxs-lookup"><span data-stu-id="d05bd-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d05bd-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d05bd-107">Return Value</span></span>  
 <span data-ttu-id="d05bd-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d05bd-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d05bd-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d05bd-109">Remarks</span></span>  
 <span data-ttu-id="d05bd-110">Una volta chiuso un ambito, non è possibile definire altre variabili al suo interno.</span><span class="sxs-lookup"><span data-stu-id="d05bd-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="d05bd-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere utilizzato con [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) per definire in un secondo momento l'offset iniziale e finale dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="d05bd-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="d05bd-112">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e `ISymUnmanagedWriter::CloseScope` saranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="d05bd-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="d05bd-113">Gli identificatori di ambito sono validi solo nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="d05bd-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d05bd-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d05bd-114">Requirements</span></span>  
 <span data-ttu-id="d05bd-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d05bd-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05bd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d05bd-116">See also</span></span>

- [<span data-ttu-id="d05bd-117">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d05bd-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

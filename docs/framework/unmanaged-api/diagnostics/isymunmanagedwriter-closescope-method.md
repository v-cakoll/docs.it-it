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
ms.openlocfilehash: e2e911fb1d737ebb6b2106c89ac11335788ace4f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501729"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="f3c28-102">Metodo ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="f3c28-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="f3c28-103">Chiude l'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="f3c28-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3c28-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3c28-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3c28-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3c28-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="f3c28-106">in Offset dall'inizio del metodo del punto alla fine dell'ultima istruzione nell'ambito lessicale, espresso in byte.</span><span class="sxs-lookup"><span data-stu-id="f3c28-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3c28-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f3c28-107">Return Value</span></span>  
 <span data-ttu-id="f3c28-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f3c28-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3c28-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f3c28-109">Remarks</span></span>  
 <span data-ttu-id="f3c28-110">Una volta chiuso un ambito, non è possibile definire altre variabili al suo interno.</span><span class="sxs-lookup"><span data-stu-id="f3c28-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="f3c28-111">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere utilizzato con [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) per definire in un secondo momento l'offset iniziale e finale dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="f3c28-111">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="f3c28-112">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e `ISymUnmanagedWriter::CloseScope` saranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="f3c28-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="f3c28-113">Gli identificatori di ambito sono validi solo nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="f3c28-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3c28-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3c28-114">Requirements</span></span>  
 <span data-ttu-id="f3c28-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f3c28-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c28-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3c28-116">See also</span></span>

- [<span data-ttu-id="f3c28-117">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f3c28-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

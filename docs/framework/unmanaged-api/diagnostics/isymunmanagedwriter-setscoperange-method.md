---
title: Metodo ISymUnmanagedWriter::SetScopeRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
ms.openlocfilehash: b57bb549278f62cdce6ed5deaaa62f154ec919b5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609365"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="1b5e7-102">Metodo ISymUnmanagedWriter::SetScopeRange</span><span class="sxs-lookup"><span data-stu-id="1b5e7-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="1b5e7-103">Definisce l'intervallo di offset per l'ambito lessicale specificato.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="1b5e7-104">L'ambito diventa il nuovo ambito corrente e viene inserito in uno stack di ambiti.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="1b5e7-105">Gli ambiti devono formare una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="1b5e7-106">Gli elementi di pari livello non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b5e7-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b5e7-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b5e7-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b5e7-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="1b5e7-109">in Identificatore dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="1b5e7-110">in Offset, in byte, della prima istruzione nell'ambito lessicale dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="1b5e7-111">in Offset, in byte, dell'ultima istruzione nell'ambito lessicale dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b5e7-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1b5e7-112">Return Value</span></span>  
 <span data-ttu-id="1b5e7-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b5e7-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1b5e7-114">Remarks</span></span>  
 <span data-ttu-id="1b5e7-115">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere usato con `ISymUnmanagedWriter::SetScopeRange` per definire un offset iniziale e finale dell'ambito in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="1b5e7-116">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="1b5e7-117">Gli identificatori di ambito sono validi solo nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b5e7-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b5e7-118">Requirements</span></span>  
 <span data-ttu-id="1b5e7-119">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1b5e7-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5e7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b5e7-120">See also</span></span>

- [<span data-ttu-id="1b5e7-121">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="1b5e7-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

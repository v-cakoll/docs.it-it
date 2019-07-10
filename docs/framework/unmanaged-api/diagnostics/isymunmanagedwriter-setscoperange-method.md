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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c13eb7ca16cdb7c70f3fef0dd4efcb9362cd3d87
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776590"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="64d1b-102">Metodo ISymUnmanagedWriter::SetScopeRange</span><span class="sxs-lookup"><span data-stu-id="64d1b-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="64d1b-103">Definisce l'intervallo di offset per l'ambito lessicale specificato.</span><span class="sxs-lookup"><span data-stu-id="64d1b-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="64d1b-104">L'ambito diventa il nuovo ambito corrente e viene inserito nello stack di ambiti.</span><span class="sxs-lookup"><span data-stu-id="64d1b-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="64d1b-105">Gli ambiti devono formare una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="64d1b-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="64d1b-106">Elementi di pari livello non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="64d1b-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d1b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64d1b-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64d1b-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="64d1b-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="64d1b-109">[in] L'identificatore di ambito per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="64d1b-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="64d1b-110">[in] Offset, in byte, della prima istruzione dell'ambito lessicale a partire dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="64d1b-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="64d1b-111">[in] Offset, in byte, dell'ultima istruzione nell'ambito lessicale a partire dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="64d1b-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64d1b-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="64d1b-112">Return Value</span></span>  
 <span data-ttu-id="64d1b-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="64d1b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64d1b-114">Note</span><span class="sxs-lookup"><span data-stu-id="64d1b-114">Remarks</span></span>  
 <span data-ttu-id="64d1b-115">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere usato con `ISymUnmanagedWriter::SetScopeRange` per definire un ambito dell'offset iniziale e finale in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="64d1b-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="64d1b-116">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="64d1b-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="64d1b-117">Gli identificatori di ambito solo sono validi nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="64d1b-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64d1b-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64d1b-118">Requirements</span></span>  
 <span data-ttu-id="64d1b-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="64d1b-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d1b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64d1b-120">See also</span></span>

- [<span data-ttu-id="64d1b-121">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="64d1b-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

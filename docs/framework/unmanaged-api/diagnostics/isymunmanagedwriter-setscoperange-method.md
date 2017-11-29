---
title: Metodo ISymUnmanagedWriter::SetScopeRange
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetScopeRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b86df423d53c9fa3a738c603d6cc575add594cae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="288ca-102">Metodo ISymUnmanagedWriter::SetScopeRange</span><span class="sxs-lookup"><span data-stu-id="288ca-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="288ca-103">Definisce l'intervallo di offset per l'ambito lessicale specificato.</span><span class="sxs-lookup"><span data-stu-id="288ca-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="288ca-104">L'ambito diventa il nuovo ambito corrente e viene inserito nello stack di ambiti.</span><span class="sxs-lookup"><span data-stu-id="288ca-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="288ca-105">Gli ambiti devono formare una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="288ca-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="288ca-106">Elementi di pari livello non è consentiti si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="288ca-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="288ca-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="288ca-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="288ca-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="288ca-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="288ca-109">[in] L'identificatore di ambito per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="288ca-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="288ca-110">[in] L'offset in byte, della prima istruzione nell'ambito lessicale dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="288ca-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="288ca-111">[in] L'offset in byte, dell'ultima istruzione nell'ambito lessicale dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="288ca-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="288ca-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="288ca-112">Return Value</span></span>  
 <span data-ttu-id="288ca-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="288ca-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="288ca-114">Note</span><span class="sxs-lookup"><span data-stu-id="288ca-114">Remarks</span></span>  
 <span data-ttu-id="288ca-115">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere utilizzato con `ISymUnmanagedWriter::SetScopeRange` per definire un ambito dell'offset iniziale e finale in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="288ca-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="288ca-116">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="288ca-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="288ca-117">Gli identificatori di ambito sono solo validi nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="288ca-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="288ca-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="288ca-118">Requirements</span></span>  
 <span data-ttu-id="288ca-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="288ca-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="288ca-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="288ca-120">See Also</span></span>  
 [<span data-ttu-id="288ca-121">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="288ca-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

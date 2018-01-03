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
ms.workload: dotnet
ms.openlocfilehash: 9afb0038adc4273033fb9f1db1ebc57f43eae779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="3089b-102">Metodo ISymUnmanagedWriter::SetScopeRange</span><span class="sxs-lookup"><span data-stu-id="3089b-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="3089b-103">Definisce l'intervallo di offset per l'ambito lessicale specificato.</span><span class="sxs-lookup"><span data-stu-id="3089b-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="3089b-104">L'ambito diventa il nuovo ambito corrente e viene inserito nello stack di ambiti.</span><span class="sxs-lookup"><span data-stu-id="3089b-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="3089b-105">Gli ambiti devono formare una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="3089b-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="3089b-106">Elementi di pari livello non è consentiti si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="3089b-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3089b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3089b-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3089b-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="3089b-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="3089b-109">[in] L'identificatore di ambito per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="3089b-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="3089b-110">[in] L'offset in byte, della prima istruzione nell'ambito lessicale dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="3089b-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="3089b-111">[in] L'offset in byte, dell'ultima istruzione nell'ambito lessicale dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="3089b-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3089b-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3089b-112">Return Value</span></span>  
 <span data-ttu-id="3089b-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="3089b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3089b-114">Note</span><span class="sxs-lookup"><span data-stu-id="3089b-114">Remarks</span></span>  
 <span data-ttu-id="3089b-115">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere utilizzato con `ISymUnmanagedWriter::SetScopeRange` per definire un ambito dell'offset iniziale e finale in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="3089b-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="3089b-116">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="3089b-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="3089b-117">Gli identificatori di ambito sono solo validi nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="3089b-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3089b-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3089b-118">Requirements</span></span>  
 <span data-ttu-id="3089b-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3089b-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3089b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3089b-120">See Also</span></span>  
 [<span data-ttu-id="3089b-121">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="3089b-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

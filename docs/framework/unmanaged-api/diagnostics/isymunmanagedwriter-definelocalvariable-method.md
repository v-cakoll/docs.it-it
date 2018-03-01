---
title: Metodo ISymUnmanagedWriter::DefineLocalVariable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 89ea3e23166b4745b34b7c2af498d29564cdd68d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="a15fe-102">Metodo ISymUnmanagedWriter::DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="a15fe-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="a15fe-103">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="a15fe-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="a15fe-104">Questo metodo può essere chiamato più volte per una variabile con lo stesso nome presente in più posizioni in un ambito.</span><span class="sxs-lookup"><span data-stu-id="a15fe-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="a15fe-105">In questo caso, tuttavia, i valori del `startOffset` e `endOffset` parametri non devono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="a15fe-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a15fe-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a15fe-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a15fe-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a15fe-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="a15fe-108">[in] Un puntatore a un `WCHAR` che definisce il nome della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="a15fe-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="a15fe-109">[in] Attributi della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="a15fe-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="a15fe-110">[in] Oggetto `ULONG32` che indica le dimensioni, in byte, del `signature` buffer.</span><span class="sxs-lookup"><span data-stu-id="a15fe-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="a15fe-111">[in] La firma di variabile locale.</span><span class="sxs-lookup"><span data-stu-id="a15fe-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="a15fe-112">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a15fe-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="a15fe-113">[in] Il primo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="a15fe-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="a15fe-114">[in] Il secondo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="a15fe-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="a15fe-115">[in] Terzo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="a15fe-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="a15fe-116">[in] Offset iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="a15fe-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="a15fe-117">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a15fe-117">This parameter is optional.</span></span> <span data-ttu-id="a15fe-118">Se il valore è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="a15fe-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="a15fe-119">Se è un valore diverso da zero, la variabile rientrerà negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="a15fe-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="a15fe-120">[in] Offset finale della variabile.</span><span class="sxs-lookup"><span data-stu-id="a15fe-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="a15fe-121">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a15fe-121">This parameter is optional.</span></span> <span data-ttu-id="a15fe-122">Se il valore è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="a15fe-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="a15fe-123">Se è un valore diverso da zero, la variabile rientrerà negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="a15fe-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a15fe-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a15fe-124">Return Value</span></span>  
 <span data-ttu-id="a15fe-125">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="a15fe-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a15fe-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a15fe-126">Requirements</span></span>  
 <span data-ttu-id="a15fe-127">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a15fe-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a15fe-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a15fe-128">See Also</span></span>  
 [<span data-ttu-id="a15fe-129">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="a15fe-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="a15fe-130">Metodo DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="a15fe-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [<span data-ttu-id="a15fe-131">Metodo DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="a15fe-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)

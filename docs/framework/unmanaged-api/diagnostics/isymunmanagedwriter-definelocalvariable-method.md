---
title: Metodo ISymUnmanagedWriter::DefineLocalVariable
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c561eb70f0e3d243984decfb39629601f8eeea37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125298"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="617fe-102">Metodo ISymUnmanagedWriter::DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="617fe-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="617fe-103">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="617fe-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="617fe-104">Questo metodo può essere chiamato più volte per una variabile con lo stesso nome presente in più posizioni in un ambito.</span><span class="sxs-lookup"><span data-stu-id="617fe-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="617fe-105">In questo caso, tuttavia, i valori del `startOffset` e `endOffset` parametri non devono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="617fe-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="617fe-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="617fe-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="617fe-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="617fe-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="617fe-108">[in] Un puntatore a un `WCHAR` che definisce il nome della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="617fe-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="617fe-109">[in] Attributi della variabile locali.</span><span class="sxs-lookup"><span data-stu-id="617fe-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="617fe-110">[in] Oggetto `ULONG32` che indica la dimensione, espressa in byte, del `signature` buffer.</span><span class="sxs-lookup"><span data-stu-id="617fe-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="617fe-111">[in] Firma della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="617fe-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="617fe-112">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="617fe-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="617fe-113">[in] Il primo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="617fe-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="617fe-114">[in] Il secondo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="617fe-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="617fe-115">[in] Terzo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="617fe-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="617fe-116">[in] Offset iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="617fe-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="617fe-117">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="617fe-117">This parameter is optional.</span></span> <span data-ttu-id="617fe-118">Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="617fe-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="617fe-119">Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="617fe-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="617fe-120">[in] Offset finale per la variabile.</span><span class="sxs-lookup"><span data-stu-id="617fe-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="617fe-121">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="617fe-121">This parameter is optional.</span></span> <span data-ttu-id="617fe-122">Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="617fe-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="617fe-123">Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="617fe-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="617fe-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="617fe-124">Return Value</span></span>  
 <span data-ttu-id="617fe-125">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="617fe-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="617fe-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="617fe-126">Requirements</span></span>  
 <span data-ttu-id="617fe-127">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="617fe-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="617fe-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="617fe-128">See also</span></span>

- [<span data-ttu-id="617fe-129">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="617fe-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="617fe-130">Metodo DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="617fe-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="617fe-131">Metodo DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="617fe-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)

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
ms.openlocfilehash: f6a741df3ea57b5e9b4fa8bc5d304bfedd1d6c15
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428018"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="8459f-102">Metodo ISymUnmanagedWriter::DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="8459f-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="8459f-103">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="8459f-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="8459f-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span><span class="sxs-lookup"><span data-stu-id="8459f-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="8459f-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span><span class="sxs-lookup"><span data-stu-id="8459f-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8459f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8459f-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="8459f-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="8459f-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8459f-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span><span class="sxs-lookup"><span data-stu-id="8459f-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="8459f-109">[in] The local variable attributes.</span><span class="sxs-lookup"><span data-stu-id="8459f-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="8459f-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span><span class="sxs-lookup"><span data-stu-id="8459f-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="8459f-111">[in] The local variable signature.</span><span class="sxs-lookup"><span data-stu-id="8459f-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="8459f-112">[in] The address type.</span><span class="sxs-lookup"><span data-stu-id="8459f-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="8459f-113">[in] The first address for the parameter specification.</span><span class="sxs-lookup"><span data-stu-id="8459f-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="8459f-114">[in] The second address for the parameter specification.</span><span class="sxs-lookup"><span data-stu-id="8459f-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="8459f-115">[in] The third address for the parameter specification.</span><span class="sxs-lookup"><span data-stu-id="8459f-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="8459f-116">[in] The start offset for the variable.</span><span class="sxs-lookup"><span data-stu-id="8459f-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="8459f-117">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8459f-117">This parameter is optional.</span></span> <span data-ttu-id="8459f-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span><span class="sxs-lookup"><span data-stu-id="8459f-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="8459f-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span><span class="sxs-lookup"><span data-stu-id="8459f-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="8459f-120">[in] The end offset for the variable.</span><span class="sxs-lookup"><span data-stu-id="8459f-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="8459f-121">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8459f-121">This parameter is optional.</span></span> <span data-ttu-id="8459f-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span><span class="sxs-lookup"><span data-stu-id="8459f-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="8459f-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span><span class="sxs-lookup"><span data-stu-id="8459f-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8459f-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8459f-124">Return Value</span></span>  
 <span data-ttu-id="8459f-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="8459f-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8459f-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8459f-126">Requirements</span></span>  
 <span data-ttu-id="8459f-127">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8459f-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8459f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8459f-128">See also</span></span>

- [<span data-ttu-id="8459f-129">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="8459f-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="8459f-130">Metodo DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="8459f-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="8459f-131">Metodo DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="8459f-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)

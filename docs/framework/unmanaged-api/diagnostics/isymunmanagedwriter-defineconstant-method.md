---
title: Metodo ISymUnmanagedWriter::DefineConstant
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
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9b22b0d9c9de27ba9950a0501193bc682586bfbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="17507-102">Metodo ISymUnmanagedWriter::DefineConstant</span><span class="sxs-lookup"><span data-stu-id="17507-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="17507-103">Definisce un nome per un valore costante.</span><span class="sxs-lookup"><span data-stu-id="17507-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17507-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17507-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17507-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17507-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="17507-106">[in] Un puntatore a un `WCHAR` che definisce il nome della costante.</span><span class="sxs-lookup"><span data-stu-id="17507-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="17507-107">[in] Il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="17507-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="17507-108">[in] Dimensione della matrice `signature`.</span><span class="sxs-lookup"><span data-stu-id="17507-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="17507-109">[in] La firma di tipo per la costante.</span><span class="sxs-lookup"><span data-stu-id="17507-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17507-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="17507-110">Return Value</span></span>  
 <span data-ttu-id="17507-111">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="17507-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17507-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17507-112">Requirements</span></span>  
 <span data-ttu-id="17507-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="17507-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17507-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17507-114">See Also</span></span>  
 [<span data-ttu-id="17507-115">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="17507-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="17507-116">Metodo DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="17507-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)

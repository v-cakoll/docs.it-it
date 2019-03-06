---
title: Metodo ISymUnmanagedWriter::DefineGlobalVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bba8d887bc516149135aae61c4f9bdb9a9e0c9d9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470536"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="f7cd4-102">Metodo ISymUnmanagedWriter::DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="f7cd4-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="f7cd4-103">Definisce una variabile globale singola.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7cd4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7cd4-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7cd4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7cd4-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f7cd4-106">[in] Un puntatore a un `WCHAR` che definisce il nome della variabile globale.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="f7cd4-107">[in] Attributi della variabile globale.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="f7cd4-108">[in] Oggetto `ULONG32` che indica le dimensioni, in caratteri, del `signature` buffer.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="f7cd4-109">[in] Firma della variabile globale.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="f7cd4-110">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="f7cd4-111">[in] Il primo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="f7cd4-112">[in] Il secondo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="f7cd4-113">[in] Terzo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7cd4-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f7cd4-114">Return Value</span></span>  
 <span data-ttu-id="f7cd4-115">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7cd4-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7cd4-116">Requirements</span></span>  
 <span data-ttu-id="f7cd4-117">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f7cd4-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7cd4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7cd4-118">See also</span></span>
- [<span data-ttu-id="f7cd4-119">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f7cd4-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="f7cd4-120">Metodo DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="f7cd4-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="f7cd4-121">Metodo DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="f7cd4-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)

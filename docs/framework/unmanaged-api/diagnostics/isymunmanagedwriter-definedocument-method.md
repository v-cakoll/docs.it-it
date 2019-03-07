---
title: Metodo ISymUnmanagedWriter::DefineDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 41b27c8d545cce7051ca1507a6bd98b87a32468b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499563"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="e204f-102">Metodo ISymUnmanagedWriter::DefineDocument</span><span class="sxs-lookup"><span data-stu-id="e204f-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="e204f-103">Definisce un documento di origine.</span><span class="sxs-lookup"><span data-stu-id="e204f-103">Defines a source document.</span></span> <span data-ttu-id="e204f-104">Vengono forniti i GUID per i linguaggi conosciuti, fornitori e i tipi di documento.</span><span class="sxs-lookup"><span data-stu-id="e204f-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e204f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e204f-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e204f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e204f-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="e204f-107">[in] Un puntatore a un `WCHAR` che definisce l'uniform resource locator (URL) che identifica il documento.</span><span class="sxs-lookup"><span data-stu-id="e204f-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="e204f-108">[in] Puntatore a un GUID che definisce la lingua del documento.</span><span class="sxs-lookup"><span data-stu-id="e204f-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="e204f-109">[in] Puntatore a un GUID che definisce l'identità del fornitore del linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="e204f-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="e204f-110">[in] Un puntatore a un GUID che definisce il tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="e204f-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e204f-111">[out] Un puntatore al valore restituito [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e204f-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e204f-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e204f-112">Return Value</span></span>  
 <span data-ttu-id="e204f-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e204f-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e204f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e204f-114">Requirements</span></span>  
 <span data-ttu-id="e204f-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e204f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e204f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e204f-116">See also</span></span>
- [<span data-ttu-id="e204f-117">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="e204f-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

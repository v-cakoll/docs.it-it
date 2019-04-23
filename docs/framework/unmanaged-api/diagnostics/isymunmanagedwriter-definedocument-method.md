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
ms.openlocfilehash: 726ac0e23f739f451e1a0ab66c4c36aa6edbe569
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132132"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="d3b09-102">Metodo ISymUnmanagedWriter::DefineDocument</span><span class="sxs-lookup"><span data-stu-id="d3b09-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="d3b09-103">Definisce un documento di origine.</span><span class="sxs-lookup"><span data-stu-id="d3b09-103">Defines a source document.</span></span> <span data-ttu-id="d3b09-104">Vengono forniti i GUID per i linguaggi conosciuti, fornitori e i tipi di documento.</span><span class="sxs-lookup"><span data-stu-id="d3b09-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b09-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3b09-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3b09-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3b09-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="d3b09-107">[in] Un puntatore a un `WCHAR` che definisce l'uniform resource locator (URL) che identifica il documento.</span><span class="sxs-lookup"><span data-stu-id="d3b09-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="d3b09-108">[in] Puntatore a un GUID che definisce la lingua del documento.</span><span class="sxs-lookup"><span data-stu-id="d3b09-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="d3b09-109">[in] Puntatore a un GUID che definisce l'identità del fornitore del linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="d3b09-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="d3b09-110">[in] Un puntatore a un GUID che definisce il tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="d3b09-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d3b09-111">[out] Un puntatore al valore restituito [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d3b09-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3b09-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d3b09-112">Return Value</span></span>  
 <span data-ttu-id="d3b09-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d3b09-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3b09-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3b09-114">Requirements</span></span>  
 <span data-ttu-id="d3b09-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d3b09-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b09-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3b09-116">See also</span></span>

- [<span data-ttu-id="d3b09-117">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d3b09-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

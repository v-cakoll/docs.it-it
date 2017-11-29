---
title: Metodo ISymUnmanagedWriter::DefineDocument
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 638759cb52eb28cc79217da81a867f2593e1ae97
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="0c671-102">Metodo ISymUnmanagedWriter::DefineDocument</span><span class="sxs-lookup"><span data-stu-id="0c671-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="0c671-103">Definisce un documento di origine.</span><span class="sxs-lookup"><span data-stu-id="0c671-103">Defines a source document.</span></span> <span data-ttu-id="0c671-104">Per le lingue note, fornitori e i tipi di documento vengono forniti i GUID.</span><span class="sxs-lookup"><span data-stu-id="0c671-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c671-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c671-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c671-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c671-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="0c671-107">[in] Un puntatore a un `WCHAR` che definisce l'uniform resource locator (URL) che identifica il documento.</span><span class="sxs-lookup"><span data-stu-id="0c671-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="0c671-108">[in] Un puntatore a un GUID che definisce il linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="0c671-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="0c671-109">[in] Puntatore a un GUID che definisce l'identità del fornitore del linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="0c671-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="0c671-110">[in] Puntatore a un GUID che definisce il tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="0c671-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0c671-111">[out] Un puntatore all'oggetto restituito [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0c671-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c671-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c671-112">Return Value</span></span>  
 <span data-ttu-id="0c671-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0c671-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c671-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c671-114">Requirements</span></span>  
 <span data-ttu-id="0c671-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0c671-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c671-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c671-116">See Also</span></span>  
 [<span data-ttu-id="0c671-117">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0c671-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

---
title: Metodo ISymUnmanagedReader::GetDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a173c23ea33532f05e30d072677715e15d04018
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093684"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="cab79-102">Metodo ISymUnmanagedReader::GetDocument</span><span class="sxs-lookup"><span data-stu-id="cab79-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="cab79-103">Trova un documento.</span><span class="sxs-lookup"><span data-stu-id="cab79-103">Finds a document.</span></span> <span data-ttu-id="cab79-104">Il linguaggio del documento, fornitore e tipo sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="cab79-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cab79-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cab79-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cab79-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cab79-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="cab79-107">[in] L'URL che identifica il documento.</span><span class="sxs-lookup"><span data-stu-id="cab79-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="cab79-108">[in] Linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="cab79-108">[in] The document language.</span></span> <span data-ttu-id="cab79-109">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cab79-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="cab79-110">[in] L'identità del fornitore del linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="cab79-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="cab79-111">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cab79-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="cab79-112">[in] Il tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="cab79-112">[in] The type of the document.</span></span> <span data-ttu-id="cab79-113">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cab79-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="cab79-114">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="cab79-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cab79-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cab79-115">Return Value</span></span>  
 <span data-ttu-id="cab79-116">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cab79-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cab79-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cab79-117">Requirements</span></span>  
 <span data-ttu-id="cab79-118">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cab79-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cab79-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cab79-119">See also</span></span>

- [<span data-ttu-id="cab79-120">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="cab79-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

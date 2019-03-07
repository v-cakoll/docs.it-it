---
title: Metodo ISymUnmanagedReader::GetMethodFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 06ada4d4d34497cef15d693b285c780817653e71
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494071"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="2ed5c-102">Metodo ISymUnmanagedReader::GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="2ed5c-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="2ed5c-103">Restituisce il metodo che contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.</span><span class="sxs-lookup"><span data-stu-id="2ed5c-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed5c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ed5c-104">Syntax</span></span>  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ed5c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ed5c-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="2ed5c-106">[in] Il documento specificato.</span><span class="sxs-lookup"><span data-stu-id="2ed5c-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="2ed5c-107">[in] La riga del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="2ed5c-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="2ed5c-108">[in] La colonna del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="2ed5c-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2ed5c-109">[out] Un puntatore all'indirizzo di un [interfaccia ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) oggetto che rappresenta il metodo che contiene il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2ed5c-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ed5c-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2ed5c-110">Return Value</span></span>  
 <span data-ttu-id="2ed5c-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="2ed5c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed5c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ed5c-112">Requirements</span></span>  
 <span data-ttu-id="2ed5c-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2ed5c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed5c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ed5c-114">See also</span></span>
- [<span data-ttu-id="2ed5c-115">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="2ed5c-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

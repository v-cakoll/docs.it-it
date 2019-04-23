---
title: Metodo ISymUnmanagedReader::GetMethodsFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64d7f138094e03ca76ec78a50a6f37aa3d9ca2f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091733"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="385af-102">Metodo ISymUnmanagedReader::GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="385af-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="385af-103">Restituisce una matrice di metodi, ognuno dei quali contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.</span><span class="sxs-lookup"><span data-stu-id="385af-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="385af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="385af-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="385af-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="385af-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="385af-106">[in] Il documento specificato.</span><span class="sxs-lookup"><span data-stu-id="385af-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="385af-107">[in] La riga del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="385af-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="385af-108">[in] La colonna del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="385af-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="385af-109">[in] Dimensione della matrice `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="385af-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="385af-110">[out] Un puntatore a una variabile che riceve il numero di elementi restituiti nella `pRetVal` matrice.</span><span class="sxs-lookup"><span data-stu-id="385af-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="385af-111">[out] Una matrice di puntatori, ognuno dei quali punta a un [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) oggetto che rappresenta un metodo che contiene il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="385af-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="385af-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="385af-112">Return Value</span></span>  
 <span data-ttu-id="385af-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="385af-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="385af-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="385af-114">Requirements</span></span>  
 <span data-ttu-id="385af-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="385af-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="385af-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="385af-116">See also</span></span>

- [<span data-ttu-id="385af-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="385af-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

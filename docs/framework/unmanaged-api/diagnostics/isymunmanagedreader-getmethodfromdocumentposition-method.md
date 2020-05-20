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
ms.openlocfilehash: 8015056b110fe8a5b5122b1bc81143980b780047
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614981"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="0ac8b-102">Metodo ISymUnmanagedReader::GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="0ac8b-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="0ac8b-103">Restituisce il metodo che contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac8b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ac8b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ac8b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ac8b-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="0ac8b-106">in Documento specificato.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="0ac8b-107">in Riga del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="0ac8b-108">in Colonna del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0ac8b-109">out Puntatore all'indirizzo di un oggetto [interfaccia ISymUnmanagedMethod](isymunmanagedmethod-interface.md) che rappresenta il metodo che contiene il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ac8b-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0ac8b-110">Return Value</span></span>  
 <span data-ttu-id="0ac8b-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0ac8b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ac8b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ac8b-112">Requirements</span></span>  
 <span data-ttu-id="0ac8b-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0ac8b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac8b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ac8b-114">See also</span></span>

- [<span data-ttu-id="0ac8b-115">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="0ac8b-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

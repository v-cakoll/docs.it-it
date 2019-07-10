---
title: Metodo ISymUnmanagedReader::GetMethodByVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3210f0186401729a5bc95369e88b290ae49a634
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776988"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="fc6c8-102">Metodo ISymUnmanagedReader::GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="fc6c8-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="fc6c8-103">Ottiene un metodo del lettore di simboli, dato un token di metodo e un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="fc6c8-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="fc6c8-104">I numeri di versione iniziano da 1 e vengano incrementati ogni volta che il metodo viene modificato in seguito a un'operazione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="fc6c8-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc6c8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc6c8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc6c8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc6c8-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="fc6c8-107">[in] Il token del metodo.</span><span class="sxs-lookup"><span data-stu-id="fc6c8-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="fc6c8-108">[in] La versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="fc6c8-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fc6c8-109">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="fc6c8-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc6c8-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fc6c8-110">Return Value</span></span>  
 <span data-ttu-id="fc6c8-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fc6c8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc6c8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc6c8-112">Requirements</span></span>  
 <span data-ttu-id="fc6c8-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fc6c8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6c8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc6c8-114">See also</span></span>

- [<span data-ttu-id="fc6c8-115">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="fc6c8-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

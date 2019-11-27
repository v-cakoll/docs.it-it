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
ms.openlocfilehash: d5f42e5ed3ce7829cfcf921f3002c238985710a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426757"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="7a8a2-102">Metodo ISymUnmanagedReader::GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="7a8a2-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="7a8a2-103">Ottiene un metodo del lettore di simboli, dato un token del metodo e un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="7a8a2-104">I numeri di versione iniziano da 1 e vengono incrementati ogni volta che il metodo viene modificato come risultato di un'operazione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a8a2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a8a2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a8a2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a8a2-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="7a8a2-107">in Token del metodo.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="7a8a2-108">in Versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7a8a2-109">out Puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a8a2-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7a8a2-110">Return Value</span></span>  
 <span data-ttu-id="7a8a2-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a8a2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a8a2-112">Requirements</span></span>  
 <span data-ttu-id="7a8a2-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7a8a2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8a2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a8a2-114">See also</span></span>

- [<span data-ttu-id="7a8a2-115">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="7a8a2-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

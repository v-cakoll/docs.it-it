---
title: Metodo ISymUnmanagedReader::GetMethodVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: 8ee4c1bffccb44d15fa53eb3d4d6c0fcdc3e7697
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614968"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="51aba-102">Metodo ISymUnmanagedReader::GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="51aba-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="51aba-103">Ottiene la versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="51aba-103">Gets the method version.</span></span> <span data-ttu-id="51aba-104">La versione del metodo inizia da 1 e viene incrementata ogni volta che il metodo viene ricompilato.</span><span class="sxs-lookup"><span data-stu-id="51aba-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="51aba-105">La ricompilazione può verificarsi senza apportare modifiche al metodo.</span><span class="sxs-lookup"><span data-stu-id="51aba-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51aba-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51aba-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51aba-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="51aba-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="51aba-108">in Metodo per il quale ottenere la versione.</span><span class="sxs-lookup"><span data-stu-id="51aba-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="51aba-109">out Puntatore a una variabile che riceve la versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="51aba-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51aba-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="51aba-110">Return Value</span></span>  
 <span data-ttu-id="51aba-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="51aba-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51aba-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51aba-112">Requirements</span></span>  
 <span data-ttu-id="51aba-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="51aba-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51aba-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51aba-114">See also</span></span>

- [<span data-ttu-id="51aba-115">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="51aba-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

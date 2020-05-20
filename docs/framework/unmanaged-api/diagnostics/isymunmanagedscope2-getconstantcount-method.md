---
title: Metodo ISymUnmanagedScope2::GetConstantCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
ms.openlocfilehash: 88fc6b7d6076bca42050ca87533062557e6a7b50
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610951"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="ac70d-102">Metodo ISymUnmanagedScope2::GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="ac70d-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="ac70d-103">Ottiene un conteggio delle costanti definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="ac70d-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac70d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac70d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac70d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac70d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ac70d-106">out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere le costanti.</span><span class="sxs-lookup"><span data-stu-id="ac70d-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac70d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ac70d-107">Return Value</span></span>  
 <span data-ttu-id="ac70d-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ac70d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac70d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac70d-109">Requirements</span></span>  
 <span data-ttu-id="ac70d-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ac70d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac70d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac70d-111">See also</span></span>

- [<span data-ttu-id="ac70d-112">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="ac70d-112">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)

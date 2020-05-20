---
title: Metodo ISymUnmanagedMethod::GetSequencePointCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
ms.openlocfilehash: a44f81deb2d57b49f1fd0650fa52c06383210352
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614435"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="8379d-102">Metodo ISymUnmanagedMethod::GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="8379d-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="8379d-103">Ottiene il conteggio dei punti di sequenza all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="8379d-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8379d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8379d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8379d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8379d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8379d-106">out Puntatore a un oggetto `ULONG32` che riceve le dimensioni del buffer necessarie per contenere i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="8379d-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8379d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8379d-107">Return Value</span></span>  
 <span data-ttu-id="8379d-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8379d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8379d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8379d-109">Requirements</span></span>  
 <span data-ttu-id="8379d-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8379d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8379d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8379d-111">See also</span></span>

- [<span data-ttu-id="8379d-112">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="8379d-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)

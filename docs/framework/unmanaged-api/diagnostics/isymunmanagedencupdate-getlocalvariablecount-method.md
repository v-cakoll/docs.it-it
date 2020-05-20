---
title: Metodo ISymUnmanagedENCUpdate::GetLocalVariableCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: d04c9865d8272bf8d04080f6049ddfb1d4c643bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614578"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="a9c7e-102">Metodo ISymUnmanagedENCUpdate::GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="a9c7e-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="a9c7e-103">Ottiene il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a9c7e-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9c7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9c7e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a9c7e-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="a9c7e-106">in Token di metadati dei metodi.</span><span class="sxs-lookup"><span data-stu-id="a9c7e-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="a9c7e-107">out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a9c7e-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9c7e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a9c7e-108">Return Value</span></span>  
 <span data-ttu-id="a9c7e-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="a9c7e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9c7e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9c7e-110">Requirements</span></span>  
 <span data-ttu-id="a9c7e-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a9c7e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c7e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9c7e-112">See also</span></span>

- [<span data-ttu-id="a9c7e-113">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="a9c7e-113">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)

---
title: Metodo ISymUnmanagedScope::GetLocals
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: 0acd31d85504688427cace0222a657885035c537
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615384"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="ca04e-102">Metodo ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="ca04e-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="ca04e-103">Ottiene le variabili locali definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="ca04e-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca04e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca04e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca04e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca04e-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="ca04e-106">in Oggetto `ULONG32` che indica la dimensione della `locals` matrice.</span><span class="sxs-lookup"><span data-stu-id="ca04e-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="ca04e-107">out Puntatore a un oggetto `ULONG32` che riceve le dimensioni del buffer necessarie per contenere le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="ca04e-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="ca04e-108">out Matrice che riceve le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="ca04e-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca04e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ca04e-109">Return Value</span></span>  
 <span data-ttu-id="ca04e-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ca04e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca04e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca04e-111">Requirements</span></span>  
 <span data-ttu-id="ca04e-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ca04e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca04e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca04e-113">See also</span></span>

- [<span data-ttu-id="ca04e-114">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="ca04e-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)

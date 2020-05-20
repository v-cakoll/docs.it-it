---
title: Metodo ISymUnmanagedNamespace::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: 84b2f1226c84713483499c7ff777838058cb0f95
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615111"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="1e540-102">Metodo ISymUnmanagedNamespace::GetName</span><span class="sxs-lookup"><span data-stu-id="1e540-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="1e540-103">Ottiene il nome di questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1e540-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e540-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e540-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e540-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e540-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1e540-106">in Oggetto `ULONG32` che indica le dimensioni del `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="1e540-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1e540-107">out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere il nome dello spazio dei nomi, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="1e540-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="1e540-108">out Puntatore a un buffer contenente il nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1e540-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e540-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1e540-109">Return Value</span></span>  
 <span data-ttu-id="1e540-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1e540-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e540-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e540-111">Requirements</span></span>  
 <span data-ttu-id="1e540-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1e540-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e540-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e540-113">See also</span></span>

- [<span data-ttu-id="1e540-114">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="1e540-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)

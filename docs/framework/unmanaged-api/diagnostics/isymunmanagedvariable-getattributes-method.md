---
title: Metodo ISymUnmanagedVariable::GetAttributes
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
ms.openlocfilehash: 29869abdd39f61c6c9cb51d6b2be50fa462c5b70
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615254"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="0a5e6-102">Metodo ISymUnmanagedVariable::GetAttributes</span><span class="sxs-lookup"><span data-stu-id="0a5e6-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="0a5e6-103">Ottiene i flag di attributo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a5e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a5e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a5e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a5e6-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0a5e6-106">out Puntatore a un oggetto `ULONG32` che riceve gli attributi.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="0a5e6-107">Il valore restituito sarà uno dei valori definiti nell'enumerazione [CorSymVarFlag](corsymvarflag-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="0a5e6-107">The returned value will be one of the values defined in the [CorSymVarFlag](corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a5e6-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0a5e6-108">Return Value</span></span>  
 <span data-ttu-id="0a5e6-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a5e6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a5e6-110">Requirements</span></span>  
 <span data-ttu-id="0a5e6-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0a5e6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a5e6-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a5e6-112">See also</span></span>

- [<span data-ttu-id="0a5e6-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="0a5e6-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d1585ccfa560d31fc32dce2f39dd525c51711797
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466336"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="ce75a-102">Metodo ISymUnmanagedVariable::GetAttributes</span><span class="sxs-lookup"><span data-stu-id="ce75a-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="ce75a-103">Ottiene i flag di attributo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="ce75a-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce75a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce75a-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce75a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce75a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ce75a-106">[out] Un puntatore a un `ULONG32` che riceve gli attributi.</span><span class="sxs-lookup"><span data-stu-id="ce75a-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="ce75a-107">Il valore restituito sarà uno dei valori definiti nel [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ce75a-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce75a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ce75a-108">Return Value</span></span>  
 <span data-ttu-id="ce75a-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ce75a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce75a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce75a-110">Requirements</span></span>  
 <span data-ttu-id="ce75a-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ce75a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce75a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce75a-112">See also</span></span>
- [<span data-ttu-id="ce75a-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="ce75a-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)

---
title: Metodo ISymUnmanagedVariable::GetAttributes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAttributes
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 41bdbf20d3905ba218802a6801c7394b237f6e0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="ab49d-102">Metodo ISymUnmanagedVariable::GetAttributes</span><span class="sxs-lookup"><span data-stu-id="ab49d-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="ab49d-103">Ottiene i flag di attributo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="ab49d-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab49d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab49d-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab49d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab49d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ab49d-106">[out] Un puntatore a un `ULONG32` che riceve gli attributi.</span><span class="sxs-lookup"><span data-stu-id="ab49d-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="ab49d-107">Il valore restituito sarà uno dei valori definiti nel [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ab49d-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab49d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ab49d-108">Return Value</span></span>  
 <span data-ttu-id="ab49d-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ab49d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab49d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab49d-110">Requirements</span></span>  
 <span data-ttu-id="ab49d-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ab49d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab49d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab49d-112">See Also</span></span>  
 [<span data-ttu-id="ab49d-113">ISymUnmanagedVariable (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ab49d-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)

---
title: Metodo ISymUnmanagedVariable::GetAddressKind
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAddressKind
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c4651641e3c430379b11698acf29eae450b02b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="1a2c6-102">Metodo ISymUnmanagedVariable::GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="1a2c6-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="1a2c6-103">Ottiene il tipo di indirizzo della variabile.</span><span class="sxs-lookup"><span data-stu-id="1a2c6-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a2c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a2c6-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a2c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a2c6-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1a2c6-106">[out] Un puntatore a un `ULONG32` che riceve il valore.</span><span class="sxs-lookup"><span data-stu-id="1a2c6-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="1a2c6-107">I valori possibili sono definiti nel [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1a2c6-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a2c6-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1a2c6-108">Return Value</span></span>  
 <span data-ttu-id="1a2c6-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1a2c6-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a2c6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a2c6-110">Requirements</span></span>  
 <span data-ttu-id="1a2c6-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1a2c6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a2c6-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a2c6-112">See Also</span></span>  
 [<span data-ttu-id="1a2c6-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="1a2c6-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)

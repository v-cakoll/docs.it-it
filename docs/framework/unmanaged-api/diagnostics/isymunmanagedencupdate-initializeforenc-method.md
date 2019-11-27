---
title: Metodo ISymUnmanagedENCUpdate::InitializeForEnc
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
ms.openlocfilehash: 220788a38cd0ff90fed3b681a161c579206cf805
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449027"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="efaf5-102">Metodo ISymUnmanagedENCUpdate::InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="efaf5-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="efaf5-103">Consente il calcolo dei limiti del metodo prima della prima chiamata al metodo [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="efaf5-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efaf5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efaf5-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="efaf5-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="efaf5-105">Return Value</span></span>  
 <span data-ttu-id="efaf5-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="efaf5-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efaf5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="efaf5-107">Requirements</span></span>  
 <span data-ttu-id="efaf5-108">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="efaf5-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efaf5-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efaf5-109">See also</span></span>

- [<span data-ttu-id="efaf5-110">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="efaf5-110">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

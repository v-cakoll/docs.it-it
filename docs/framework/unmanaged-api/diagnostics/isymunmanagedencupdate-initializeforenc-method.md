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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 135ae21c2281c545aa701ac2a22a43cea63f5242
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939711"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="e4692-102">Metodo ISymUnmanagedENCUpdate::InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="e4692-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="e4692-103">Consente i limiti del metodo deve essere calcolata prima della prima chiamata per il [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="e4692-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4692-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4692-104">Syntax</span></span>  
  
```  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e4692-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e4692-105">Return Value</span></span>  
 <span data-ttu-id="e4692-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e4692-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4692-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4692-107">Requirements</span></span>  
 <span data-ttu-id="e4692-108">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e4692-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4692-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4692-109">See also</span></span>

- [<span data-ttu-id="e4692-110">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="e4692-110">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

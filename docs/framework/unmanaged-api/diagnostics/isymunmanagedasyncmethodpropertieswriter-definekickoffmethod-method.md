---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce3c135e031d0c8425e990811fedc40f4ec45243
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226612"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="d61ab-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="d61ab-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="d61ab-103">Imposta il metodo inizio che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="d61ab-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d61ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d61ab-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d61ab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d61ab-105">Parameters</span></span>  
  
|<span data-ttu-id="d61ab-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="d61ab-106">Parameter</span></span>|<span data-ttu-id="d61ab-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d61ab-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="d61ab-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d61ab-108">Return Value</span></span>  
 <span data-ttu-id="d61ab-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="d61ab-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d61ab-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d61ab-110">Requirements</span></span>  
 <span data-ttu-id="d61ab-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d61ab-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d61ab-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d61ab-112">See also</span></span>

- [<span data-ttu-id="d61ab-113">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="d61ab-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

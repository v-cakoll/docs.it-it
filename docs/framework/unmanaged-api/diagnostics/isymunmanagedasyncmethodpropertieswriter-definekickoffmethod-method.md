---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce3c135e031d0c8425e990811fedc40f4ec45243
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940114"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="1b0cf-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="1b0cf-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="1b0cf-103">Imposta il metodo inizio che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="1b0cf-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b0cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b0cf-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b0cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b0cf-105">Parameters</span></span>  
  
|<span data-ttu-id="1b0cf-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="1b0cf-106">Parameter</span></span>|<span data-ttu-id="1b0cf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b0cf-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="1b0cf-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1b0cf-108">Return Value</span></span>  
 <span data-ttu-id="1b0cf-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="1b0cf-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b0cf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b0cf-110">Requirements</span></span>  
 <span data-ttu-id="1b0cf-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1b0cf-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0cf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b0cf-112">See also</span></span>

- [<span data-ttu-id="1b0cf-113">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="1b0cf-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

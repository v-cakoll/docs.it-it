---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24560ed4b0bb7ca04d5859280baa594fbb2e4097
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473467"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="5ab06-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="5ab06-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="5ab06-103">Imposta il metodo inizio che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="5ab06-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab06-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ab06-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab06-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5ab06-105">Parameters</span></span>  
  
|<span data-ttu-id="5ab06-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="5ab06-106">Parameter</span></span>|<span data-ttu-id="5ab06-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ab06-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="5ab06-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5ab06-108">Return Value</span></span>  
 <span data-ttu-id="5ab06-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="5ab06-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab06-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ab06-110">Requirements</span></span>  
 <span data-ttu-id="5ab06-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5ab06-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab06-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ab06-112">See also</span></span>
- [<span data-ttu-id="5ab06-113">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="5ab06-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

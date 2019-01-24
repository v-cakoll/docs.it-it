---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b4564aeb3c8ed4674e755e5691bb0a9d417bca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624176"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="80289-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="80289-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="80289-103">Imposta il metodo inizio che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="80289-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80289-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80289-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80289-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80289-105">Parameters</span></span>  
  
|<span data-ttu-id="80289-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="80289-106">Parameter</span></span>|<span data-ttu-id="80289-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80289-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="80289-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="80289-108">Return Value</span></span>  
 <span data-ttu-id="80289-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="80289-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80289-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80289-110">Requirements</span></span>  
 <span data-ttu-id="80289-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="80289-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80289-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80289-112">See also</span></span>
- [<span data-ttu-id="80289-113">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="80289-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 691a46e20339b659b5df3136d4dca6c03a69d3d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="be02c-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="be02c-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="be02c-103">Imposta il metodo di avvio che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="be02c-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be02c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be02c-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be02c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be02c-105">Parameters</span></span>  
  
|<span data-ttu-id="be02c-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="be02c-106">Parameter</span></span>|<span data-ttu-id="be02c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be02c-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="be02c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="be02c-108">Return Value</span></span>  
 <span data-ttu-id="be02c-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="be02c-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be02c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be02c-110">Requirements</span></span>  
 <span data-ttu-id="be02c-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="be02c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be02c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be02c-112">See Also</span></span>  
 [<span data-ttu-id="be02c-113">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="be02c-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

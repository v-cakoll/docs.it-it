---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a476d92486d7f2523dfbcc8b25e9c11e26c55f2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425615"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="97374-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="97374-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="97374-103">Imposta il metodo di avvio che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="97374-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97374-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97374-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97374-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97374-105">Parameters</span></span>  
  
|<span data-ttu-id="97374-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="97374-106">Parameter</span></span>|<span data-ttu-id="97374-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97374-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="97374-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97374-108">Return Value</span></span>  
 <span data-ttu-id="97374-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="97374-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97374-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97374-110">Requirements</span></span>  
 <span data-ttu-id="97374-111">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="97374-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97374-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97374-112">See Also</span></span>  
 [<span data-ttu-id="97374-113">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="97374-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

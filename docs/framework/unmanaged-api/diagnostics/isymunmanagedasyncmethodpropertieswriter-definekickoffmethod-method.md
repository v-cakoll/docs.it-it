---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: ccf1287a1b0218e7f2560e1afbb0930c93b43263
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129168"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="76af8-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="76af8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="76af8-103">Imposta il metodo iniziale che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="76af8-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76af8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76af8-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76af8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="76af8-105">Parameters</span></span>  
  
|<span data-ttu-id="76af8-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="76af8-106">Parameter</span></span>|<span data-ttu-id="76af8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76af8-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="76af8-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="76af8-108">Return Value</span></span>  
 <span data-ttu-id="76af8-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="76af8-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76af8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76af8-110">Requirements</span></span>  
 <span data-ttu-id="76af8-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="76af8-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76af8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76af8-112">See also</span></span>

- [<span data-ttu-id="76af8-113">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="76af8-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

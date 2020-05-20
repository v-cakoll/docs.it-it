---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: c35455fc679d79d56814a9c2f026ec395e944f24
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441721"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="517c2-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="517c2-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="517c2-103">Imposta il metodo iniziale che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="517c2-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="517c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="517c2-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="517c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="517c2-105">Parameters</span></span>  
  
|<span data-ttu-id="517c2-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="517c2-106">Parameter</span></span>|<span data-ttu-id="517c2-107">Description</span><span class="sxs-lookup"><span data-stu-id="517c2-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="517c2-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="517c2-108">Return Value</span></span>  
 <span data-ttu-id="517c2-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="517c2-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="517c2-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="517c2-110">Requirements</span></span>  
 <span data-ttu-id="517c2-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="517c2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="517c2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="517c2-112">See also</span></span>

- [<span data-ttu-id="517c2-113">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="517c2-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)

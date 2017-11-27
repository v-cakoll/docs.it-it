---
title: Metodo CloseAssembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location: alink.dll
api_type: COM
f1_keywords: CloseAssembly
helpviewer_keywords: CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be68348b619f342eca4841a6052088bf7152f453
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="closeassembly-method"></a><span data-ttu-id="30635-102">Metodo CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="30635-102">CloseAssembly Method</span></span>
<span data-ttu-id="30635-103">Consente di finalizzare le operazioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="30635-103">Finalizes assembly operations.</span></span> <span data-ttu-id="30635-104">Chiamare questo metodo prima di iniziare un nuovo assembly o il modulo non associato.</span><span class="sxs-lookup"><span data-stu-id="30635-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30635-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30635-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30635-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="30635-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="30635-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="30635-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30635-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="30635-108">Return Value</span></span>  
 <span data-ttu-id="30635-109">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="30635-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30635-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30635-110">Requirements</span></span>  
 <span data-ttu-id="30635-111">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="30635-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30635-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30635-112">See Also</span></span>  
 [<span data-ttu-id="30635-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="30635-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="30635-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="30635-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="30635-115">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="30635-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

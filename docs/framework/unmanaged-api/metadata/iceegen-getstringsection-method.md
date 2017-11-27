---
title: Metodo ICeeGen::GetStringSection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetStringSection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce511b4610a6ff681eb70bfeb6a7a7afe162818e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="d667b-102">Metodo ICeeGen::GetStringSection</span><span class="sxs-lookup"><span data-stu-id="d667b-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="d667b-103">Ottiene una rappresentazione di stringa della sezione di codice a cui fa riferimento l'handle specificato.</span><span class="sxs-lookup"><span data-stu-id="d667b-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="d667b-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d667b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d667b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d667b-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d667b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d667b-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="d667b-107">[in, out] Handle alla sezione di codice.</span><span class="sxs-lookup"><span data-stu-id="d667b-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d667b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d667b-108">Requirements</span></span>  
 <span data-ttu-id="d667b-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d667b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d667b-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d667b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d667b-111">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d667b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d667b-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d667b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d667b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d667b-113">See Also</span></span>  
 [<span data-ttu-id="d667b-114">ICeeGen (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d667b-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

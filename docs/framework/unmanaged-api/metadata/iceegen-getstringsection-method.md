---
title: Metodo ICeeGen::GetStringSection
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68dc80c657c3794a416f6e142f70cfb05bee2c77
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745897"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="8106b-102">Metodo ICeeGen::GetStringSection</span><span class="sxs-lookup"><span data-stu-id="8106b-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="8106b-103">Ottiene una rappresentazione di stringa della sezione di codice fa riferimento l'handle specificato.</span><span class="sxs-lookup"><span data-stu-id="8106b-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="8106b-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="8106b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8106b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8106b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8106b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8106b-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="8106b-107">[in, out] Handle per la sezione di codice.</span><span class="sxs-lookup"><span data-stu-id="8106b-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8106b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8106b-108">Requirements</span></span>  
 <span data-ttu-id="8106b-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8106b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8106b-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8106b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8106b-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8106b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8106b-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8106b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8106b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8106b-113">See also</span></span>

- [<span data-ttu-id="8106b-114">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="8106b-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

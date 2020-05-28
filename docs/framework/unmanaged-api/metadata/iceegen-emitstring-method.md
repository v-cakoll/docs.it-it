---
title: Metodo ICeeGen::EmitString
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
ms.openlocfilehash: e7c58e6cdbe0d3c8513721a40eaa3fdfcec6ce2e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008859"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="06406-102">Metodo ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="06406-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="06406-103">Genera la stringa specificata nella codebase.</span><span class="sxs-lookup"><span data-stu-id="06406-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="06406-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="06406-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06406-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06406-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06406-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="06406-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="06406-107">in Stringa da creare.</span><span class="sxs-lookup"><span data-stu-id="06406-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="06406-108">out Indirizzo virtuale relativo della stringa generata.</span><span class="sxs-lookup"><span data-stu-id="06406-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06406-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06406-109">Requirements</span></span>  
 <span data-ttu-id="06406-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06406-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06406-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="06406-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06406-112">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="06406-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06406-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06406-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06406-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06406-114">See also</span></span>

- [<span data-ttu-id="06406-115">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="06406-115">ICeeGen Interface</span></span>](iceegen-interface.md)

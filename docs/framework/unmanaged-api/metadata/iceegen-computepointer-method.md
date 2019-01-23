---
title: Metodo ICeeGen::ComputePointer
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 496082bbf89ceb93ba3dceef9a9222425db71784
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522414"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="9cdc0-102">Metodo ICeeGen::ComputePointer</span><span class="sxs-lookup"><span data-stu-id="9cdc0-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="9cdc0-103">Determina il buffer per la sezione di codice specificato.</span><span class="sxs-lookup"><span data-stu-id="9cdc0-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="9cdc0-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9cdc0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cdc0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9cdc0-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cdc0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9cdc0-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="9cdc0-107">[in] La sezione di codice per cui restituire un buffer.</span><span class="sxs-lookup"><span data-stu-id="9cdc0-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="9cdc0-108">[in] L'indirizzo virtuale relativo del metodo per cui ottenere un puntatore.</span><span class="sxs-lookup"><span data-stu-id="9cdc0-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="9cdc0-109">[out] Puntatore al buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="9cdc0-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cdc0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9cdc0-110">Requirements</span></span>  
 <span data-ttu-id="9cdc0-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cdc0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cdc0-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9cdc0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9cdc0-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9cdc0-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9cdc0-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cdc0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cdc0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cdc0-115">See also</span></span>
- [<span data-ttu-id="9cdc0-116">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="9cdc0-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

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
ms.openlocfilehash: 5741ba1b4564a703ff57b45c728bb9efac0bb35a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782013"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="b5335-102">Metodo ICeeGen::ComputePointer</span><span class="sxs-lookup"><span data-stu-id="b5335-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="b5335-103">Determina il buffer per la sezione di codice specificato.</span><span class="sxs-lookup"><span data-stu-id="b5335-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="b5335-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b5335-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5335-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5335-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5335-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5335-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b5335-107">[in] La sezione di codice per cui restituire un buffer.</span><span class="sxs-lookup"><span data-stu-id="b5335-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="b5335-108">[in] L'indirizzo virtuale relativo del metodo per cui ottenere un puntatore.</span><span class="sxs-lookup"><span data-stu-id="b5335-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="b5335-109">[out] Puntatore al buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="b5335-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5335-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5335-110">Requirements</span></span>  
 <span data-ttu-id="b5335-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5335-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5335-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b5335-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5335-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b5335-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5335-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5335-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5335-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5335-115">See also</span></span>

- [<span data-ttu-id="b5335-116">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="b5335-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

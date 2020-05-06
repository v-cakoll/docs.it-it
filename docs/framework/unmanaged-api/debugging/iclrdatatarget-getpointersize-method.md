---
title: Metodo ICLRDataTarget::GetPointerSize
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
ms.openlocfilehash: e6c4d5f8cc911198add176cab9c4b9b89128068e
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860620"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="10afe-102">Metodo ICLRDataTarget::GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="10afe-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="10afe-103">Ottiene la dimensione, in byte, del tipo di puntatore utilizzato dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="10afe-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="10afe-104">Questo metodo viene chiamato dal servizio di accesso ai dati Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="10afe-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10afe-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10afe-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10afe-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="10afe-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="10afe-107">out Puntatore a un valore integer che specifica la dimensione, in byte, di un puntatore nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="10afe-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10afe-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="10afe-108">Remarks</span></span>  
 <span data-ttu-id="10afe-109">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="10afe-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10afe-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10afe-110">Requirements</span></span>  
 <span data-ttu-id="10afe-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10afe-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10afe-112">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="10afe-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="10afe-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10afe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10afe-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10afe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10afe-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10afe-115">See also</span></span>

- [<span data-ttu-id="10afe-116">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="10afe-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)

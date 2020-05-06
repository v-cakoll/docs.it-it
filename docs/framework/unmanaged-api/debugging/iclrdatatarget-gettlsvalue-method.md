---
title: Metodo ICLRDataTarget::GetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
ms.openlocfilehash: 141dc8632812ab4a2ce82864cde56337025baa28
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860578"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="5cc2e-102">Metodo ICLRDataTarget::GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="5cc2e-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="5cc2e-103">Ottiene un valore dall'archiviazione locale di thread (TLS) del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5cc2e-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="5cc2e-104">Questo metodo viene chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5cc2e-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc2e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cc2e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cc2e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5cc2e-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="5cc2e-107">in Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5cc2e-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="5cc2e-108">in Indice della posizione.</span><span class="sxs-lookup"><span data-stu-id="5cc2e-108">[in] The index of the location.</span></span> <span data-ttu-id="5cc2e-109">Questo valore deve essere un indice valido nell'archivio locale del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="5cc2e-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="5cc2e-110">out Puntatore a un `CLRDATA_ADDRESS` valore che specifica il valore restituito dal percorso TLS specificato.</span><span class="sxs-lookup"><span data-stu-id="5cc2e-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cc2e-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5cc2e-111">Remarks</span></span>  
 <span data-ttu-id="5cc2e-112">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="5cc2e-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc2e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cc2e-113">Requirements</span></span>  
 <span data-ttu-id="5cc2e-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cc2e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cc2e-115">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="5cc2e-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5cc2e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cc2e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cc2e-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cc2e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc2e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cc2e-118">See also</span></span>

- [<span data-ttu-id="5cc2e-119">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="5cc2e-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)

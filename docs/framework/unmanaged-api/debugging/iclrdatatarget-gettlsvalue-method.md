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
ms.openlocfilehash: d4e7c055480ea611357d5d3e18ac4306acf4d0b0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785410"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="b97c6-102">Metodo ICLRDataTarget::GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="b97c6-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="b97c6-103">Ottiene un valore dall'archiviazione locale di thread (TLS) del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b97c6-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="b97c6-104">Questo metodo viene chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b97c6-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b97c6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b97c6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b97c6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b97c6-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="b97c6-107">in Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b97c6-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="b97c6-108">in Indice della posizione.</span><span class="sxs-lookup"><span data-stu-id="b97c6-108">[in] The index of the location.</span></span> <span data-ttu-id="b97c6-109">Questo valore deve essere un indice valido nell'archivio locale del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="b97c6-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="b97c6-110">out Puntatore a un valore `CLRDATA_ADDRESS` che specifica il valore restituito dal percorso TLS specificato.</span><span class="sxs-lookup"><span data-stu-id="b97c6-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b97c6-111">Note</span><span class="sxs-lookup"><span data-stu-id="b97c6-111">Remarks</span></span>  
 <span data-ttu-id="b97c6-112">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="b97c6-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b97c6-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b97c6-113">Requirements</span></span>  
 <span data-ttu-id="b97c6-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b97c6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b97c6-115">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="b97c6-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b97c6-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b97c6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b97c6-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b97c6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b97c6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b97c6-118">See also</span></span>

- [<span data-ttu-id="b97c6-119">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="b97c6-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)

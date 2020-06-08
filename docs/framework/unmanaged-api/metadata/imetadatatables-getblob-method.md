---
title: Metodo IMetaDataTables::GetBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: ff97e419c5309fa7cb820cb7e82db96fee34f30c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501274"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="cdd98-102">Metodo IMetaDataTables::GetBlob</span><span class="sxs-lookup"><span data-stu-id="cdd98-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="cdd98-103">Ottiene un puntatore all'oggetto binario di grandi dimensioni (BLOB) in corrispondenza dell'indice di colonna specificato.</span><span class="sxs-lookup"><span data-stu-id="cdd98-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdd98-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cdd98-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdd98-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cdd98-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="cdd98-106">in Indirizzo di memoria da cui ottenere `ppData` .</span><span class="sxs-lookup"><span data-stu-id="cdd98-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="cdd98-107">out Puntatore alla dimensione, in byte, di `ppData` .</span><span class="sxs-lookup"><span data-stu-id="cdd98-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="cdd98-108">out Puntatore a un puntatore ai dati binari recuperati.</span><span class="sxs-lookup"><span data-stu-id="cdd98-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdd98-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cdd98-109">Requirements</span></span>  
 <span data-ttu-id="cdd98-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdd98-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdd98-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cdd98-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cdd98-112">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cdd98-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cdd98-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdd98-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd98-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdd98-114">See also</span></span>

- [<span data-ttu-id="cdd98-115">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="cdd98-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="cdd98-116">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="cdd98-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

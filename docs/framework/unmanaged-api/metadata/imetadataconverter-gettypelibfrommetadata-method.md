---
title: Metodo IMetaDataConverter::GetTypeLibFromMetaData
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: ef573eb9a572c27e685289b2740a55e898be2093
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177637"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="f7568-102">Metodo IMetaDataConverter::GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="f7568-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="f7568-103">Ottiene un puntatore a un'istanza `ITypeLib` che rappresenta la libreria dei tipi con i nomi di libreria e modulo specificati.</span><span class="sxs-lookup"><span data-stu-id="f7568-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7568-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7568-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7568-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7568-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="f7568-106">[in] Nome del modulo della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="f7568-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="f7568-107">[in] Nome della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="f7568-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="f7568-108">[fuori] Puntatore a una posizione che riceve `ITypeLib` l'indirizzo dell'istanza che rappresenta la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="f7568-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7568-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7568-109">Requirements</span></span>  
 <span data-ttu-id="f7568-110">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7568-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7568-111">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f7568-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7568-112">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f7568-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7568-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7568-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7568-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7568-114">See also</span></span>

- [<span data-ttu-id="f7568-115">Interfaccia IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="f7568-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)

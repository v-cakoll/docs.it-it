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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 208dd5ff2ba9eb450cac5a9807f0cd09852d5cf3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777827"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="dc559-102">Metodo IMetaDataConverter::GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="dc559-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="dc559-103">Ottiene un puntatore a un `ITypeLib` istanza che rappresenta la libreria dei tipi con i nomi di libreria e il modulo specificati.</span><span class="sxs-lookup"><span data-stu-id="dc559-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc559-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc559-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc559-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dc559-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="dc559-106">[in] Il nome del modulo della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="dc559-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="dc559-107">[in] Il nome della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="dc559-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="dc559-108">[out] Un puntatore a una posizione che riceve l'indirizzo del `ITypeLib` istanza che rappresenta la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="dc559-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc559-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc559-109">Requirements</span></span>  
 <span data-ttu-id="dc559-110">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc559-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc559-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dc559-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc559-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="dc559-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc559-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc559-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc559-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc559-114">See also</span></span>

- [<span data-ttu-id="dc559-115">Interfaccia IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="dc559-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)

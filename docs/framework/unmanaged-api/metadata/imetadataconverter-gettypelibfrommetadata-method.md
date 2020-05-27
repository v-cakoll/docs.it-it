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
ms.openlocfilehash: 79bd8901641ee587e94861c0aec85b812591ea48
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008417"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="01286-102">Metodo IMetaDataConverter::GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="01286-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="01286-103">Ottiene un puntatore a un' `ITypeLib` istanza di che rappresenta la libreria dei tipi con la libreria e i nomi dei moduli specificati.</span><span class="sxs-lookup"><span data-stu-id="01286-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01286-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01286-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01286-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01286-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="01286-106">in Nome del modulo della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="01286-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="01286-107">in Nome della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="01286-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="01286-108">out Puntatore a una posizione che riceve l'indirizzo dell'istanza di `ITypeLib` che rappresenta la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="01286-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01286-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01286-109">Requirements</span></span>  
 <span data-ttu-id="01286-110">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01286-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01286-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="01286-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01286-112">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="01286-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01286-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01286-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01286-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01286-114">See also</span></span>

- [<span data-ttu-id="01286-115">Interfaccia IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="01286-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)

---
title: Metodo IMetaDataImport::GetModuleFromScope
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
ms.openlocfilehash: 4e2b2501b6b7117cefcfa43511ef20f25106bb42
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503585"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="4a8c5-102">Metodo IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="4a8c5-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="4a8c5-103">Ottiene un token di metadati per il modulo a cui si fa riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="4a8c5-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a8c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a8c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a8c5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a8c5-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="4a8c5-106">out Puntatore al token che rappresenta il modulo a cui si fa riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="4a8c5-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a8c5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a8c5-107">Requirements</span></span>  
 <span data-ttu-id="4a8c5-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a8c5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a8c5-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4a8c5-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a8c5-110">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a8c5-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a8c5-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a8c5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8c5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a8c5-112">See also</span></span>

- [<span data-ttu-id="4a8c5-113">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4a8c5-113">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4a8c5-114">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4a8c5-114">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

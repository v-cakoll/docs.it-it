---
title: Metodo IMetaDataEmit::SetModuleProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: aee258c49e6726ebef990257456fd273b01b9ef0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007845"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="8cdab-102">Metodo IMetaDataEmit::SetModuleProps</span><span class="sxs-lookup"><span data-stu-id="8cdab-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="8cdab-103">Aggiorna i riferimenti a un modulo definito da una chiamata precedente a [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="8cdab-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cdab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cdab-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cdab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8cdab-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="8cdab-106">in Nome del modulo in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="8cdab-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="8cdab-107">Si tratta solo del nome del file e non del percorso completo.</span><span class="sxs-lookup"><span data-stu-id="8cdab-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cdab-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8cdab-108">Requirements</span></span>  
 <span data-ttu-id="8cdab-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cdab-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cdab-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8cdab-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8cdab-111">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8cdab-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8cdab-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cdab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cdab-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cdab-113">See also</span></span>

- [<span data-ttu-id="8cdab-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8cdab-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8cdab-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8cdab-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

---
title: Metodo IMetaDataAssemblyImport::GetAssemblyFromScope
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
ms.openlocfilehash: adcaac02526c7d72ffb75ba6c7552632173032cf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009041"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="13a65-102">Metodo IMetaDataAssemblyImport::GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="13a65-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="13a65-103">Ottiene un puntatore all'assembly nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="13a65-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13a65-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13a65-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13a65-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="13a65-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="13a65-106">out Puntatore al `mdAssembly` token recuperato che identifica l'assembly.</span><span class="sxs-lookup"><span data-stu-id="13a65-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13a65-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13a65-107">Requirements</span></span>  
 <span data-ttu-id="13a65-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13a65-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13a65-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="13a65-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13a65-110">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="13a65-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13a65-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13a65-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a65-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13a65-112">See also</span></span>

- [<span data-ttu-id="13a65-113">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="13a65-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)

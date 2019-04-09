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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d4797c952bfec4e0863e7a12b97e038c7ff8d95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191523"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="2cfe5-102">Metodo IMetaDataAssemblyImport::GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="2cfe5-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="2cfe5-103">Ottiene un puntatore all'assembly nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="2cfe5-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cfe5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2cfe5-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cfe5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2cfe5-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="2cfe5-106">[out] Un puntatore a oggetto recuperato `mdAssembly` token che identifica l'assembly.</span><span class="sxs-lookup"><span data-stu-id="2cfe5-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cfe5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2cfe5-107">Requirements</span></span>  
 <span data-ttu-id="2cfe5-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cfe5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cfe5-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2cfe5-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2cfe5-110">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2cfe5-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="2cfe5-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2cfe5-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2cfe5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cfe5-112">See also</span></span>

- [<span data-ttu-id="2cfe5-113">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="2cfe5-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

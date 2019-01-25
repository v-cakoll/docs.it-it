---
title: Metodo IMetaDataImport::GetParamForMethodIndex
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28d4c9098076699de250ab1c43e5f9e353dc9752
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740112"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="e9077-102">Metodo IMetaDataImport::GetParamForMethodIndex</span><span class="sxs-lookup"><span data-stu-id="e9077-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="e9077-103">Ottiene il token che rappresenta un parametro specificato del metodo rappresentato dal token MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="e9077-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9077-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9077-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9077-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9077-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="e9077-106">[in] Un token che rappresenta il metodo per restituire il token del parametro.</span><span class="sxs-lookup"><span data-stu-id="e9077-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="e9077-107">[in] La posizione ordinale nell'elenco dei parametri in cui è presente il parametro richiesto.</span><span class="sxs-lookup"><span data-stu-id="e9077-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="e9077-108">I parametri sono numerati a partire da uno, con valore restituito del metodo nella posizione zero.</span><span class="sxs-lookup"><span data-stu-id="e9077-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="e9077-109">[out] Puntatore a un token ParamDef che rappresenta il parametro richiesto.</span><span class="sxs-lookup"><span data-stu-id="e9077-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9077-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9077-110">Requirements</span></span>  
 <span data-ttu-id="e9077-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9077-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9077-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9077-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9077-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e9077-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9077-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9077-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9077-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9077-115">See also</span></span>
- [<span data-ttu-id="e9077-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e9077-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e9077-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e9077-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

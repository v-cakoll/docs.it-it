---
title: Metodo IMetaDataImport::GetParamForMethodIndex
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0cedc993e6b8794a15ff9927b06ff650ed76b79e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="fad82-102">Metodo IMetaDataImport::GetParamForMethodIndex</span><span class="sxs-lookup"><span data-stu-id="fad82-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="fad82-103">Ottiene il token che rappresenta un parametro del metodo rappresentato dal token MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="fad82-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fad82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fad82-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fad82-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fad82-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="fad82-106">[in] Un token che rappresenta il metodo per restituire il token del parametro.</span><span class="sxs-lookup"><span data-stu-id="fad82-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="fad82-107">[in] La posizione ordinale nell'elenco di parametri in cui si verifica il parametro richiesto.</span><span class="sxs-lookup"><span data-stu-id="fad82-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="fad82-108">I parametri sono numerati a partire da uno, con il valore restituito del metodo nella posizione zero.</span><span class="sxs-lookup"><span data-stu-id="fad82-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="fad82-109">[out] Puntatore a un token ParamDef che rappresenta il parametro richiesto.</span><span class="sxs-lookup"><span data-stu-id="fad82-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fad82-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fad82-110">Requirements</span></span>  
 <span data-ttu-id="fad82-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fad82-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fad82-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fad82-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fad82-113">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fad82-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fad82-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fad82-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad82-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fad82-115">See Also</span></span>  
 [<span data-ttu-id="fad82-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="fad82-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="fad82-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="fad82-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

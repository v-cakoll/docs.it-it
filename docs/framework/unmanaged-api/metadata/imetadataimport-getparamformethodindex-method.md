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
ms.openlocfilehash: a70691b9c519bc59ae7df7a86d5d6697db565575
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437168"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="1221b-102">Metodo IMetaDataImport::GetParamForMethodIndex</span><span class="sxs-lookup"><span data-stu-id="1221b-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="1221b-103">Ottiene il token che rappresenta un parametro specificato del metodo rappresentato dal token MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="1221b-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1221b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1221b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1221b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1221b-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="1221b-106">in Token che rappresenta il metodo per il quale restituire il token di parametro.</span><span class="sxs-lookup"><span data-stu-id="1221b-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="1221b-107">in Posizione ordinale nell'elenco di parametri in cui si verifica il parametro richiesto.</span><span class="sxs-lookup"><span data-stu-id="1221b-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="1221b-108">I parametri sono numerati a partire da uno, con il valore restituito del metodo nella posizione zero.</span><span class="sxs-lookup"><span data-stu-id="1221b-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="1221b-109">out Puntatore a un token ParamDef che rappresenta il parametro richiesto.</span><span class="sxs-lookup"><span data-stu-id="1221b-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1221b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1221b-110">Requirements</span></span>  
 <span data-ttu-id="1221b-111">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1221b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1221b-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1221b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1221b-113">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1221b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1221b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1221b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1221b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1221b-115">See also</span></span>

- [<span data-ttu-id="1221b-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1221b-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1221b-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1221b-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

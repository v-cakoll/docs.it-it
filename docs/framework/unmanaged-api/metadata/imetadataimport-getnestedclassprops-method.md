---
title: Metodo IMetaDataImport::GetNestedClassProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
ms.openlocfilehash: 0adf4f91e1bc7bfb72f634cb3bf038710198b74f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437134"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="21275-102">Metodo IMetaDataImport::GetNestedClassProps</span><span class="sxs-lookup"><span data-stu-id="21275-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="21275-103">Ottiene il token TypeDef per la <xref:System.Type> padre del tipo annidato specificato.</span><span class="sxs-lookup"><span data-stu-id="21275-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21275-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21275-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21275-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="21275-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="21275-106">in Token TypeDef che rappresenta il <xref:System.Type> per cui restituire il token della classe padre.</span><span class="sxs-lookup"><span data-stu-id="21275-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="21275-107">out Puntatore al token TypeDef per la <xref:System.Type> che `tdNestedClass` è annidato in.</span><span class="sxs-lookup"><span data-stu-id="21275-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21275-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21275-108">Requirements</span></span>  
 <span data-ttu-id="21275-109">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21275-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21275-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="21275-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21275-111">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="21275-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21275-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21275-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21275-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21275-113">See also</span></span>

- [<span data-ttu-id="21275-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="21275-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="21275-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="21275-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

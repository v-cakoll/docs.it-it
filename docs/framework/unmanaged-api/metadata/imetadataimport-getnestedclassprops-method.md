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
ms.openlocfilehash: 82cf5e14520f0e677c2d274cf013d8a0020e8fa2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503536"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="e8410-102">Metodo IMetaDataImport::GetNestedClassProps</span><span class="sxs-lookup"><span data-stu-id="e8410-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="e8410-103">Ottiene il token TypeDef per l'elemento padre <xref:System.Type> del tipo annidato specificato.</span><span class="sxs-lookup"><span data-stu-id="e8410-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8410-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8410-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8410-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8410-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="e8410-106">in Token TypeDef che rappresenta l'oggetto per il quale <xref:System.Type> restituire il token della classe padre.</span><span class="sxs-lookup"><span data-stu-id="e8410-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="e8410-107">out Puntatore al token TypeDef per l'oggetto <xref:System.Type> `tdNestedClass` annidato in.</span><span class="sxs-lookup"><span data-stu-id="e8410-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8410-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8410-108">Requirements</span></span>  
 <span data-ttu-id="e8410-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8410-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8410-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e8410-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8410-111">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e8410-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8410-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8410-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8410-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8410-113">See also</span></span>

- [<span data-ttu-id="e8410-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e8410-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e8410-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e8410-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

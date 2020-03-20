---
title: Metodo IMetaDataImport::GetInterfaceImplProps
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175382"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="a2a97-102">Metodo IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="a2a97-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="a2a97-103">Ottiene un puntatore ai <xref:System.Type> token di metadati per il che implementa il metodo specificato e per l'interfaccia che dichiara tale metodo.</span><span class="sxs-lookup"><span data-stu-id="a2a97-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="a2a97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2a97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2a97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2a97-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="a2a97-106">[in] Token di metadati che rappresenta il metodo per cui restituire la classe e i token di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a2a97-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="a2a97-107">[fuori] Token di metadati che rappresenta la classe che implementa il metodo.</span><span class="sxs-lookup"><span data-stu-id="a2a97-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="a2a97-108">[fuori] Token di metadati che rappresenta l'interfaccia che definisce il metodo implementato.</span><span class="sxs-lookup"><span data-stu-id="a2a97-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="a2a97-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a2a97-109">Remarks</span></span>

 <span data-ttu-id="a2a97-110">È possibile ottenere `iImpl` il valore per chiamando il [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="a2a97-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="a2a97-111">Si supponga, ad esempio, `mdTypeDef` che una classe abbia un valore token pari a 0x02000007 e che implementi tre interfacce i cui tipi dispongono di token:For example, suppose that a class has an token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span><span class="sxs-lookup"><span data-stu-id="a2a97-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="a2a97-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="a2a97-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="a2a97-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="a2a97-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="a2a97-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="a2a97-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="a2a97-115">Concettualmente, queste informazioni vengono archiviate in una tabella di implementazione dell'interfaccia come segue:Conceptually, this information is stored into an interface implementation table as:</span><span class="sxs-lookup"><span data-stu-id="a2a97-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="a2a97-116">Numero di riga</span><span class="sxs-lookup"><span data-stu-id="a2a97-116">Row number</span></span> | <span data-ttu-id="a2a97-117">Token di classe</span><span class="sxs-lookup"><span data-stu-id="a2a97-117">Class token</span></span> | <span data-ttu-id="a2a97-118">Token di interfaccia</span><span class="sxs-lookup"><span data-stu-id="a2a97-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="a2a97-119">4</span><span class="sxs-lookup"><span data-stu-id="a2a97-119">4</span></span>          |             |                 |
| <span data-ttu-id="a2a97-120">5</span><span class="sxs-lookup"><span data-stu-id="a2a97-120">5</span></span>          | <span data-ttu-id="a2a97-121">02000007</span><span class="sxs-lookup"><span data-stu-id="a2a97-121">02000007</span></span>    | <span data-ttu-id="a2a97-122">02000003</span><span class="sxs-lookup"><span data-stu-id="a2a97-122">02000003</span></span>        |
| <span data-ttu-id="a2a97-123">6</span><span class="sxs-lookup"><span data-stu-id="a2a97-123">6</span></span>          | <span data-ttu-id="a2a97-124">02000007</span><span class="sxs-lookup"><span data-stu-id="a2a97-124">02000007</span></span>    | <span data-ttu-id="a2a97-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="a2a97-125">0100000A</span></span>        |
| <span data-ttu-id="a2a97-126">7</span><span class="sxs-lookup"><span data-stu-id="a2a97-126">7</span></span>          |             |                 |
| <span data-ttu-id="a2a97-127">8</span><span class="sxs-lookup"><span data-stu-id="a2a97-127">8</span></span>          | <span data-ttu-id="a2a97-128">02000007</span><span class="sxs-lookup"><span data-stu-id="a2a97-128">02000007</span></span>    | <span data-ttu-id="a2a97-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="a2a97-129">0200001C</span></span>        |

<span data-ttu-id="a2a97-130">Ricordiamo che il token è un valore a 4 byte:Recall, the token is a 4-byte value:</span><span class="sxs-lookup"><span data-stu-id="a2a97-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="a2a97-131">I 3 byte inferiori contengono il numero di riga o RID.</span><span class="sxs-lookup"><span data-stu-id="a2a97-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="a2a97-132">Il byte superiore contiene il tipo di `mdtInterfaceImpl`token – 0x09 per .</span><span class="sxs-lookup"><span data-stu-id="a2a97-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="a2a97-133">`GetInterfaceImplProps`restituisce le informazioni contenute nella riga `iImpl` di cui si fornisce il token nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="a2a97-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="a2a97-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2a97-134">Requirements</span></span>  
 <span data-ttu-id="a2a97-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2a97-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2a97-136">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a2a97-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2a97-137">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2a97-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2a97-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2a97-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a97-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2a97-139">See also</span></span>

- [<span data-ttu-id="a2a97-140">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a2a97-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a2a97-141">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a2a97-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

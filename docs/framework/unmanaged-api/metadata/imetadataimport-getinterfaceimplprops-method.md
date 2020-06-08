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
ms.openlocfilehash: 1c9d9647084aa729817eeeb17ee3f5cd320c0d29
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491244"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="41161-102">Metodo IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="41161-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="41161-103">Ottiene un puntatore ai token di metadati per l'oggetto <xref:System.Type> che implementa il metodo specificato e per l'interfaccia che dichiara il metodo.</span><span class="sxs-lookup"><span data-stu-id="41161-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="41161-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41161-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41161-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="41161-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="41161-106">in Token di metadati che rappresenta il metodo per restituire i token di interfaccia e di classe per.</span><span class="sxs-lookup"><span data-stu-id="41161-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="41161-107">out Token di metadati che rappresenta la classe che implementa il metodo.</span><span class="sxs-lookup"><span data-stu-id="41161-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="41161-108">out Token di metadati che rappresenta l'interfaccia che definisce il metodo implementato.</span><span class="sxs-lookup"><span data-stu-id="41161-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="41161-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="41161-109">Remarks</span></span>

 <span data-ttu-id="41161-110">Per ottenere il valore `iImpl` di, chiamare il metodo [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) .</span><span class="sxs-lookup"><span data-stu-id="41161-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="41161-111">Si supponga, ad esempio, che una classe disponga `mdTypeDef` di un valore token di 0x02000007 e che implementi tre interfacce i cui tipi includono token:</span><span class="sxs-lookup"><span data-stu-id="41161-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="41161-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="41161-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="41161-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="41161-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="41161-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="41161-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="41161-115">Concettualmente, queste informazioni vengono archiviate in una tabella di implementazione dell'interfaccia come:</span><span class="sxs-lookup"><span data-stu-id="41161-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="41161-116">Numero di riga</span><span class="sxs-lookup"><span data-stu-id="41161-116">Row number</span></span> | <span data-ttu-id="41161-117">Token di classe</span><span class="sxs-lookup"><span data-stu-id="41161-117">Class token</span></span> | <span data-ttu-id="41161-118">Token di interfaccia</span><span class="sxs-lookup"><span data-stu-id="41161-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="41161-119">4</span><span class="sxs-lookup"><span data-stu-id="41161-119">4</span></span>          |             |                 |
| <span data-ttu-id="41161-120">5</span><span class="sxs-lookup"><span data-stu-id="41161-120">5</span></span>          | <span data-ttu-id="41161-121">02000007</span><span class="sxs-lookup"><span data-stu-id="41161-121">02000007</span></span>    | <span data-ttu-id="41161-122">02000003</span><span class="sxs-lookup"><span data-stu-id="41161-122">02000003</span></span>        |
| <span data-ttu-id="41161-123">6</span><span class="sxs-lookup"><span data-stu-id="41161-123">6</span></span>          | <span data-ttu-id="41161-124">02000007</span><span class="sxs-lookup"><span data-stu-id="41161-124">02000007</span></span>    | <span data-ttu-id="41161-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="41161-125">0100000A</span></span>        |
| <span data-ttu-id="41161-126">7</span><span class="sxs-lookup"><span data-stu-id="41161-126">7</span></span>          |             |                 |
| <span data-ttu-id="41161-127">8</span><span class="sxs-lookup"><span data-stu-id="41161-127">8</span></span>          | <span data-ttu-id="41161-128">02000007</span><span class="sxs-lookup"><span data-stu-id="41161-128">02000007</span></span>    | <span data-ttu-id="41161-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="41161-129">0200001C</span></span>        |

<span data-ttu-id="41161-130">Si ricordi che il token è un valore a 4 byte:</span><span class="sxs-lookup"><span data-stu-id="41161-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="41161-131">I 3 byte inferiori contengono il numero di riga o il RID.</span><span class="sxs-lookup"><span data-stu-id="41161-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="41161-132">Il byte superiore include il tipo di token – 0x09 per `mdtInterfaceImpl` .</span><span class="sxs-lookup"><span data-stu-id="41161-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="41161-133">`GetInterfaceImplProps`Restituisce le informazioni contenute nella riga il cui token è stato fornito nell' `iImpl` argomento.</span><span class="sxs-lookup"><span data-stu-id="41161-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="41161-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41161-134">Requirements</span></span>  
 <span data-ttu-id="41161-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41161-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41161-136">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="41161-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41161-137">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="41161-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41161-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41161-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41161-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41161-139">See also</span></span>

- [<span data-ttu-id="41161-140">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="41161-140">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="41161-141">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="41161-141">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

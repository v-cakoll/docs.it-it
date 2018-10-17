---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: 49a640a666131491366646d6d486d25a515e35bf
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373432"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="c0964-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="c0964-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="c0964-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="c0964-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0964-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0964-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c0964-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c0964-105">Methods</span></span>  
 <span data-ttu-id="c0964-106">La classe MtomMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="c0964-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c0964-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c0964-107">Properties</span></span>  
 <span data-ttu-id="c0964-108">La classe MtomMessageEncodingBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0964-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="c0964-109">Codifica</span><span class="sxs-lookup"><span data-stu-id="c0964-109">Encoding</span></span>  
 <span data-ttu-id="c0964-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c0964-110">Data type: string</span></span>  
  
 <span data-ttu-id="c0964-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c0964-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0964-112">Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.</span><span class="sxs-lookup"><span data-stu-id="c0964-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="c0964-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="c0964-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="c0964-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="c0964-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="c0964-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c0964-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0964-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="c0964-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="c0964-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="c0964-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="c0964-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="c0964-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="c0964-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c0964-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0964-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="c0964-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="c0964-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="c0964-121">ReaderQuotas</span></span>  
 <span data-ttu-id="c0964-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="c0964-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="c0964-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c0964-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0964-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="c0964-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0964-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0964-125">Requirements</span></span>  
  
|<span data-ttu-id="c0964-126">MOF</span><span class="sxs-lookup"><span data-stu-id="c0964-126">MOF</span></span>|<span data-ttu-id="c0964-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c0964-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c0964-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c0964-128">Namespace</span></span>|<span data-ttu-id="c0964-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c0964-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0964-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0964-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

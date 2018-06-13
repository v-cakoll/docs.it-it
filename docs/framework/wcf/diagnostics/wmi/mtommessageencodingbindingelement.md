---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: 83fa879fbef94e2dc9c142dfb92a51a54a7b60cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486534"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="01b31-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="01b31-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="01b31-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="01b31-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01b31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01b31-104">Syntax</span></span>  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="01b31-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="01b31-105">Methods</span></span>  
 <span data-ttu-id="01b31-106">La classe MtomMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="01b31-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="01b31-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="01b31-107">Properties</span></span>  
 <span data-ttu-id="01b31-108">La classe MtomMessageEncodingBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="01b31-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="01b31-109">Codifica</span><span class="sxs-lookup"><span data-stu-id="01b31-109">Encoding</span></span>  
 <span data-ttu-id="01b31-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="01b31-110">Data type: string</span></span>  
  
 <span data-ttu-id="01b31-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="01b31-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="01b31-112">Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.</span><span class="sxs-lookup"><span data-stu-id="01b31-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="01b31-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="01b31-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="01b31-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="01b31-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="01b31-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="01b31-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="01b31-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="01b31-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="01b31-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="01b31-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="01b31-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="01b31-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="01b31-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="01b31-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="01b31-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="01b31-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="01b31-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="01b31-121">ReaderQuotas</span></span>  
 <span data-ttu-id="01b31-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="01b31-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="01b31-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="01b31-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="01b31-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="01b31-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01b31-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01b31-125">Requirements</span></span>  
  
|<span data-ttu-id="01b31-126">MOF</span><span class="sxs-lookup"><span data-stu-id="01b31-126">MOF</span></span>|<span data-ttu-id="01b31-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="01b31-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="01b31-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="01b31-128">Namespace</span></span>|<span data-ttu-id="01b31-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="01b31-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01b31-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01b31-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

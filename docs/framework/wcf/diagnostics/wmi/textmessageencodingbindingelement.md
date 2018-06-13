---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: f9b94e946413967cc14282e85743a23327683b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486016"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="4aa09-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="4aa09-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="4aa09-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="4aa09-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aa09-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4aa09-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4aa09-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4aa09-105">Methods</span></span>  
 <span data-ttu-id="4aa09-106">La classe TextMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="4aa09-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4aa09-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4aa09-107">Properties</span></span>  
 <span data-ttu-id="4aa09-108">La classe TextMessageEncodingBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="4aa09-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="4aa09-109">Codifica</span><span class="sxs-lookup"><span data-stu-id="4aa09-109">Encoding</span></span>  
 <span data-ttu-id="4aa09-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4aa09-110">Data type: string</span></span>  
  
 <span data-ttu-id="4aa09-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4aa09-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4aa09-112">Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.</span><span class="sxs-lookup"><span data-stu-id="4aa09-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="4aa09-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4aa09-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="4aa09-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="4aa09-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="4aa09-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4aa09-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4aa09-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="4aa09-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="4aa09-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4aa09-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="4aa09-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="4aa09-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="4aa09-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4aa09-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4aa09-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="4aa09-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="4aa09-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4aa09-121">ReaderQuotas</span></span>  
 <span data-ttu-id="4aa09-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4aa09-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="4aa09-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4aa09-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4aa09-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="4aa09-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4aa09-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4aa09-125">Requirements</span></span>  
  
|<span data-ttu-id="4aa09-126">MOF</span><span class="sxs-lookup"><span data-stu-id="4aa09-126">MOF</span></span>|<span data-ttu-id="4aa09-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4aa09-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4aa09-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4aa09-128">Namespace</span></span>|<span data-ttu-id="4aa09-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4aa09-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4aa09-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4aa09-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

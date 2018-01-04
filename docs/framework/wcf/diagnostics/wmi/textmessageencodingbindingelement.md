---
title: TextMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f1e026296745f6fc40171866c81f91818789e01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="d68ba-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d68ba-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="d68ba-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d68ba-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d68ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d68ba-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d68ba-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d68ba-105">Methods</span></span>  
 <span data-ttu-id="d68ba-106">La classe TextMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="d68ba-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d68ba-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d68ba-107">Properties</span></span>  
 <span data-ttu-id="d68ba-108">La classe TextMessageEncodingBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d68ba-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="d68ba-109">Codifica</span><span class="sxs-lookup"><span data-stu-id="d68ba-109">Encoding</span></span>  
 <span data-ttu-id="d68ba-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d68ba-110">Data type: string</span></span>  
  
 <span data-ttu-id="d68ba-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d68ba-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d68ba-112">Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.</span><span class="sxs-lookup"><span data-stu-id="d68ba-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="d68ba-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d68ba-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="d68ba-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="d68ba-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="d68ba-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d68ba-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d68ba-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="d68ba-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="d68ba-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d68ba-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="d68ba-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="d68ba-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="d68ba-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d68ba-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d68ba-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="d68ba-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="d68ba-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d68ba-121">ReaderQuotas</span></span>  
 <span data-ttu-id="d68ba-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d68ba-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="d68ba-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d68ba-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d68ba-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="d68ba-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d68ba-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d68ba-125">Requirements</span></span>  
  
|<span data-ttu-id="d68ba-126">MOF</span><span class="sxs-lookup"><span data-stu-id="d68ba-126">MOF</span></span>|<span data-ttu-id="d68ba-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d68ba-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d68ba-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d68ba-128">Namespace</span></span>|<span data-ttu-id="d68ba-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d68ba-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d68ba-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d68ba-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

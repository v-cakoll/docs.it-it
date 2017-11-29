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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6e1eccbaae35a16fe4fb133296698d347c190e94
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="b1c85-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="b1c85-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="b1c85-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="b1c85-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c85-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1c85-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b1c85-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b1c85-105">Methods</span></span>  
 <span data-ttu-id="b1c85-106">La classe TextMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="b1c85-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b1c85-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b1c85-107">Properties</span></span>  
 <span data-ttu-id="b1c85-108">La classe TextMessageEncodingBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1c85-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="b1c85-109">Codifica</span><span class="sxs-lookup"><span data-stu-id="b1c85-109">Encoding</span></span>  
 <span data-ttu-id="b1c85-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="b1c85-110">Data type: string</span></span>  
  
 <span data-ttu-id="b1c85-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b1c85-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1c85-112">Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.</span><span class="sxs-lookup"><span data-stu-id="b1c85-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="b1c85-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="b1c85-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="b1c85-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="b1c85-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b1c85-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b1c85-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1c85-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="b1c85-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="b1c85-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="b1c85-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="b1c85-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="b1c85-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="b1c85-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b1c85-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1c85-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="b1c85-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="b1c85-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="b1c85-121">ReaderQuotas</span></span>  
 <span data-ttu-id="b1c85-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="b1c85-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="b1c85-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b1c85-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1c85-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="b1c85-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1c85-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1c85-125">Requirements</span></span>  
  
|<span data-ttu-id="b1c85-126">MOF</span><span class="sxs-lookup"><span data-stu-id="b1c85-126">MOF</span></span>|<span data-ttu-id="b1c85-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b1c85-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b1c85-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="b1c85-128">Namespace</span></span>|<span data-ttu-id="b1c85-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b1c85-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1c85-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1c85-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 67c1083daa9acfd204d4de50d4e9178b25aafcf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858390"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="37a35-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="37a35-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="37a35-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="37a35-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37a35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37a35-104">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="37a35-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="37a35-105">Methods</span></span>  
 <span data-ttu-id="37a35-106">La classe TextMessageEncodingBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="37a35-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="37a35-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="37a35-107">Properties</span></span>  
 <span data-ttu-id="37a35-108">La classe TextMessageEncodingBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="37a35-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="37a35-109">Codifica</span><span class="sxs-lookup"><span data-stu-id="37a35-109">Encoding</span></span>  
 <span data-ttu-id="37a35-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="37a35-110">Data type: string</span></span>  
  
 <span data-ttu-id="37a35-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="37a35-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37a35-112">Codifica del set di caratteri da utilizzare per l'emissione dei messaggi sull'associazione.</span><span class="sxs-lookup"><span data-stu-id="37a35-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="37a35-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="37a35-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="37a35-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="37a35-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="37a35-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="37a35-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37a35-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="37a35-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="37a35-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="37a35-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="37a35-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="37a35-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="37a35-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="37a35-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37a35-120">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="37a35-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="37a35-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="37a35-121">ReaderQuotas</span></span>  
 <span data-ttu-id="37a35-122">Tipo di dati: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="37a35-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="37a35-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="37a35-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37a35-124">Quote dei lettori.</span><span class="sxs-lookup"><span data-stu-id="37a35-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37a35-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37a35-125">Requirements</span></span>  
  
|<span data-ttu-id="37a35-126">MOF</span><span class="sxs-lookup"><span data-stu-id="37a35-126">MOF</span></span>|<span data-ttu-id="37a35-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="37a35-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="37a35-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="37a35-128">Namespace</span></span>|<span data-ttu-id="37a35-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="37a35-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37a35-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37a35-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
